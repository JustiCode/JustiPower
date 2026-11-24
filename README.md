# JustiPower 2.1.0 — Poderosa plataforma accesible de gestión multimedia

**JustiPower** es un programa portable para Windows, desarrollado por **Mauro Ocampo – JustiCode (drmauroocampo271@gmail.com)**.

Es la evolución de JustiDownloadPRO, un proyecto que inicialmente estuvo orientado a la descarga multimedia y que, mediante sucesivas mejoras e incorporaciones, ha evolucionado hacia una plataforma accesible de reproducción, descarga y gestión de contenido multimedia.

El proyecto nace desde una perspectiva de **accesibilidad universal**, combinando automatización, procesamiento multimedia e integración con diferentes servicios y reproductores, para ofrecer una experiencia sencilla tanto a usuarios de lectores de pantalla como a otros usuarios de Windows.

## 🚀 Características principales

La versión 2.1.0 incorpora nuevas funcionalidades y mejoras en la integración con plataformas multimedia, consolidando la evolución del proyecto hacia una plataforma de gestión multimedia accesible.

Entre sus principales características se incluyen:

* Reproducción multimedia mediante MotorV8.
* Compatibilidad con diferentes reproductores multimedia instalados en Windows.
* Descarga de contenido mediante `yt-dlp`.
* Compatibilidad con YouTube.
* Compatibilidad con SoundCloud.
* Compatibilidad con Bandcamp.
* Compatibilidad con Mixcloud.
* Compatibilidad con Vimeo.
* Compatibilidad con Twitch.
* Compatibilidad con Facebook e Instagram, mediante extractores compatibles.
* Integración con Spotify mediante fallback al navegador.
* Gestión de playlists.
* Selección personalizada de elementos de una playlist.
* Descarga de los elementos seleccionados de una playlist.
* Apertura automática del contenido descargado.
* Selección de formato de descarga.
* Mejoras de accesibilidad mediante teclado.
* Mensajes y avisos mediante síntesis de voz.
* Optimización de la navegación con lectores de pantalla.
* Arquitectura preparada para incorporar nuevos servicios, reproductores y funcionalidades.

---

## 🎵 Integración con Spotify

JustiPower incorpora una integración con **Spotify** que permite acceder a la plataforma y utilizar sus funciones de reproducción mediante el navegador.

A diferencia de otros servicios multimedia, Spotify utiliza mecanismos de protección DRM para proteger sus contenidos.

Por este motivo, `yt-dlp`, la herramienta de extracción multimedia utilizada por el proyecto, no admite la extracción de los flujos protegidos de Spotify.

En el código fuente de `yt-dlp`, el sitio `open.spotify.com` se encuentra incluido en la clase `KnownDRMIE`, dentro del archivo `yt_dlp/extractor/unsupported.py`.

Esta clasificación identifica sitios conocidos por utilizar mecanismos DRM para los cuales la herramienta no ofrece compatibilidad de extracción.

**Código fuente de referencia:**

[yt-dlp — KnownDRMIE (GitHub)](https://github.com/yt-dlp/yt-dlp/blob/master/yt_dlp/extractor/unsupported.py)

Para ofrecer una alternativa de acceso, JustiPower incorpora un mecanismo de **fallback automático al navegador**.

Cuando la ruta de reproducción externa no resulta compatible, el programa recurre al navegador para abrir el reproductor web oficial de Spotify.

De esta manera, el usuario puede acceder a la plataforma e interactuar con sus controles de reproducción desde el flujo de trabajo de JustiPower.

**Limitaciones:**

* La integración no permite descargar contenido protegido por DRM.
* No permite reproducir los flujos protegidos mediante reproductores multimedia externos de Windows.
* La reproducción se realiza mediante el reproductor web oficial de Spotify.
* Las funciones disponibles dependen de las condiciones de acceso de la cuenta y de la compatibilidad del navegador.

---

## 🎵 Compatibilidad con SoundCloud

JustiPower incorpora compatibilidad con **SoundCloud** mediante el sistema de extracción multimedia de `yt-dlp`.

Permite procesar y descargar contenido compatible de la plataforma, incluyendo pistas y otros recursos admitidos por el extractor.

La descarga puede realizarse directamente mediante el atajo correspondiente, agilizando el acceso a esta funcionalidad.

Además, cuando la casilla de reproducción externa se encuentra seleccionada, los archivos descargados pueden abrirse automáticamente con el reproductor multimedia configurado por el usuario en Windows.

**Limitaciones observadas:**

Durante las pruebas realizadas con una cuenta gratuita de SoundCloud, algunos de los archivos obtenidos reprodujeron aproximadamente 29-30 segundos y posteriormente quedaron sin audio.

Este comportamiento se ha observado en los contenidos probados, pero no se ha verificado si afecta a todas las pistas ni si una suscripción de pago modifica las condiciones de descarga mediante `yt-dlp`.

Por este motivo, JustiPower no garantiza que todos los contenidos compatibles puedan obtenerse y reproducirse en su duración completa.

La reproducción externa está disponible para los archivos descargados que contienen audio reproducible.

---

## 📋 Playlists personalizadas

Una de las funcionalidades de JustiPower permite seleccionar individualmente qué elementos de una playlist se desean procesar.

El procedimiento es el siguiente:

1. Seleccionar una playlist.
2. Abrir **Playlist Personalizada**.
3. Marcar los elementos deseados.
4. Confirmar la selección.
5. JustiPower procesa únicamente los elementos seleccionados.

La ventana de selección está diseñada para utilizarse mediante teclado y lectores de pantalla.

También dispone de la opción **Cancelar**, que permite cerrar la ventana sin iniciar ninguna descarga.

---

## ▶️ Reproducción multimedia

JustiPower utiliza **MotorV8** como capa encargada de clasificar las URL y determinar el procedimiento adecuado de reproducción.

El motor puede trabajar con:

* Archivos locales.
* Streams.
* Contenido que requiere extracción multimedia.
* Contenido que debe abrirse mediante navegador.

Cuando existe un archivo multimedia local, Windows puede utilizar la aplicación asociada al tipo de archivo.

Para determinadas reproducciones mediante URL, MotorV8 puede utilizar los reproductores multimedia disponibles en el sistema.

Entre los reproductores contemplados por el proyecto se encuentran:

* PotPlayer.
* VLC.
* Sonarpad.
* MPC-HC.
* MPC-BE.
* MPV.
* GOM Player.

La arquitectura está preparada para continuar ampliando esta compatibilidad.

---

## 📥 Descargas

Las descargas utilizan `yt-dlp` como motor de extracción multimedia.

El proyecto utiliza además herramientas auxiliares como **FFmpeg** y **Deno** cuando son necesarias para determinados procesos de extracción y procesamiento multimedia.

JustiPower genera los archivos temporales en una carpeta propia dentro del directorio temporal de Windows.

La disponibilidad de las descargas depende de las características de cada servicio, sus mecanismos de acceso y los extractores compatibles.

---

## 🎚️ Formatos

La interfaz permite seleccionar diferentes formatos de descarga, entre ellos:

* MP3.
* MP4.
* M4A.
* WAV.

La selección del formato se realiza desde la interfaz de JustiPower.

---

## 🔊 Accesibilidad

JustiPower está diseñado teniendo en cuenta el uso cotidiano con lectores de pantalla.

El programa incorpora:

* Navegación mediante teclado.
* Controles accesibles.
* Mensajes mediante síntesis de voz.
* Cuadros de diálogo accesibles.
* Listas navegables mediante teclado.
* Botones accesibles.
* Selección mediante teclado.
* Confirmaciones y mensajes durante las operaciones principales.

El objetivo es que las funciones principales puedan utilizarse sin depender exclusivamente de una interfaz visual.

La accesibilidad no se considera una función adicional, sino una parte fundamental del diseño del programa.

---

## 🆕 Mejoras de la versión 2.1.0

### Integración con Spotify

* Incorporación de una nueva integración con Spotify.
* Implementación de fallback al navegador.
* Acceso al reproductor web oficial.
* Posibilidad de interactuar con los controles de reproducción de la plataforma.
* Respeto de las restricciones DRM y de las condiciones de acceso establecidas por Spotify.

### SoundCloud

* Mejoras y optimización del funcionamiento del extractor.
* Descargas mediante el atajo correspondiente.
* Reproducción externa de archivos descargados cuando la opción correspondiente está habilitada.
* Apertura mediante el reproductor multimedia configurado por el usuario.

### Continuidad del proyecto

* Evolución de JustiDownloadPRO hacia JustiPower.
* Nueva identidad y nomenclatura del programa.
* Consolidación de su arquitectura como plataforma accesible de gestión multimedia.

---

## 🆕 Características incorporadas en la versión 2.0.0

### Motor multimedia

* Incorporación y evolución de MotorV8.
* Clasificación automática de URL.
* Separación de las rutas de reproducción según el tipo de contenido.
* Compatibilidad con archivos locales, streams, extracción y navegador.
* Preparación para ampliar la compatibilidad con nuevos reproductores.

### Descargas

* Mejor gestión de descargas temporales.
* Integración con FFmpeg.
* Integración con Deno para los procesos compatibles de extracción.
* Mejor gestión de archivos generados.
* Apertura automática del contenido descargado cuando esta opción está habilitada.

### Playlists

* Incorporación de Playlist Personalizada.
* Selección individual de elementos.
* Cancelación de la ventana de selección.
* Procesamiento únicamente de los elementos seleccionados.

### Plataformas

* YouTube.
* SoundCloud.
* Bandcamp.
* Mixcloud.
* Vimeo.
* Twitch.
* Facebook.
* Instagram.
* Spotify mediante integración con navegador.
* Otras fuentes compatibles con `yt-dlp`.

> La compatibilidad concreta de cada sitio depende del extractor disponible en la versión de `yt-dlp` utilizada, ya que los servicios web pueden cambiar sus interfaces y mecanismos de acceso.

---

## ⚙️ Requisitos

* Windows x64.
* Python 3.x durante el desarrollo.
* `yt-dlp`.
* FFmpeg.
* Deno cuando sea requerido por determinados extractores.
* Uno o más reproductores multimedia compatibles para la reproducción externa.

---

## 🧑‍🦯 Diseñado para accesibilidad

JustiPower nace desde una experiencia real de uso con lectores de pantalla.

El proyecto busca facilitar el acceso a herramientas multimedia para:

* Personas con discapacidad visual total o parcial.
* Personas con baja visión.
* Usuarios de NVDA.
* Usuarios de JAWS.
* Usuarios que prefieren trabajar mediante teclado.
* Cualquier persona que valore una interfaz sencilla y accesible.

La accesibilidad universal constituye uno de los pilares fundamentales del proyecto.

---

## 🛠️ Estado del proyecto

JustiPower continúa en desarrollo.

Las futuras versiones podrán incorporar:

* Nuevos servicios multimedia.
* Nuevos reproductores.
* Integración de radios online.
* Mejoras de reproducción.
* Nuevas herramientas para playlists.
* Mejoras de accesibilidad.
* Optimizaciones de rendimiento.
* Nuevas funciones orientadas a la gestión y automatización multimedia.

---

## 👨‍💻 Autor

**Mauro Ocampo – JustiCode**

---

## 📂 Repositorio

**JustiPower — anteriormente JustiDownloadPRO**

https://github.com/JustiCode/JustiPower

---


## 📄 Licencia y condiciones de uso

JustiPower es un software propietario de uso gratuito, desarrollado por Mauro Ocampo – JustiCode.

Se autoriza su descarga, instalación y utilización gratuita, conforme a las condiciones establecidas en el documento **LICENSE.md**.

La autorización de uso no implica la entrega del código fuente ni concede derechos para modificar, adaptar, descompilar, crear versiones derivadas o distribuir versiones modificadas del programa, con las excepciones que establezcan las normas imperativas y las licencias de terceros aplicables.

Se autoriza expresamente compartir gratuitamente copias íntegras y sin modificaciones del programa compilado, tanto por medios digitales como físicos, especialmente para facilitar el acceso a personas con discapacidad visual y a otros usuarios que necesiten asistencia para obtenerlo.

Esta distribución solidaria no podrá realizarse con fines comerciales y deberá conservar los avisos de autoría, identificación y licencia del programa.

Los componentes, herramientas y bibliotecas desarrollados por terceros conservan sus respectivas licencias y condiciones de uso.

**Consulta:** [Licencia propietaria de uso gratuito](LICENSE.md).


---

## 🙏 Agradecimientos

Gracias a todas las personas y compañeros que prueban JustiPower durante sus etapas de contrastación y pruebas beta, informan errores, aportan sugerencias y ayudan a mejorar la accesibilidad del proyecto.

Las pruebas realizadas en diferentes equipos, versiones de Windows, reproductores y configuraciones son fundamentales para detectar problemas de compatibilidad y continuar mejorando el motor multimedia.

---

## ⏳ Historial de versiones

* **Versión 1.0.0:** Primera versión pública.
* **Versión 1.1.0:** Segunda versión pública.
* **Versión 2.0.0:** Tercera versión pública. Evolución hacia una plataforma multimedia con MotorV8, gestión de playlists y compatibilidad con diferentes servicios.
* **Versión 2.1.0:** Nueva identidad JustiPower. Integración con Spotify mediante fallback al navegador y mejoras en SoundCloud.

---

## 🔥 JustiCode

**Accesibilidad, automatización y software pensado para todos y todas.**

¡Que no te digan que no podés!
