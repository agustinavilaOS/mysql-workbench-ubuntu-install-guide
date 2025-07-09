---

# 🚀 Instalación de MySQL Workbench desde archivo `.deb` en Ubuntu 24.04

Esta guía explica cómo instalar la versión más reciente de **MySQL Workbench** en Ubuntu 24.04 utilizando el paquete `.deb` oficial descargado manualmente desde el sitio de MySQL.

---

## 1. Descargar el paquete `.deb` oficial

- Accede a la página de descargas de MySQL Workbench:  
  [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)

- Descarga el archivo que corresponda a tu versión de Ubuntu (ejemplo para Ubuntu 24.04):
```
mysql-workbench-community_8.0.42-1ubuntu24.04_amd64.deb
````

---

## 2. Instalar el paquete `.deb` manualmente

Abre una terminal, navega a la carpeta donde descargaste el archivo y ejecuta:

```bash
sudo dpkg -i mysql-workbench-community_8.0.42-1ubuntu24.04_amd64.deb
````

> **Nota:**
> Si tu archivo tiene otro nombre o versión, ajústalo en el comando.

---

## 3. Resolver dependencias automáticamente

Si aparecen errores de dependencias, ejecuta:

```bash
sudo apt --fix-broken install
```

Esto instalará automáticamente los paquetes adicionales requeridos.

---

## 4. Verificar la instalación

Para iniciar MySQL Workbench, puedes buscarlo en el menú de aplicaciones o desde terminal:

```bash
mysql-workbench
```

---

## Notas importantes

* Si tu versión de Ubuntu no está soportada oficialmente, intenta descargar el `.deb` más cercano a tu versión (por ejemplo, para Ubuntu 22.04 o 20.04).
* Si alguna dependencia no se resuelve automáticamente, instálala manualmente con `sudo apt install nombre-paquete`.
* Para desinstalar:

  ```bash
  sudo apt remove mysql-workbench-community
  ```

---

## Referencias

* [Documentación oficial MySQL Workbench](https://dev.mysql.com/doc/workbench/en/)
* [Página oficial de descargas](https://dev.mysql.com/downloads/workbench/)

---

```
