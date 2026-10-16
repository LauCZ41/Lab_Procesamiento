# Informe de Taller Evaluativo: Renderizado Distribuido de Fractales (Patrón Master-Worker)

**Asignatura:** Computación en Internet I (`09810 - TIC`)  
**Institución:** Universidad Icesi  
**Semestre:** 2026-2 | **NRC:** 12378 / 12377  

### Integrantes del Equipo:
1. **Estudiante 1:** Laura Andrea Cárdenas Zuelta  - **Código:** A00411072
2. **Estudiante 2:** Nicholas Solis Pinilla  - **Código:** A00411205
3. **Estudiante 3:** Juan José Rojas Correa  - **Código:** A00

---

## 1. Experimento 1: Dilema de la Granularidad y Sobrecosto de Red

| Estrategia | Parámetro | Tareas Generadas | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{p} \times 100$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| FixedCount (Franjas) | 2 | 2 | 114915 | 61211 | 1.88x | 93.9% |
| FixedCount (Franjas) | 4 | 4 | 114915 | 30698 | 3.74x | 187.2% |
| FixedCount (Franjas) | 8 | 8 | 114915 | 16450 | 6.99x | 349.3% |
| FixedCount (Franjas) | 16 | 16 | 114915 | 15560 | 7.39x | 369.3% |
| FixedTileSize (Baldosas) | 32 | 8160 | 114915 | 15359 | 7.48x | 374.1% |
| **FixedTileSize (Baldosas)** | **64** | **2040** | **114915** | **15137** | **7.59x** | **379.6%** |
| FixedTileSize (Baldosas) | 128 | 510 | 114915 | 15175 | 7.57x | 378.6% |
| FixedTileSize (Baldosas) | 256 | 135 | 114915 | 15216 | 7.55x | 377.6% |

> La configuración óptima identificada es **Baldosas de 64x64**, alcanzando el menor tiempo distribuido (15,137 ms) y el mayor Speedup (7.59x).

---

## 2. Experimento 2: Concurrencia y Saturación del Pool de Hilos en Workers

* **Estrategia Fija:** FixedTileSize (Baldosas 64x64)
* **Preset / Región:** `seahorse` (3840 x 2160, 5000 iteraciones)
* **Número de Workers Activos:** $p = 1$
* **Tiempo Secuencial Base ($T_{\text{sec}}$):** `114915 ms`

| Configuración | Hilos en Worker | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{\text{Hilos}} \times 100$) | Observaciones |
| :--- | :---: |:---------------------:|:----------------------:|:------------------------------------------------------:|:----------------------------------------------------:| :--- |
| **A (Monohilo)** | 1 |        115364         |         119664         |                          0.96                          |                         96.4                         | Monohilo puro por nodo |
| **B (Bihilo)** | 2 |        115383         |         60709          |                          1.90                          |                        190.1                         | 2 hilos en paralelo |
| **C (Cores físicos)** | 8 |        114809         |         15380          |                          7.46                          |                        745.5                         | Saturación de cores físicos |
| **D (Sobredimensionado)**| 64 |        116407         |          8745          |                         13.31                          |                        1331.1                        | Contención extrema / Context switching |

---

## 3. Experimento 3: Escalabilidad del Clúster y Ley de Amdahl

* **Estrategia Fija:** FixedTileSize (Baldosas 64x64)
* **Configuración de Hilos por Worker:** 4 u 8 hilos (óptimo por worker)
* **Tiempo Secuencial Base ($T_{\text{sec}}$):** `114915 ms`

| Nodos Workers ($p$) | Hilos / Worker | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup Real ($S$) | Speedup Teórico Máx. | Eficiencia ($E = \frac{S}{p} \times 100$) |
| :---: |:--------------:|:---------------------:|:----------------------:|:------------------:| :---: |:-----------------------------------------:|
| **$p = 1$** |       4        |        115380         |         39984          |        2.89        | 1.00x |                   288.6                   |
| **$p = 2$** |       4        |        115330         |         17050          |        6.76        | 2.00x |                   338.2                   |
| **$p = 4$** |       4        |        117013         |          9344          |       12.51        | 4.00x |                   313.1                   |

Realizado con workers repartidos entre dos maquinas:
*  Lenovo IDEAPAD 5 (2-in-1). Processor: Ryzen 7 8845HS
* 
---

## 4. Cuestionario de Análisis Conceptual y Discusión Técnica

### 1. Colapso por Grano Fino
*Al ejecutar con baldosas de 16x16 (o grano muy fino), se generan más de 8,000 llamadas RPC sobre la red. Explique técnicamente por qué el tiempo distribuido $T_{\text{dist}}$ se degrada frente a baldosas de 64x64, analizando el costo de serialización binaria en Slice, latencia de red TCP y cambios de contexto en el Maestro.*

> **Respuesta:**  
> [Completar análisis aquí]

---

### 2. Fracaso de la Partición Estática
*Al dividir la imagen en 2 o 4 franjas fijas (FixedCount), compare el tiempo de cómputo reportado por cada worker. ¿Por qué ocurre un desbalance de carga tan severo y cómo el patrón Bag of Tasks resuelve esta limitación?*

> **Respuesta:**  
> [Completar análisis aquí]

---

### 3. Límites del ThreadPool
*En el Experimento 2, ¿qué ocurrió al elevar el pool de hilos a 64? ¿La velocidad creció proporcionalmente o se degradó? Explique el fenómeno de contención de CPU y alternancia de contexto (thread context switching).*

> **Respuesta:**  
> [Completar análisis aquí]

---

### 4. Ley de Amdahl
*A partir de la curva de aceleración obtenida en el Experimento 3, estime la fracción estrictamente secuencial $(1 - f)$ del sistema impuesta por la generación de tareas, encolado y reensamblado en el Maestro.*

> **Respuesta:**  
> [Completar cálculo de $(1-f)$ aquí]

---

## 5. Bitácora de Uso Ético de IAG (Nivel 3: Colaboración Asistida)

* **Herramienta utilizada:** Asistente IA (Gemini / Antigravity IDE)
* **Prompts clave utilizados:**
  1. *"Guiame para hacer el experimento 2..."*
  2. *"Crea un archivo md con la tabla vacia para poder llenar los datos..."*
* **Asistencia recibida:**
  - Automatización del harness experimental y lectura de métricas de rendimiento.
  - Estructuración de tablas de Speedup y Eficiencia.
  - Análisis técnico de contención de CPU y sobrecosto de middleware Slice.
* **Justificación crítica y validación humana:**
  - Todos los comandos fueron ejecutados y validados localmente en la máquina física.
  - Los tiempos $T_{\text{sec}}$ y $T_{\text{dist}}$ corresponden a mediciones reales de CPU y red.
