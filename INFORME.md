### Integrantes:
1. **Estudiante 1:** Laura Andrea Cárdenas Zuelta  - **Código:** A00411072
2. **Estudiante 2:** Nicholas Solis Pinilla  - **Código:** A00411205
3. **Estudiante 3:** Juan José Rojas Correa - **Código:** A00409833

---

## 1. Experimento 

**Computador:  Lenovo IDEAPAD 5 (2-in-1). Processor: Ryzen 7 8845HS - Laura** 
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

> La configuración óptima identificada es **Baldosas de 64x64**, alcanzando el menor tiempo distribuido (15137 ms) y el mayor Speedup (7.59x).

**Computador:  Victus by HP Gaming Laptop 15-fa0xxx. Processor: 12th Gen Intel(R) Core(TM) i5-12450H (2.00 GHz) - Nicholas** 

| Estrategia | Parámetro | Tareas Generadas | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{p} \times 100$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| FixedCount (Franjas) | 2 | 2 | 120767 | 55736 | 2,17x | 108,3% |
| FixedCount (Franjas) | 4 | 4 | 120767 | 26736 | 4,52x | 225,9% |
| FixedCount (Franjas) | 8 | 8 | 120767 | 14796 | 8,16x | 408,1% |
| FixedCount (Franjas) | 16 | 16 | 120767 | 14426 | 8,37x | 418,6% |
| FixedTileSize (Baldosas) | 32 | 8160 | 120767 | 14268 | 8,46x | 423,2% |
| FixedTileSize (Baldosas) | 64 | 2040 | 120767 | 13998 | 8,63x | 431,4% |
| FixedTileSize (Baldosas) | 128 | 510 | 120767 | 14082 | 8,58x | 428,8% |
| **FixedTileSize (Baldosas)** | **256** | **135** | **120767** | **13909** | **8,68x** | **434,1%** |

> La configuración óptima identificada es **Baldosas de 256x256**, alcanzando el menor tiempo distribuido (13909 ms) y el mayor Speedup (8.68x).

**Computador: Lenovo LOQ 15IAX9. Processor: 12th Gen Intel(R) Core(TM) i5-12450HX - Juan José**

| Estrategia | Parámetro | Tareas Generadas | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{p} \times 100$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| FixedCount (Franjas) | 2 | 2 | 64410 | 33830 | 1,90x | 190,4% |
| FixedCount (Franjas) | 4 | 4 | 64410 | 17842 | 3,61x | 361,0% |
| FixedCount (Franjas) | 8 | 8 | 64410 | 10228 | 6,30x | 629,7% |
| FixedCount (Franjas) | 16 | 16 | 64410 | 7537 | 8,55x | 854,6% |
| FixedTileSize (Baldosas) | 32 | 8160 | 64410 | 7317 | 8,80x | 880,3% |
| **FixedTileSize (Baldosas)** | **64** | **2040** | **64410** | **6874** | **9,37x** | **937,0%** |
| FixedTileSize (Baldosas) | 128 | 510 | 64410 | 6958 | 9,26x | 925,7% |
| FixedTileSize (Baldosas) | 256 | 135 | 64410 | 7159 | 9,00x | 899,7% |

> La configuración óptima identificada es **Baldosas de 64x64**, alcanzando el menor tiempo distribuido (6874 ms) y el mayor Speedup (9,37x).


<img width="1192" height="745" alt="image" src="https://github.com/user-attachments/assets/81f8832d-3442-4ce7-949c-2a43a44dc535" />


---

## 2. Experimento 

**Computador:  Lenovo IDEAPAD 5 (2-in-1). Processor: Ryzen 7 8845HS - Laura** 

* **Estrategia Fija:** FixedTileSize (Baldosas 64x64)
* **Preset / Región:** `seahorse` (3840 x 2160, 5000 iteraciones)
* **Número de Workers Activos:** $p = 1$
* **Tiempo Secuencial Base ($T_{\text{sec}}$):** `114915 ms`

| Configuración | Hilos en Worker | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{\text{Hilos}} \times 100$) | Observaciones |
| :--- | :---: |:---------------------:|:----------------------:|:------------------------------------------------------:|:----------------------------------------------------:| :--- |
| **A (Monohilo)** | 1 |        115364         |         119664         |                          0.96X                          |                         96.4%                        | Monohilo puro por nodo |
| **B (Bihilo)** | 2 |        115383         |         60709          |                          1.90X                          |                        190.1%                       | 2 hilos en paralelo |
| **C (Cores físicos)** | 8 |        114809         |         15380          |                          7.46X                          |                        745.5%                         | Saturación de cores físicos |
| **D (Sobredimensionado)**| 64 |        116407         |          8745          |                         13.31X                          |                        1331.1%                        | Contención extrema / Context switching |

**Computador:  Victus by HP Gaming Laptop 15-fa0xxx. Processor: 12th Gen Intel(R) Core(TM) i5-12450H (2.00 GHz) - Nicholas** 

* **Estrategia Fija:** FixedTileSize (Baldosas 256x256)
* **Preset / Región:** `seahorse` (3840 x 2160, 5000 iteraciones)
* **Número de Workers Activos:** $p = 1$
* **Tiempo Secuencial Base ($T_{\text{sec}}$):** `120767 ms`

| Configuración | Hilos en Worker | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{\text{Hilos}} \times 100$) | Observaciones |
| :--- | :---: |:---------------------:|:----------------------:|:------------------------------------------------------:|:----------------------------------------------------:| :--- |
| **A (Monohilo)** | 1 |        129069         |         142490         |                          0,91x                          |                         90,6                         | Monohilo puro por nodo |
| **B (Bihilo)** | 2 |        142915         |         52005          |                          2,75x                          |                        274,8                         | 2 hilos en paralelo |
| **C (Cores físicos)** | 8 |        129880         |         22934          |                           5,66x                          |                        566,3                         | Saturación de cores físicos |
| **D (Sobredimensionado)**| 64 |        181027         |          15347          |                          11,80x                          |                        1179,6                        | Contención extrema / Context switching |

**Computador: Lenovo LOQ 15IAX9. Processor: 12th Gen Intel(R) Core(TM) i5-12450HX - Juan José**

* **Estrategia Fija:** FixedTileSize (Baldosas 64x64)
* **Preset / Región:** `seahorse` (3840 x 2160, 5000 iteraciones)
* **Número de Workers Activos:** $p = 1$
* **Tiempo Secuencial Base ($T_{\text{sec}}$):** `64410 ms`

| Configuración | Hilos en Worker | $T_{\text{sec}}$ (ms) | $T_{\text{dist}}$ (ms) | Speedup ($S = \frac{T_{\text{sec}}}{T_{\text{dist}}}$) | Eficiencia ($E = \frac{S}{\text{Hilos}} \times 100$) | Observaciones |
| :--- | :---: |:---------------------:|:----------------------:|:------------------------------------------------------:|:----------------------------------------------------:| :--- |
| **A (Monohilo)** | 1 | 65458 | 66940 | 0,98x | 97,8% | Monohilo puro por nodo |
| **B (Bihilo)** | 2 | 64297 | 34557 | 1,86x | 93,1% | 2 hilos en paralelo |
| **C (Cores físicos)** | 8 | 64993 | 10035 | 6,48x | 80,9% | Saturación de cores físicos |
| **D (Sobredimensionado)** | 64 | 64897 | 7304 | 8,89x | 13,9% | Contención extrema / Context switching |

<img width="1177" height="746" alt="image" src="https://github.com/user-attachments/assets/64b47711-b683-472a-b501-fc28a1d8cd3c" />

---

## 3. Experimento 

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
*  Victus by HP Gaming Laptop 15-fa0xxx. Processor: 12th Gen Intel(R) Core(TM) i5-12450H (2.00 GHz) 
---

## 4. Cuestionario de Análisis Conceptual y Discusión Técnica

### 1. La Trampa del Espacio Vacío vs. Zona de Estrés: 
*Explique por qué el cómputo monohilo secuencial en la vista clásica
(classic) parece rápido a pesar de fijar 5,000 iteraciones, y contraste este comportamiento con el tiempo obtenido al renderizar
la región hiperdensa de Seahorse Valley. ¿Por qué la vista macro oculta la necesidad de un clúster distribuido?*

En la vista clasica, aun que se establezca un maxmo de 5.000 iteraciones, la mayoria de los puntos no llega a ese limite: aproximadamente el 76% escapa en menos de 20 iteraciones. Por eso, el calculo secuencial parece rapido: gran parte de la imagen se resuelve con pocas operaciones.

Seahorse Valley es diferente porque concentra muchos pixeles en la frontera del fractal, donde cada uno puede requerir entre 4.000 y 5.000 iteraciones. En la medición disponible, el calculo secuencial tardo 114.915 ms, mientras que al repartir el trabajo entre dos workers toma 15.137 ms. Asi, la vista panoramica puede dar una impresión engañosa, no muestra la carga mucho mayor de las zonas densas, donde distribuir el calculo si aporta una mejora clara.

### 2. Colapso por Grano Fino
*Al ejecutar con baldosas de 16x16 (o grano muy fino), se generan más de 8,000 llamadas RPC sobre la red. Explique técnicamente por qué el tiempo distribuido $T_{dist}$ se degrada frente a baldosas de 64x64, analizando el costo de serialización binaria en Slice, latencia de red TCP y cambios de contexto en el Maestro.*  

Al utilizar un grano muy fino como el de 32x32 se tienen que realizar más de 8,000 llamadas RPC, lo cual no es eficiente porque se incrementa la latencia de red en TCP por cada paquete enviado y al ser tantas llamadas, el sistema pierde demasiado tiempo empaquetando y reconstruyendo los datos. Además, el Maestro se satura atendiendo tantas peticiones al mismo tiempo, sufriendo una sobrecarga por cambios de contexto entre los hilos. En cambio cuando se utilizan baldosas de 64x64 las llamadas se reducen, por lo que no se genera tanta latencia, se evita el desgaste de serializar miles de paquetes pequeños y el Maestro puede procesar la imagen mucho más rápido.

---

### 3. Fracaso de la Partición Estática
*Al dividir la imagen en 2 o 4 franjas fijas (FixedCount), compare el tiempo de cómputo reportado por cada worker. ¿Por qué ocurre un desbalance de carga tan severo y cómo el patrón Bag of Tasks resuelve esta limitación?*

Cuando la imagen se divide en 2 o 4 franjas horizontales fijas, cada franja cubre una banda completa del ancho de la imagen, pero la carga del conjunto no se distribuye de manera uniforme en el espacio. Las franjas donde los puntos tardan miles de iteraciones en escapar consumen mucho más tiempo que las franjas que cubren zonas exteriores donde los puntos escapan en pocas iteraciones. Con 2 franjas fijas un worker puede terminar en segundos mientras el otro sigue calculando eso explica el bajo speedup observado (1.88x con Laura, 2.17x con Nicholas) a pesar de tener 2 workers disponibles.

El patrón Bag of Tasks resuelve esta limitación porque no asigna una porción fija a cada worker desde el inicio. Por el contrario el Maestro mantiene una cola de tareas pequeñas que aqui manejamos como baldosas, y cada worker pide la siguiente tarea apenas termina la anterior. Si a un worker le toca una baldosa densa que tarda más el otro worker sigue tomando baldosas de la cola, de esta manera balanceando la carga de forma dinámica según la capacidad real de cada nodo, sin importar qué tan desigual sea la distribución del cómputo en la imagen.

---

### 4. Límites del ThreadPool
*En el Experimento 2, ¿qué ocurrió al elevar el pool de hilos a 64? ¿La velocidad creció proporcionalmente o se degradó? Explique el fenómeno de contención de CPU y alternancia de contexto (thread context switching).*

Al elevar el pool de hilos a 64, la velocidad no creció de forma proporcional al número de hilos. En la máquina de Laura, pasar de 8 hilos $T_dist=15380 ms$ a 64 hilos ($T_dist=8745 ms$) mejoró el tiempo, pero la ganancia está lejos de ser 8 veces mayor. En la máquina de Nicholas ocurre algo similar de 8 hilos $T_dist=22934 ms$ a 64 hilos $T_dist=15347 ms$ hay mejora, pero tampoco proporcional. En la máquina de Juan el patrón se repite de 8 hilos $T_dist=10035 ms$ a 64 hilos $T_dist=7304 ms$.

Esto ocurre porque los procesadores de las tres máquinas tienen un número limitado de cores físicos, muy por debajo de 64. Cuando se crean 64 hilos para ejecutarse sobre esos pocos cores, el sistema operativo tiene que alternar constantemente la ejecución de esos hilos, lo que se conoce como cambio de contexto cada cambio implica guardar el estado de un hilo, cargar el del siguiente y vaciar cachés, lo cual consume tiempo de CPU que no se traduce en trabajo útil. A esto se suma la contención por recursos compartidos, como la caché L3 y el bus de memoria, porque muchos hilos compiten por los mismos datos al mismo tiempo. La ganancia que sí se observa al pasar de 8 a 64 hilos se debe a que, con baldosas de carga desigual, tener más hilos evita que un core quede ocioso esperando que termine una baldosa pesada, pero esa ganancia se paga con el overhead del S.O.

---

### 5. Ley de Amdahl
*A partir de la curva de aceleración obtenida en el Experimento 3, estime la fracción estrictamente secuencial $(1 - f)$ del sistema impuesta por la generación de tareas, encolado y reensamblado en el Maestro.*

La Ley de Amdahl establece que el speedup máximo con $p$ procesadores es

$$S = \frac{1}{(1 - f) + \frac{f}{p}}$$
Usando el dato de $p = 4$ workers con speedup real $S = 12.51$ del Experimento 3, y considerando que cada worker usa 4 hilos (16 unidades de cómputo efectivas en total):

$$12.51 = \frac{1}{(1-f) + \frac{f}{16}}$$

$$(1-f) + \frac{f}{16} = \frac{1}{12.51} = 0.0799$$

Sea $s = (1-f)$, entonces $f = 1 - s$:

$$s + \frac{1-s}{16} = 0.0799$$

$$16s + 1 - s = 1.279$$

$$15s = 0.279$$

$$s = (1-f) \approx 0.0186$$

La fracción estrictamente secuencial del sistema es aproximadamente $1.9$%, correspondiente al tiempo que el Maestro gasta generando las $2040$ tareas El 98.1% restante corresponde a trabajo paralelizable.
---
## Los otros puntos del git
### 4. Puntos de Quiebre del Hardware y la Memoria
#### a) Precisión numérica y double IEEE 754

Un double tiene $52$ bits de mantisa, lo que da una precisión de aproximadamente 15-16 dígitos decimales significativos. En el caso analizado cuando el factor de magnificación supera aproximadamente $10^13$ o $10^14$ la diferencia entre coordenadas de pixeles vecinos se vuelve menor que el épsilon de máquina del aproximadamente $2.2*10^-16$. En ese punto pixeles distintos empiezan a mapear a la misma coordenada representable y el cálculo pierde la capacidad de distinguir detalles fino, apareciendo zonas planas, bloques de pixeles con el mismo número de iteraciones formando bandas o cuadrados artificiales en vez de la estructura fractal continua, especialmente visible en los bordes donde debería haber detalles infinitos.

Si sustituimos double por BigDecimal eliminaría ese límite de precisión ya que permite tantos dígitos como se configure, pero el costo  sería mucho mayor, dado que en BigDecimal cada operación más lenta que con `double` ya que convierte cada digito en un hexa y el tiempo de cómputo por pixel se dispararía dependiendo de la precisión configurada.

#### b) Saturación de RAM a 16K/32K

A resolución 16K estariamos hablando de casi 132.7 millones d e pixeles(15360×8640 ) o en 32K unos 530.8 millones pixeles(30720×17280 ) el array de resultados por pixel típicamente un int[] requiere varios GB solo para almacenar la imagen en memoria antes de contar buffers intermedios el array de colores RGB para el PNG final, y la sobrecarga del heap. Con el heap por defecto los limites se alcanzan rápido.

La excepción que arroja la JVM es java.lang.OutOfMemoryError: Java heap space o si el array supera el máximo de elementos por dimensión OutOfMemoryError: Requested array size exceeds VM limit.

---



## 6. Bitácora de Uso Ético de IAG (Nivel 3: Colaboración Asistida)

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
