# 🌐 El Protocolo DNS

**DNS (Domain Name System)** es un protocolo de nivel de aplicación que establece las normas de funcionamiento de un servicio de nombres jerárquico basado en dominios.

**El protocolo DNS** establece que dentro de una red puede haber varios servidores DNS que prestan el servicio de resolución de nombres.

**El sistema DNS** se basa en una organización en dominios y subdominios. Un dominio tiene un nombre y todos sus miembros comparten ese nombre.

---
## 🏢 Tipos de dominio

1. **Dominio raíz:** Es la parte superior de la jerarquía de DNS y está representada por un único punto "." Todos los demás dominios se derivan del dominio raíz. Los servidores del dominio raíz tienen información sobre los servidores de dominio de TLD.
2. **Dominios de nivel superior (TLD):** Son el nivel que sigue al dominio raíz. Por lo general se clasifican de la siguiente manera:
	- **Dominios genéricos de nivel superior (gTLD):**
		- Son dominios comunes como: **.com**,**.net**,**.org**,**.edu**.
	-  **Dominios de nivel superior con código de país (ccTLD):**
		-  Son códigos de dos letras que representan países o regiones: **.es**,**.fr**,**.co**,**.eu**.
	- **Dominios de nivel superior patrocinados (sTLD):**
		- Son TLD que están patrocinados por organizaciones: **.aero**,**.travel**,**.fm**.
	- **Dominios lingüísticos de nivel superior (ITLD):**
		- Son TLD que tienen como objetivo el uso específico de idiomas: **.cat**,**.gal**.
3. **Dominios de segundo nivel:** Son los dominios que se registran bajo los TLD. Las entidades registran estos dominios, algunos ejemplos:
	- wikipedia.org
	- mec.es
	- google.com
4. **Subdominios:** Son dominios que se crean bajo dominios de segundo nivel u otros subdominios. No requieren un registro independiente como los dominios de segundo nivel. El propietario del dominio de segundo nivel puede crear subdominios. 

---
## 🏗️Funcionamiento de DNS

Los dominios funcionan en conjunto con los servidores DNS para traducir los nombres de dominio en direcciones IP, lo que permite que los usuarios se conecten a sitios web y servicios en internet.

Funcionamiento:
1. **Usuario ingresa nombre de dominio** 
2. **Consulta DNS:** El equipo del usuario realiza una consulta DNS al caché del navegador, si no la encuentra pasa al archivo de configuración hosts de su equipo local, si no lo encuentra en el fichero le pasa la petición al servidor DNS configurado.
3. **Resolución DNS:** El servidor DNS verifica sus registros, si no tiene la dirección IP, puede realizar un proceso de [[resolución iterativa o recursiva]] para consultar otros servidores DNS en la jerarquía.
4. **Devolución de la dirección IP:** El servidor DNS envía la dirección IP de vuelta al usuario. 

---
## 🔄 Resoluciones DNS inversas

La resolución DNS inversa se basa en un dominio de nivel superior especializado llamado .arpa, específicamente el subdominio **in-addr.arpa** para direcciones IPv4. Esta jerarquía está estructurada en función de los octetos de direcciones IP dispuestos en orden inverso.

Funcionamiento:
1. **Dirección IP:** Queremos encontrar el nombre de dominio asociado con la ip 193.28.0.5.
2. **Invertir octetos y añadir in-addr.arpa:** La dirección IP pasa a ser 5.0.28.193.in-addr.arpa, que utilizaremos como nombre de dominio.
3. **Consulta DNS:** Se envía una consulta DNS para este nombre de dominio.
4. **Respuesta del servidor autorizado:** El servidor DNS autorizado responderá con un registro PTR(pointer), SOA o NS, este registro contendrá el nombre del dominio asociado.

---
## 📋Zonas de DNS

Una **zona** es una parte del sistema de nombres de dominio que está bajo la autoridad de un servidor DNS específico.

Las zonas se encargan de resolver los nombres de dominio dentro de esa zona, traduciendo los nombres a direcciones IP.

Las zonas pueden ser:
1. **Primarias:** Contienen los archivos de configuración de la zona.
2. **Secundarias:** Obtienen copias de las zonas primarias, son de solo lectura. Cuando la zona primaria no es accesible, se puede utilizar esta zona para la resolución de nombres.
