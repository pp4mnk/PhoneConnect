# PhoneConnect
**PhoneConnect** is a lightweight utility that allows you to mirror and control your Android smartphone directly from your Linux computer.


Te preparo un **README bilingüe (English / Español)** para publicar en GitHub, con una presentación de PhoneConnect, sus funcionalidades, instalación, instrucciones de uso, dependencias y resolución de problemas.

Está orientado a Puppy Linux, especialmente a F96CE_XFCE_FUSILLI, y a su distribución como paquete `.pet` con las dependencias necesarias incluidas.

He tomado como referencia la versión **2.2**, que incorpora scrcpy 1.12.1 y ADB 8.1.0. No he podido verificar directamente el contenido del paquete PET definitivo, por lo que conviene confirmar las versiones y dependencias antes de publicar.

Puedes copiar directamente este contenido en el archivo `README.md` de GitHub.

# 📱 PhoneConnect — by pp4mnk

**Connect your phone. Control your Android device. Enjoy the freedom of Linux.**



**Version:** 2.2\
**Developer:** pp4mnk\
**Architecture:** x86_64\
**Package format:** PET\
**Platform:** Puppy Linux / F96CE_XFCE_FUSILLI

English | Español

---

# English

## 1. What is PhoneConnect?

PhoneConnect is a lightweight Linux utility that allows you to mirror and control your Android smartphone directly from your computer.

It integrates scrcpy, Android Debug Bridge (ADB), supporting libraries and a dedicated graphical launcher into a convenient installation package.

PhoneConnect has been developed to simplify the connection between Android devices and Puppy Linux computers, avoiding complicated installation procedures and unnecessary manual configuration.

Originally developed for F96CE_XFCE_FUSILLI, the project aims to provide an accessible solution for other compatible Puppy Linux distributions.

## 2. Main features

- Real-time Android screen mirroring.
- Smartphone control using your computer's mouse and keyboard.
- USB connectivity.
- Low latency and responsive interaction.
- Lightweight design.
- Optimized screen resolution and frame rate.
- Desktop menu integration.
- Simple PET package installation.
- No root access required on the Android device.
- No additional application required on the smartphone.
- No Internet connection required during normal USB operation.
- No external account or cloud service required.
- Suitable for older computers with limited hardware resources.

## 3. What is included?

PhoneConnect integrates the following components into a single PET package:

| Component               | Description                                 |
| ----------------------- | ------------------------------------------- |
| scrcpy 1.12.1           | Android screen mirroring and remote control |
| scrcpy-server           | Communication with the Android device       |
| ADB 8.1.0               | Android Debug Bridge                        |
| android-libadb          | ADB supporting library                      |
| android-libbase         | Android base library                        |
| android-libcutils       | Android C utilities                         |
| android-libcrypto-utils | Cryptographic utilities                     |
| android-liblog          | Android logging library                     |
| android-libboringssl    | Cryptographic support                       |
| PhoneConnect launcher   | Simplified application startup              |
| PhoneConnect icon       | Dedicated application artwork               |
| Desktop entry           | Integration into the applications menu      |
| Documentation           | Installation and usage instructions         |

Standard system libraries such as SDL2, FFmpeg and libusb may be required if they are not already available in your Linux distribution.

## 4. System requirements

### Computer

- 64-bit x86_64 processor.
- Puppy Linux or a compatible Linux distribution.
- Available USB port.
- Graphical desktop environment.
- Required system libraries.

### Smartphone

- Android 5.0 or later, subject to device compatibility.
- USB debugging enabled.
- USB data cable.

PhoneConnect does not require a high-performance computer or a dedicated graphics card.

## 5. Installation

1. Download the PhoneConnect PET package from the GitHub Releases section.
2. Locate the downloaded PET file.
3. Double-click the package.
4. Confirm the installation.
5. Wait until the installation is complete.

The included Android components are installed together, reducing the need to search for individual dependencies.

## 6. Preparing your Android smartphone

Before using PhoneConnect for the first time, you must enable USB debugging.

### Enable Developer Options

1. Open **Settings** on your smartphone.
2. Go to **About phone**.
3. Open **Software information**, if available.
4. Locate **Build number**.
5. Tap it seven times.
6. Enter your PIN if requested.

### Enable USB debugging

1. Return to Settings.
2. Open Developer Options.
3. Locate USB debugging.
4. Enable it.
5. Connect your smartphone to the computer using a USB data cable.
6. Unlock your smartphone.
7. Accept the USB debugging authorization request.

You may select **Always allow from this computer** if you trust your computer.

## 7. Starting PhoneConnect

Once installed, open:

**Menu → Accessories → F96CE PhoneConnect — by pp4mnk**

Alternatively, launch it from a terminal:

```
f96ce-phoneconnect
```

Your Android screen should appear in a new window on your Linux desktop.

You can now interact with your smartphone using your computer's mouse and keyboard.

## 8. Default performance settings

PhoneConnect uses optimized scrcpy parameters to reduce resource consumption:

```
scrcpy --max-size 1024 --max-fps 30
```

These settings provide a balance between:

- Image quality.
- Smooth interaction.
- CPU consumption.
- USB bandwidth.
- Compatibility with older computers.

Advanced users can launch scrcpy manually with different parameters.

## 9. Basic controls

| Action          | Control                      |
| --------------- | ---------------------------- |
| Tap the screen  | Left mouse click             |
| Swipe           | Click and drag               |
| Scroll          | Mouse wheel                  |
| Enter text      | Computer keyboard            |
| Android Back    | Right mouse click            |
| Android Home    | Middle mouse click           |
| Close mirroring | Close the application window |

## 10. What can you do with PhoneConnect?

PhoneConnect can be used for many everyday activities:

- Manage your Android applications.
- Read and reply to messages.
- Browse websites.
- Access photographs and documents through Android applications.
- Manage smartphone settings.
- Demonstrate Android applications.
- Display your smartphone on a larger screen.
- Create tutorials and presentations.
- Interact with your smartphone without constantly picking it up.

Some protected applications may prevent their content from being mirrored.

## 11. Privacy and security

PhoneConnect establishes a direct connection between your Android device and your computer through ADB.

Normal USB operation does not require an external server, cloud account or Internet connection.

Only authorize USB debugging on computers you trust.

When using a public or shared computer, disable USB debugging or revoke debugging authorizations after use.

## 12. Troubleshooting

### My smartphone is not detected

Check that:

- USB debugging is enabled.
- The smartphone is unlocked.
- The USB cable supports data transfer.
- The debugging authorization has been accepted.

Run:

```
adb devices
```

### The device appears as unauthorized

Unlock your smartphone and accept the USB debugging authorization request.

If necessary, disconnect and reconnect the USB cable.

### ADB does not respond

Restart the ADB server:

```
adb kill-server
adb start-server
adb devices
```

### PhoneConnect does not start

Launch the application from a terminal:

```
f96ce-phoneconnect
```

Check the output for missing libraries or other error messages.

### The connection is slow

Try reducing the screen resolution and frame rate:

```
scrcpy --max-size 800 --max-fps 20
```

### A missing shared library is reported

Check the required libraries using:

```
ldd "$(command -v scrcpy)"
ldd "$(command -v adb)"
```

Any library marked as **not found** must be installed or made available to the application.

## 13. Uninstallation

Open Puppy Package Manager, locate the installed PhoneConnect package and select the uninstall option.

To remove the computer's authorization from your smartphone, use the **Revoke USB debugging authorizations** option in Android Developer Options.

## 14. Compatibility

PhoneConnect has been developed primarily for F96CE_XFCE_FUSILLI.

Potential compatibility includes:

- FossaPup64.
- Other compatible 64-bit Puppy Linux distributions.
- Other Linux distributions with suitable libraries.

Compatibility with every Puppy Linux version is not guaranteed.

## 15. Project philosophy

PhoneConnect follows a simple philosophy:

**Make technology useful, lightweight and accessible.**

The aim is to simplify existing technologies and make them available to users who do not want to spend time installing multiple packages, searching for dependencies or configuring complex tools.

Linux should be powerful without necessarily being complicated.

## 16. Credits and licensing

PhoneConnect integration, packaging, launcher and artwork:

**pp4mnk**

Underlying technologies:

- [scrcpy — Genymobile](https://github.com/Genymobile/scrcpy)
- [Android Debug Bridge — Android Open Source Project](https://developer.android.com/tools/adb)
- [SDL](https://www.libsdl.org/)
- [FFmpeg](https://ffmpeg.org/)
- [libusb](https://libusb.info/)

Third-party components remain subject to their respective licenses.

PhoneConnect is an independent integration project and is not officially affiliated with Google, Android or Genymobile.

## 17. Contributions and feedback

Suggestions, bug reports, compatibility reports and improvements are welcome.

When reporting an issue, please include:

- Linux distribution and version.
- PhoneConnect version.
- Android version.
- Smartphone model.
- Relevant terminal output.

16. License, copyright and credits

GNU General Public License v3.0

PhoneConnect — by pp4mnk is free and open-source software released under the GNU General Public License version 3 (GPL-3.0-only).

Copyright © 2026 pp4mnk.

What this license allows

Commercial use: You may use PhoneConnect for personal, educational or commercial purposes.

Modification: You may study, modify and improve the source code.

Distribution: You may freely distribute original or modified versions.

Private use: You may use and modify the software privately.

Patent protection: The license includes explicit patent provisions.

License conditions

Preserve the original copyright and license notices.

Provide a copy of the GPL-3.0 license when redistributing the software.

Make the corresponding source code available when distributing binaries, in accordance with the GPL.

Distribute derivative works covered by the GPL under the same license.

Clearly indicate significant modifications and their dates.

Disclaimer

PhoneConnect is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY, including implied warranties of merchantability or fitness for a particular purpose.

The developer shall not be held liable for damages arising from the use of this software, except where applicable law provides otherwise.

Third-party software and credits

PhoneConnect integrates existing open-source technologies:

PhoneConnect: Integration, packaging, launcher and artwork by pp4mnk.

scrcpy: Developed by Genymobile, licensed under Apache License 2.0.

ADB: Android Debug Bridge, developed as part of the Android Open Source Project.

Android supporting libraries: Distributed under their respective upstream licenses.

SDL, FFmpeg and libusb: Subject to their respective licenses and distribution conditions.

Third-party components retain their original copyrights and licenses.

PhoneConnect is an independent project and is not officially affiliated with Google, Android or Genymobile.

Official license

License: GNU GPL v3.0

SPDX identifier: GPL-3.0-only

Full license: https://www.gnu.org/licenses/gpl-3.0.html
---

# Español

## 1. ¿Qué es PhoneConnect?

PhoneConnect es una aplicación ligera para Linux que permite visualizar y controlar un teléfono Android directamente desde el ordenador.

Integra scrcpy, Android Debug Bridge (ADB), bibliotecas auxiliares y un lanzador propio en un único paquete de instalación.

PhoneConnect ha sido desarrollado para simplificar la conexión entre dispositivos Android y ordenadores con Puppy Linux, evitando instalaciones complicadas y configuraciones manuales innecesarias.

Desarrollado originalmente para F96CE_XFCE_FUSILLI, el proyecto pretende ofrecer una solución accesible para otras distribuciones compatibles de Puppy Linux.

## 2. Características principales

- Visualización de la pantalla de Android en tiempo real.
- Control del teléfono mediante el ratón y el teclado del ordenador.
- Conexión mediante USB.
- Baja latencia y respuesta fluida.
- Diseño ligero.
- Resolución y frecuencia de imagen optimizadas.
- Integración en el menú de aplicaciones.
- Instalación sencilla mediante un paquete PET.
- No requiere acceso root en Android.
- No requiere instalar aplicaciones adicionales en el teléfono.
- No necesita Internet durante el funcionamiento normal por USB.
- No requiere cuentas externas ni servicios en la nube.
- Adecuado para ordenadores antiguos o con recursos limitados.

## 3. ¿Qué incluye PhoneConnect?

| Componente              | Descripción                             |
| ----------------------- | --------------------------------------- |
| scrcpy 1.12.1           | Visualización y control de Android      |
| scrcpy-server           | Comunicación con el dispositivo Android |
| ADB 8.1.0               | Android Debug Bridge                    |
| android-libadb          | Biblioteca auxiliar de ADB              |
| android-libbase         | Biblioteca base de Android              |
| android-libcutils       | Utilidades C de Android                 |
| android-libcrypto-utils | Utilidades criptográficas               |
| android-liblog          | Biblioteca de registros de Android      |
| android-libboringssl    | Soporte criptográfico                   |
| Lanzador PhoneConnect   | Inicio simplificado de la aplicación    |
| Icono PhoneConnect      | Identidad gráfica propia                |
| Entrada de escritorio   | Integración en el menú de aplicaciones  |
| Documentación           | Instrucciones de instalación y uso      |

Las bibliotecas generales del sistema, como SDL2, FFmpeg y libusb, pueden ser necesarias si no están disponibles previamente en la distribución utilizada.

## 4. Requisitos del sistema

### Ordenador

- Procesador de 64 bits x86_64.
- Puppy Linux o distribución Linux compatible.
- Puerto USB disponible.
- Entorno gráfico de escritorio.
- Bibliotecas del sistema necesarias.

### Teléfono móvil

- Android 5.0 o superior, sujeto a compatibilidad.
- Depuración USB activada.
- Cable USB con capacidad de transferencia de datos.

PhoneConnect no necesita un ordenador de altas prestaciones ni una tarjeta gráfica dedicada.

## 5. Instalación

1. Descarga el paquete PET de PhoneConnect desde la sección Releases de GitHub.
2. Localiza el archivo descargado.
3. Haz doble clic sobre él.
4. Confirma la instalación.
5. Espera a que finalice el proceso.

Los componentes de Android incluidos se instalan conjuntamente, reduciendo la necesidad de buscar dependencias individuales.

## 6. Preparación del teléfono Android

Antes de utilizar PhoneConnect por primera vez, es necesario activar la depuración USB.

### Activar las opciones de desarrollador

1. Abre los ajustes del teléfono.
2. Accede a Acerca del teléfono.
3. Entra en Información de software, si aparece esta opción.
4. Localiza Número de compilación.
5. Pulsa siete veces sobre él.
6. Introduce tu PIN si se solicita.

### Activar la depuración USB

1. Regresa a los ajustes.
2. Abre Opciones de desarrollador.
3. Localiza Depuración USB.
4. Actívala.
5. Conecta el teléfono al ordenador mediante un cable USB de datos.
6. Desbloquea el teléfono.
7. Acepta la solicitud de autorización de depuración USB.

Puedes marcar **Permitir siempre desde este ordenador** si se trata de un equipo de confianza.

## 7. Ejecutar PhoneConnect

Una vez instalado, accede a:

**Menú → Accesorios → F96CE PhoneConnect — by pp4mnk**

También puedes ejecutarlo desde una terminal:

```
f96ce-phoneconnect
```

La pantalla del teléfono aparecerá en una nueva ventana del escritorio Linux.

A partir de ese momento, podrás controlar el dispositivo utilizando el ratón y el teclado del ordenador.

## 8. Configuración de rendimiento

PhoneConnect utiliza parámetros optimizados para reducir el consumo de recursos:

```
scrcpy --max-size 1024 --max-fps 30
```

Esta configuración busca un equilibrio entre:

- Calidad de imagen.
- Fluidez.
- Consumo de procesador.
- Ancho de banda USB.
- Compatibilidad con ordenadores antiguos.

Los usuarios avanzados pueden ejecutar scrcpy directamente con otros parámetros.

## 9. Controles básicos

| Acción                     | Control                   |
| -------------------------- | ------------------------- |
| Pulsar sobre la pantalla   | Botón izquierdo del ratón |
| Deslizar                   | Pulsar y arrastrar        |
| Desplazarse                | Rueda del ratón           |
| Escribir texto             | Teclado del ordenador     |
| Retroceder                 | Botón derecho del ratón   |
| Inicio de Android          | Botón central del ratón   |
| Finalizar la visualización | Cerrar la ventana         |

## 10. ¿Qué puedes hacer con PhoneConnect?

- Utilizar las aplicaciones del teléfono.
- Leer y responder mensajes.
- Navegar por Internet.
- Consultar fotografías y documentos mediante las aplicaciones de Android.
- Modificar los ajustes del teléfono.
- Realizar demostraciones de aplicaciones.
- Visualizar el teléfono en una pantalla de mayor tamaño.
- Crear tutoriales y presentaciones.
- Utilizar el móvil sin tener que cogerlo constantemente.

Algunas aplicaciones con contenido protegido pueden impedir la visualización de su pantalla.

## 11. Privacidad y seguridad

PhoneConnect establece una conexión directa entre el dispositivo Android y el ordenador mediante ADB.

El funcionamiento normal mediante USB no requiere servidores externos, cuentas en la nube ni conexión a Internet.

Autoriza la depuración USB únicamente en ordenadores de confianza.

Si utilizas un ordenador público o compartido, desactiva la depuración USB o revoca las autorizaciones cuando termines.

## 12. Solución de problemas

### El teléfono no aparece

Comprueba que:

- La depuración USB está activada.
- El teléfono está desbloqueado.
- El cable USB permite transferir datos.
- Has aceptado la autorización de depuración USB.

Ejecuta:

```
adb devices
```

### El dispositivo aparece como unauthorized

Desbloquea el teléfono y acepta la solicitud de autorización.

Si es necesario, desconecta y vuelve a conectar el cable USB.

### ADB no responde

Reinicia el servidor ADB:

```
adb kill-server
adb start-server
adb devices
```

### PhoneConnect no se inicia

Ejecuta el programa desde una terminal:

```
f96ce-phoneconnect
```

Comprueba si aparecen errores relacionados con bibliotecas o dependencias.

### La conexión es lenta

Reduce la resolución y la frecuencia de imagen:

```
scrcpy --max-size 800 --max-fps 20
```

### Falta alguna biblioteca

Comprueba las dependencias mediante:

```
ldd "$(command -v scrcpy)"
ldd "$(command -v adb)"
```

Las bibliotecas que aparezcan como **not found** deberán instalarse o ponerse a disposición del programa.

## 13. Desinstalación

Abre Puppy Package Manager, localiza el paquete PhoneConnect instalado y selecciona la opción de desinstalación.

Si deseas eliminar la autorización del ordenador en el teléfono, utiliza la opción **Revocar autorizaciones de depuración USB** de Android.

## 14. Compatibilidad

PhoneConnect ha sido desarrollado principalmente para F96CE_XFCE_FUSILLI.

Puede funcionar también en:

- FossaPup64.
- Otras distribuciones compatibles de Puppy Linux de 64 bits.
- Otras distribuciones Linux que dispongan de las bibliotecas necesarias.

No se garantiza la compatibilidad con todas las versiones de Puppy Linux.

## 15. Filosofía del proyecto

PhoneConnect sigue una filosofía sencilla:

**Hacer que la tecnología sea útil, ligera y accesible.**

El objetivo es simplificar tecnologías existentes y ponerlas al alcance de usuarios que no desean invertir tiempo instalando múltiples paquetes, buscando dependencias o configurando herramientas complejas.

Linux debe ser potente sin necesidad de ser complicado.

## 16. Créditos y licencias

Integración, empaquetado, lanzador e identidad gráfica de PhoneConnect:

**pp4mnk**

Tecnologías utilizadas:

- [scrcpy — Genymobile](https://github.com/Genymobile/scrcpy)
- [Android Debug Bridge — Android Open Source Project](https://developer.android.com/tools/adb)
- [SDL](https://www.libsdl.org/)
- [FFmpeg](https://ffmpeg.org/)
- [libusb](https://libusb.info/)

Los componentes de terceros conservan sus respectivas licencias.

PhoneConnect es un proyecto de integración independiente y no está afiliado oficialmente a Google, Android ni Genymobile.

## 17. Colaboraciones y sugerencias

Todas las sugerencias, informes de errores, pruebas de compatibilidad y propuestas de mejora son bienvenidas.

Al comunicar un problema, incluye:

- Distribución Linux y versión.
- Versión de PhoneConnect.
- Versión de Android.
- Modelo del teléfono.
- Mensajes relevantes de la terminal.

Elimina cualquier información sensible antes de publicar los resultados.

---

**PhoneConnect — by pp4mnk**

*Your phone. Your computer. One connection.*

*Tu teléfono. Tu ordenador. Una conexión.*

🐧 **Made for Linux. Built for simplicity.**

## **Recomendaciones para el repositorio de GitHub**

Utilizaría esta estructura:

```
PhoneConnect/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── phoneconnect.png
├── screenshots/
├── packages/
│   └── PhoneConnect-2.2-x86_64.pet
└── src/
    └── launcher/
```

Guarda el logotipo que hemos creado con el nombre `phoneconnect.png` en la raíz del repositorio para que aparezca automáticamente en el README.

**Descripción breve para GitHub:**

> A lightweight Android screen mirroring and control utility for Puppy Linux, integrating scrcpy and ADB into an easy-to-install PET package. Developed by pp4mnk.

**Topics de GitHub:**

`puppylinux` `android` `scrcpy` `adb` `linux` `phoneconnect` `pp4mnk` `xfce` `screen-mirroring` `f96ce` `fusilli` `pet-package`

![License](https://img.shields.io/badge/License-GPLv3-green.svg)
![Open Source](https://img.shields.io/badge/Open_Source-Yes-blue.svg)
![Linux](https://img.shields.io/badge/Platform-Linux-orange.svg)
![Architecture](https://img.shields.io/badge/Architecture-x86__64-lightgrey.svg)
![Android](https://img.shields.io/badge/Android-Compatible-green.svg)
![Developer](https://img.shields.io/badge/Developer-pp4mnk-blue.svg)

