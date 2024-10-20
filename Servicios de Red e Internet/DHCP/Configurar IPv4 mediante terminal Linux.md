## 📁 Archivo de Configuración

Ruta del archivo:
``/etc/netplan/01-network-manager-all.yaml``
> El nombre del archivo puede variar.
> Para saber el nombre de nuestra interfaz, podemos utilizar el comando *"ip a"*.

---

## Ejemplo de archivo configurado:

```
network:
    ethernets:
        enp0s3:
            dhcp4: true
        enp0s8:
            dhcp4: no
            addresses:
              - 192.168.1.44/24
            gateway4: 192.168.1.1
            nameservers:
              addresses:
                - 192.168.1.44
                - 1.1.1.1
    version: 2
```


---

## 📝 Elementos del Archivo de Configuración

### Ethernets
- `ethernets`
  - Define las interfaces de red.

### DHCP4
- `dhcp4`
  - Indica si el servicio DHCP está habilitado (`true` o `false`).

### Addresses
- `addresses:`
  - Lista de direcciones IP en formato `[IP1, IP2, ...]`.

### Gateway4
- `gateway4`: 
  - Especifica la puerta de enlace (sin corchetes).

### Nameservers:
- `nameservers:`
  - **Search**:
    - `search: []`
      - Dominio(s) de búsqueda DNS.
  - **Addresses**:
    - `addresses: []`
      - Lista de servidores DNS.

