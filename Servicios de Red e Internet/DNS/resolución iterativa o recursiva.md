> [!NOTE]
> Ambos procesos tienen como objetivo encontrar la dirección IP asociada con un nombre de dominio.
> 
> En la **resolución iterativa** el servidor DNS informa al cliente de la dirección IP de otro servidor DNS, permitiendo que el cliente continúe la consulta por su cuenta.
> En la **resolución recursiva** el servidor DNS consulta otros servidores DNS en nombre del cliente, y devuelve el resultado de la consulta.

**Resolución iterativa:**
1. **Consulta inicial:** Se envía una consulta al servidor DNS solicitando la dirección IP de un nombre específico de dominio.
2. **Referencia:** El servidor comprueba si tiene la información solicitada en su caché o en los archivos de zona, si no es el caso, proporcionará una referencia a un servidor con mayor autoridad.
3. **Consultas del cliente al servidor raíz:** El cliente envía una consulta al servidor raíz referido.
4. **Referencia al servidor raíz:** El servidor raíz, conociendo las direcciones de los servidores TLD, remitirá al cliente a uno de esos servidores.
5. **El cliente consulta al servidor TLD:** El cliente hace la consulta a un servidor referido TLD.
6. **Referencia del servidor TLD:** El servidor TLD tendrá la información sobre el servidor autorizado para el dominio indicado, y remitirá al cliente ese servidor.
7. **El cliente consulta al servidor autorizado:** El cliente finalmente hace la consulta al servidor autorizado del dominio inicial.
8. **Respuesta del servidor autorizado:** El servidor autorizado, que tiene la información solicitada, responderá con la IP del nombre del dominio.
 ![[dnsiterativa.png]]


**Resolución recursiva:**
1. **Consulta inicial:** Se envía una consulta al servidor DNS solicitando la dirección IP de un nombre específico de dominio.
2. **El servidor DNS asume la responsabilidad:** El servidor DNS asume la responsabilidad total de encontrar la dirección IP, consultando a otros servidores DNS en nombre del cliente hasta obtener la respuesta.
3. **Consulta de servidores raíz, TLD y autorizados:** El servidor seguirá una cadena de referencia similar a la resolución iterativa hasta encontrar la IP del dominio que quiere el cliente.
4. **Respuesta del servidor DNS:** Una vez el servidor DNS obtiene la respuesta del servidor autorizado, envía esa dirección IP directamente al cliente.
![[dnsrecursiva.png]]

