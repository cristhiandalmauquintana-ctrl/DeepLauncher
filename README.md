# DeepMovil (launcher de movil para DeepSystemOS)
Proyecto APARTE del OS. Dos partes:

1. `agente-os/` — corre dentro de DeepSystemOS y atiende al movil (WiFi o USB).
2. `android/` — el launcher (app Android en Kotlin, sin librerias externas).

## Instalar el agente en el OS
Copia la carpeta `agente-os` al OS (scp / ssh.sh) y como root:  `sh instalar.sh`
Luego (o al reiniciar el escritorio) corre `deep-enlace`: muestra un PIN de 6 digitos en pantalla.

## Tutorial completo
Mira `TUTORIAL.md` (compilar el APK gratis con GitHub, sin Android Studio).

## Compilar el APK (alternativa)
Android Studio -> Open -> carpeta `android/` -> Build > Build APK(s).
(o en consola, con el SDK: `gradle assembleDebug`). Instala el APK en el movil.
Para usarlo como pantalla de inicio: Ajustes > Apps > Apps predeterminadas > Inicio > DeepMovil.

## Uso
Panel "DeepSystemOS" -> Buscar (o escribe la IP) -> PIN -> Emparejar.
Por USB: activa "Conexion por USB" (tethering) en el movil con el cable puesto; el OS debe ver `usb0`.
Seguridad: PIN de un solo uso, token guardado como hash, bloqueo tras 5 fallos, solo acciones fijas (estado, apps, abrir, apagar).
