# 🐧 Mi Guía de Administración en Linux

Bienvenido a mi documentación personalizada. Aquí registro lo que voy aprendiendo en **DAW** sobre gestión de procesos y automatización.

## 1. Conceptos Clave
En esta sección repasamos los pilares de la administración:
* **Usuarios:** Gestión con `useradd` y `usermod`.
* **Procesos:** Control de prioridades con `nice` y `renice`.
* **Automatización:** Uso de `cron` y `at`.

---

## 2. Comandos Útiles de Monitorización
Para administrar el sistema, estos son los comandos que más utilizo:

1.  **Estado del Sistema:** `uptime`
2.  **Memoria Libre:** `free -h`
3.  **Procesos en tiempo real:** `top` o `htop`

### Ejemplo de script de limpieza
Este es el código que usamos para limpiar la carpeta `/tmp`:

```bash
#!/bin/bash
# Borrar archivos de más de 7 días
find /tmp -type f -mtime +7 -delete
echo "Limpieza realizada con éxito."
```