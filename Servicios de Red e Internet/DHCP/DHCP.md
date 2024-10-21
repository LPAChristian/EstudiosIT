# 🌐 El Protocolo DHCP

**DHCP (Dynamic Host Configuration Protocol)** es un protocolo de red que asigna automáticamente direcciones IP y [[otros parámetros de configuración]] a los dispositivos, facilitando su conexión y comunicación en la red sin necesidad de configuración manual.

---
## Configuración Manual

- **Sistemas Windows:** Los sistemas Windows cuentan con una herramienta gráfica que permite realizar la gestión del direccionamiento IPv4 manual.
- **Sistemas Linux:** Las distribuciones populares vienen con una herramienta llamada NetworkManager la cual permite la gestión de las interfaces de red mediante interfaz gráfica o línea de comandos. Para entender cómo ajustar una dirección mediante terminal, lea: [[Configurar IPv4 mediante terminal Linux]].

---
## Funcionamiento de Servidor DHCP

El funcionamiento de DHCP en la red se basa en un modelo cliente/servidor con uno o varios equipos servidores que proporcionan el servicio y varios clientes que reciben automáticamente los parámetros de red.

Se pueden hacer uso de [[agentes relay]] para centralizar un mismo servidor DHCP en varias redes dentro de una gran empresa.

Función por capas:
1. **DHCP Solicitud:**
	1. Cuando un usuario inicia el dispositivo, se manda un paquete modo broadcast anunciando que busca un servidor DHCP.
	2. El paquete incluye la MAC del usuario para que el servidor pueda responder.
2. **DHCP Propuesta:**
	1. El servidor DHCP comprueba que la IP que le va a asignar no esté en uso en la red mediante un mensaje ARP (Address Resolution Protocol).
	2. Si la IP no se encuentra en uso, el servidor responde al usuario con la oferta de DHCP.
	3. La oferta del DHCP incluye la IP, máscara de subred y los parámetros opcionales.
3. **DHCP Aceptación:**
	1. El usuario recibe la oferta del DHCP.
	2. El usuario selecciona la primera oferta recibida.
	3. El usuario manda un paquete de vuelta al DHCP indicando que acepta la oferta indicada.
4. **DHCP Confirmación:**
	1. El servidor DHCP recibe la confirmación del usuario.
	2. El servidor confirma la asignación de IP y el tiempo de concesión junto otros parámetros necesarios.
	3. En este momento se configuran los parámetros de red del cliente.

---
## Tipos de asignaciones DHCP

1. **Asignación estática o manual:** Se reserva una IP exclusiva para un usuario, el usuario siempre recibirá esta misma IP.
2. **Asignación automática:** Se le asigna una IP dentro del rango disponible a cualquier usuario de forma permanente, hasta que el cliente renuncie a esta.
3. **Asignación dinámica:** Se le asigna una IP dentro del rango disponible a cualquier usuario con un tiempo de concesión indicado, el usuario deberá renovar la concesión con el servidor antes de que este termine si quiere mantener la misma IP.
