<p align="center">
  <img src="./assets/icon.svg" width="132" alt="Cyb3rmeth0d" />
</p>

<h1 align="center">PS5 WebKit Autoloader · V.1b</h1>

<p align="center">
  <b>Instalador ELF By Cyb3rmeth0d</b><br>
  Instala, actualiza y repara la aplicación <b>WebKit Autoloader</b> en PS5.
</p>

<p align="center">
  <img alt="Versión" src="https://img.shields.io/badge/versi%C3%B3n-V.1b-51f5ff?style=flat-square">
  <img alt="Plataforma" src="https://img.shields.io/badge/plataforma-PS5-168dff?style=flat-square">
  <img alt="Firmware" src="https://img.shields.io/badge/firmware-7.00--13.60-8a5bdf?style=flat-square">
  <img alt="Licencia" src="https://img.shields.io/badge/licencia-GPL--3.0-69ffd5?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/Cyb3rMeth0d?tab=repositories"><b>Descargar · Repositorios de Cyb3rMeth0d</b></a>
</p>

---

## Descripción

`webkit-autoloader-installer_v1b.elf` es el instalador de **WebKit Autoloader**.

Se envía a la PS5 como un payload ELF normal y se encarga de cachear la página
del autoloader, crear el acceso directo en la pantalla de inicio y configurar
el icono de la aplicación.

Una vez completada la instalación, la app funciona de forma **offline**: no
necesita PC, DNS externos ni conexión a Internet.

> Este README está centrado únicamente en el instalador ELF. No cubre el host
> para PC ni la carpeta de payloads para USB.

---

## Características

- **Instalación automática:** cachea todo el contenido y crea la app sin pasos
  manuales adicionales.
- **Diseño nuevo:** interfaz oscura con neón, panel de estado en vivo, barra de
  progreso y tarjetas informativas.
- **Interfaz en español:** estados, errores, reparación y mensajes de progreso.
- **Logo e icono personalizados:** el logo de Cyb3rmeth0d se usa en el
  instalador y como icono de la app en la PS5.
- **Caché offline:** la app queda guardada en la consola y funciona sin red.
- **Reparación integrada:** si detecta una caché dañada, ofrece borrar los
  datos de WebKit y reintentar.
- **Selección automática de exploit:** elige Poops o Relapse según el firmware
  y el estado de la red.
- **Sin dependencias externas:** todo lo necesario va dentro del ELF.

---

## Datos del archivo

| Dato | Valor |
|---|---|
| Archivo | `webkit-autoloader-installer_v1b.elf` |
| Versión | `1b` |
| Autor | Cyb3rmeth0d |
| Title ID | `CYBR00001` |
| Nombre de la app | WebKit Autoloader V.1b By Cyb3rmeth0d |
| Firmware soportado | PS5 7.00 – 13.60 |
| Requiere | PS5 ya jailbroken + `elfldr` o Payload Manager |
| SHA256 | `d130aa0b0f3a12b106ccdcf6ccd398f1bf93bcc2579513d8fac7e784a32a1231` |

---

## Requisitos

- PS5 con firmware **7.00 – 13.60**.
- Consola **ya jailbroken**.
- Un loader para enviar el ELF:
  - `elfldr`, o
  - Payload Manager, o
  - cualquier otro loader compatible con payloads `.elf`.

> **Importante:** este ELF no sirve para la primera instalación en una consola
> sin jailbreak. En ese caso hace falta ejecutar primero el exploit WebKit desde
> el host del PC.

---

## Instalación

1. Descarga `webkit-autoloader-installer_v1b.elf`.
2. Envía el archivo a la PS5 con `elfldr` o desde Payload Manager.
3. El instalador abrirá el navegador y comenzará a cachear el contenido.
4. Espera a que la barra de progreso llegue al 100 % y aparezca
   **Instalación completada**.
5. **Reinicia la PS5 una vez.**
6. Abre **WebKit Autoloader** desde la pantalla de inicio.

No hace falta PC ni Internet después de la instalación.

---

## Instalación desde Payload Manager (con logo)

Payload Manager solo muestra un icono cuando el payload se instala desde un
repositorio que publica un catálogo de iconos. Este proyecto incluye
`pldmgr-repo/` con `repo.json` e `icons.json` listos para publicar.

1. Publica la carpeta `pldmgr-repo/` en una URL **HTTPS** pública.
2. En la PS5 abre **Ajustes → Repositorios** y añade la URL de `repo.json`.
3. Comprueba que **Ajustes → Iconos de payloads en el panel** está activado.
4. Ve a **Get Payloads → Cyb3rmeth0d - WebKit Autoloader** e instala el
   payload desde ahí.
5. Si ya lo tenías instalado desde USB o subido a mano, bórralo y vuelve a
   instalarlo desde el repositorio.

Las copias en USB y los ELF subidos manualmente seguirán mostrando el icono
genérico: Payload Manager no lee el `icon0.png` de la app instalada ni el
icono incrustado en el ELF.

---

## Qué hace el instalador

1. Comprueba la versión de firmware y el estado de la caché.
2. Arranca un servidor HTTP temporal en la consola.
3. Abre el navegador para descargar y guardar la página del autoloader.
4. Valida que la caché esté completa antes de continuar.
5. Instala el icono de la app (`icon0.png`, 512×512).
6. Registra la app con el Title ID `CYBR00001`.
7. Crea el acceso directo **WebKit Autoloader** en la pantalla de inicio.
8. Se cierra automáticamente al terminar.

Si la caché ya existe y está completa, el instalador la reutiliza y
simplemente recrea el acceso directo.

---

## Firmware compatible

| Firmware | Exploit |
|---|---|
| 7.00 – 9.04 | Poops o Relapse según red |
| 9.05 | Poops |
| 9.06 – 12.00 | Poops o Relapse según red |
| 12.02 – 13.60 | Relapse |

Fuera de **7.00 – 13.60** el instalador muestra `Firmware no compatible` y no
cachea nada.

---

## Actualizar o reparar

Para actualizar o reparar la app, envía de nuevo este mismo ELF:

1. Envía `webkit-autoloader-installer_v1b.elf` a la PS5.
2. Espera a que termine el cacheo.
3. Reinicia la consola.
4. Abre **WebKit Autoloader** desde la pantalla de inicio.

Tus payloads y configuraciones externas no se modifican.

---

## Solución de problemas

### La instalación no termina

- Mantén la página abierta hasta que aparezca **Instalación completada**.
- Vuelve a enviar el ELF y espera de nuevo.
- Si el problema continúa, usa la opción de borrar los datos de WebKit que
  ofrece el propio instalador cuando detecta una caché dañada.

### La app no aparece en la pantalla de inicio

- Asegúrate de haber reiniciado la PS5 después de la instalación.
- Vuelve a enviar el ELF y deja que termine el proceso.
- Comprueba que estás en un firmware soportado.

### Sigue apareciendo la app antigua

Esta build usa el Title ID `CYBR00001`, distinto del de versiones anteriores.
Puedes borrar la app vieja desde la pantalla de inicio de la PS5.

### El navegador muestra un error

- Vuelve a ejecutar el instalador.
- Si el error ocurre durante la descarga, usa la opción de borrar los datos
  de WebKit que ofrece la propia página.
- Verifica que el ELF se haya enviado completo y no esté corrupto.

### La consola se queda en la pantalla de carga

- Comprueba que el firmware esté entre 7.00 y 13.60.
- Reinicia la PS5 y vuelve a lanzar el instalador.
- No cierres el navegador mientras la barra de progreso está avanzando.

---

## Verificar el archivo

**Windows (PowerShell):**

```powershell
Get-FileHash .\webkit-autoloader-installer_v1b.elf -Algorithm SHA256
```

**Linux / macOS:**

```bash
sha256sum webkit-autoloader-installer_v1b.elf
```

Debe devolver:

```text
d130aa0b0f3a12b106ccdcf6ccd398f1bf93bcc2579513d8fac7e784a32a1231
```

---

## Notas

- Este archivo es un **payload ELF**, no un homebrew firmado.
- No lo renombres a `eboot.bin` ni intentes instalarlo como una app normal.
- El instalador está pensado para ejecutarse desde un loader en una consola
  ya jailbroken.
- La app instalada funciona de forma offline una vez completado el cacheo.
- La interfaz del instalador está en español.
- El icono `icon0.png` se genera desde `assets/icon.svg` y se incrusta en el
  ELF durante la compilación.

---

## Créditos

- **Cyb3rmeth0d** — rebranding, diseño del instalador, logo e icono.
- **jordyidk** y colaboradores — [slopkit (Poops)](https://github.com/jordyidk/slopkit).
- **soniciso1**, **ntfargo** y colaboradores — [Relapse](https://github.com/soniciso1/relapse).
- **notmaj0r** — [porte Lua de Relapse](https://github.com/notmaj0r/remote_lua_loader).
- **john-tornblom** — [ps5-payload-sdk](https://github.com/ps5-payload-dev/sdk/) y [elfldr](https://github.com/ps5-payload-dev/elfldr).
- Proyecto base `ps5-webkit-remote-loader` y comunidad homebrew de PS5.

---

## Licencia

GPL-3.0. Consulta el archivo `LICENSE` del proyecto.

---

## Aviso

Herramienta para investigación y desarrollo. Úsala bajo tu responsabilidad.
El autor no se hace responsable de daños, pérdida de datos o bloqueos
derivados de su uso.