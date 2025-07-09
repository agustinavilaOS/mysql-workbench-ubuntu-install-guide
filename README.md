---

# 🐬 Manual de Instalación y Configuración Segura de MySQL Server + Workbench en Ubuntu 24.04

Este manual describe el procedimiento recomendado para instalar MySQL Server y MySQL Workbench en Ubuntu 24.04, incluyendo prácticas de seguridad esenciales.  
Ideal para administradores, desarrolladores y equipos de TI que requieren una guía clara y profesional.

---

## 🔄 1. Actualiza el sistema

Siempre inicia asegurando que tu sistema tiene la última información de paquetes:

```bash
sudo apt update
sudo apt upgrade -y
````

---

## 🛠️ 2. Instala MySQL Server

Instala el motor de base de datos MySQL:

```bash
sudo apt install mysql-server -y
```

* **Nota:** Durante la instalación puede solicitarte definir una contraseña para el usuario `root` de MySQL. Usa una contraseña fuerte y guárdala en un lugar seguro.

---

## 🛡️ 3. Refuerza la seguridad de MySQL Server

Ejecuta el script de seguridad oficial:

```bash
sudo mysql_secure_installation
```

### Recomendaciones para las preguntas del script:

* **¿Configurar el componente de validación de contraseñas?**
  Responde `Y` y selecciona el nivel `2 (STRONG)` para máxima seguridad.
* **¿Cambiar la contraseña de root?**
  Si ya la estableciste antes, puedes volver a cambiarla aquí.
* **¿Eliminar usuarios anónimos?**
  `Y`
* **¿Deshabilitar login remoto para root?**
  `Y` (Recomendado)
* **¿Eliminar la base de datos de pruebas?**
  `Y`
* **¿Recargar tablas de privilegios?**
  `Y`

---

## 🔍 4. Verifica el estado de MySQL Server

Asegúrate de que el servicio esté corriendo:

```bash
systemctl status mysql
```

Deberías ver `active (running)`.
Presiona `q` para salir.

---

## 💻 5. Instala MySQL Workbench (GUI oficial) desde .deb

### 5.1 ⬇️ Descarga el paquete `.deb` más reciente para Ubuntu 24.04 desde el sitio oficial:

* [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)
* Ejemplo de archivo:
  `mysql-workbench-community_8.0.42-1ubuntu24.04_amd64.deb`

### 5.2 📨 Instala el paquete descargado

Navega al directorio de descargas y ejecuta:

```bash
sudo dpkg -i mysql-workbench-community_8.0.42-1ubuntu24.04_amd64.deb
```

### 5.3 🧩 Corrige e instala las dependencias necesarias

Si aparecen errores de dependencias, ejecuta:

```bash
sudo apt --fix-broken install
```

Esto instalará todas las librerías requeridas automáticamente.

---

## 🚀 6. Accede a MySQL Workbench

* Busca “MySQL Workbench” en el menú de aplicaciones o ejecuta:

  ```bash
  mysql-workbench
  ```

* Crea una nueva conexión usando:

  * Host: `localhost`
  * Usuario: `root`
  * Contraseña: la que definiste
  * Puerto: `3306` (por defecto)

---

## 🗂️ 7. Crea tu primera base de datos (schema)

1. Conéctate con tu usuario root.
2. Haz clic derecho en el área **SCHEMAS** y selecciona **Create Schema...**
3. Ingresa el nombre de la base de datos y da clic en **Apply**.

---

## 📝 8. Buenas prácticas adicionales

* **No uses root para tus aplicaciones:**
  Crea un usuario adicional con solo los permisos necesarios.
* **Haz respaldos periódicos** y guarda las contraseñas en un gestor seguro.
* **Actualiza regularmente** tu servidor y tus herramientas.

---

## 📚 9. Referencias

* [Documentación oficial MySQL Workbench](https://dev.mysql.com/doc/workbench/en/)
* [Guía de instalación MySQL en Ubuntu](https://dev.mysql.com/doc/refman/8.0/en/linux-installation.html)
* [Descarga oficial Workbench](https://dev.mysql.com/downloads/workbench/)

---

## 🤝 🟢 Soporte

¿Tienes dudas o problemas en el proceso?
Abre un issue en este repositorio o contacta a tu área de infraestructura.

---
