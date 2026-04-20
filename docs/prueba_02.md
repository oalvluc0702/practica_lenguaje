# Buenas Prácticas y Resolución de Problemas

Esta sección sirve como guía de referencia rápida para mantener el sistema operativo estable y solucionar los errores más comunes encontrados durante las prácticas.

## 1. Permisos de Archivos
Es común encontrarse con el error `Permission denied`. Antes de usar `sudo` de forma indiscriminada, verifica los permisos actuales.

### Estados de permisos comunes:
- **755 (rwxr-xr-x):** Ideal para scripts que deben ser ejecutados por cualquier usuario.
- **644 (rw-r--r--):** Estándar para archivos de configuración que solo el dueño debe editar.
- **600 (rw-------):** Necesario para archivos sensibles como claves privadas SSH.

---

## 2. Gestión de Scripts en Bash
Para asegurar que tus scripts se ejecuten correctamente en cualquier entorno, sigue estas reglas básicas:

1. **Shebang:** Incluye siempre `#!/bin/bash` en la primera línea.
2. **Variables:** Declara variables en mayúsculas para diferenciarlas de los comandos.
3. **Comentarios:** Explica qué hace cada bloque complejo del código.

### Estructura recomendada de un script:
```bash
#!/bin/bash

# VARIABLES
FECHA=$(date +%Y-%m-%d)
DESTINO="/backup"

# CUERPO DEL SCRIPT
echo "Iniciando copia de seguridad el día $FECHA..."
# tar -czf $DESTINO/backup_$FECHA.tar.gz /home/usuario/
```