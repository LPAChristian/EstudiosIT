# 🔐 La Seguridad de la Información

Un sistema de información es seguro siempre que cumpla con los elementos básicos de la seguridad informática:

1. **Fiabilidad:** Probabilidad de buen funcionamiento de algo.
2. **Confidencialidad:** Que se hace o se dice en confianza o con seguridad recíproca entre dos o más personas.
3. **Integridad:** Que no carece de ninguna de sus partes.
4. **Disponibilidad:** Que se puede disponer libremente de ella o que está lista para usarse o utilizarse.

> [!EN RESUMEN]
> Se puede decir que un sistema es **fiable** si funciona correctamente, **confidencial** si la información es accesible solamente para las personas autorizadas, **íntegro** si el contenido de la información no se altera o se altera solamente por personal autorizado y **disponible** si el sistema funciona y los usuarios tienen acceso a todos los componentes del sistema.

Podemos distinguir entre dos tipos de seguridad:
1. [[Seguridad física y ambiental]]
2. [[Seguridad lógica]]

---
## Elementos vulnerables

La **vulnerabilidad** en un sistema informático hace referencia a las probabilidades que existen de que una amenaza se materialice contra un [[activo]].

Los activos que forman parte de un sistema informático son:
1. Datos
2. Software
3. Hardware
4. Redes
5. Soportes
6. Instalaciones
7. Personal
8. Servicios

Un sistema informático está compuesto por:
1. Hardware
2. Software
3. Datos
4. Personal


> [!Nota] 
> Cada uno de estos activos presenta diferentes vulnerabilidades, las más claras son las vulnerabilidades asociadas al personal que maneja el sistema informático.

El proceso general para analizar las vulnerabilidades de un sistema se puede explicar en varios pasos:
1. Identificar los activos del sistema
2. Identificar las medidas de seguridad existentes
3. Descubrir las vulnerabilidades
4. Valorar las posibles amenazas
5. Establecer los objetivos de seguridad de la organización
6. Valorar los daños que produciría un ataque
7. Seleccionar las medidas de protección posibles

---
## Amenazas

Una amenaza es una **circunstancia que podría afectar al sistema aprovechando alguna vulnerabilidad de éste.** Todos los sistemas son vulnerables en mayor o menos medida.

El sistema informático se puede distinguir en dos partes, y cada una de estas tiene sus propias vulnerabilidades:
1. [[Amenazas físicas (hardware)]]
2. [[Amenazas lógicas (software)]]

Pero también se puede clasificar a las amenazas en función de la manera que tienen de interferir con los datos:

| Forma de interferor | Descripción                                                                                                                                                                                                        | Gráfico                              |
| ------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| Flujo normal        | La información es enviada por el emisor al receptor, llegando a su destinatario sin que la información emitida sea accedida ni modificada.                                                                         | ![[Flujo Normal.png]]                |
| Intercepción        | El intruso accede a información transmitida por la red, pero no se modifica dicha información.                                                                                                                     | ![[Intercepción.png]]                |
| Interrupción        | Ataque activo que se ataca al principio de disponibilidad de un recurso del sistema o de la red, no pudiendo ser usado dicho recurso. Un ejemplo es un ataque DoS o DDoS.                                          | ![[Interrupción.png]]                |
| Modificación        | Ataque activo que se atacan los principios de confidencialidad e integridad. Los datos son modificados en algún momento entre su creación por parte del emisor y su llegada al receptor.                           | ![[Modificación.png]]                |
| Fabricación         | Ataque activo en el que se ataca al principio de autenticación. Se trata de modificaciones destinadas a conseguir que el producto final sea similar al atacado de forma que sea difícil distinguirlo del original. | ![[Fabricación.png]] |

---
## Análisis forense

El análisis forense es un proceso científico que elabora y verifica hipótesis, mediante el cual:
1. Se identifican las fuentes de las evidencias
2. Se preservan las evidencias
3. Se analizan las evidencias
4. Se presentan las conclusiones

Los principales objetivos del análisis forense son:
1. Recrear lo que ha ocurrido en un dispositivo digital durante el incidente de seguridad 
2. Analizar las incidencias para impedir que se repitan en el futuro

La recogida de evidencias debe seguir un orden de acuerdo al grado de volatilidad.
Los datos volátiles son aquellos que se pierden cuando se pierde la alimentación eléctrica del sistema, una secuencia de recogida de información volátil sería:
1. Registros caché
2. Tabla de enrutamiento
3. Caché ARP
4. Archivos temporales del sistema
