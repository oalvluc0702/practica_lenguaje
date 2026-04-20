# 🌐 Administración de Red local

En esta sección se detallan los comandos esenciales para diagnosticar y configurar la red en entornos Linux.

## 1. Diagnóstico Rápido
Cuando la conexión falla, seguimos este orden de comandos:

1.  **Verificar interfaces:** `ip a`
2.  **Probar conectividad:** `ping -c 4 google.com`
3.  **Ruta de los paquetes:** `traceroute google.com`

---

## 2. Puertos y Servicios en Escucha
Es vital saber qué aplicaciones están abriendo puertos en nuestro servidor.

| Comando | Descripción |
| :--- | :--- |
| `ss -tuln` | Muestra puertos TCP/UDP abiertos (sustituto de netstat) |
| `nmcli` | Gestión de Network Manager por terminal |
| `hostname -I` | Muestra la IP privada rápidamente |

## 3. Configuración Temporal

 Los cambios realizados con el comando `ip` se pierden al reiniciar. Para cambios permanentes, edita los ficheros en `/etc/netplan/` (Ubuntu) o `/etc/network/interfaces`.

```bash
title="Asignar IP manual"
# Asignar IP a la interfaz eth0
sudo ip addr add 192.168.1.50/24 dev eth0
```
```bash
# Levantar la interfaz
sudo ip link set eth0 up
```