# Tutorial: de cero a tener DeepMovil en tu telefono

## Parte A - Conseguir el APK (sin instalar Android Studio)
Android Studio pesa varios GB y tu Chromebook tiene poco espacio, asi que lo compila GitHub gratis.
1. Crea un repositorio NUEVO en github.com (por ejemplo `deepmovil`, privado esta bien).
2. Sube TODO el contenido de esta carpeta (incluida la carpeta oculta `.github`):
   en el repo -> "Add file" -> "Upload files" -> arrastra `android`, `agente-os`, `.github`, etc. -> Commit.
   (Si no ves `.github` en tu carpeta, activa "Mostrar archivos ocultos" en la app Archivos.)
3. Pestana **Actions** -> "Compilar APK" -> espera 3-5 min a que salga el check verde.
   Si sale en rojo, abre el paso que fallo y mandame el texto del error.
4. Entra a esa ejecucion -> abajo en **Artifacts** -> descarga `DeepMovil-apk` (es un zip con `app-debug.apk`).

## Parte B - Instalarlo en el telefono
1. Pasa `app-debug.apk` al telefono (Drive, cable o correo).
2. Abrelo; Android pedira permitir "instalar apps desconocidas" para esa app (Archivos/Chrome). Aceptalo.
3. Ajustes > Apps > Apps predeterminadas > App de inicio > **DeepMovil**.
   (Para volver al launcher normal, cambialo de nuevo aqui.)

## Parte C - Agente dentro de DeepSystemOS
1. Abre una terminal en DeepSystemOS (root). Copia la carpeta `agente-os` adentro:
   desde la Chromebook: `scp -P 2222 -i cache/id_deep -r agente-os root@localhost:/root/` (o con ./ssh.sh).
2. Dentro del OS: `cd /root/agente-os && sh instalar.sh && deep-enlace &`
   Sale una ventana con un PIN de 6 digitos.

## Parte D - Enlazar
- **WiFi:** telefono y OS en la misma red. OJO: la VM en la Chromebook usa red NAT y el telefono no la ve;
  por WiFi funciona con DeepSystemOS instalado en la PC real.
- **USB (para la VM o la PC real):** conecta el cable, activa "Conexion por USB" en el telefono y pasa el telefono a la VM (./telefono.sh).
- En la app: DeepSystemOS -> **Buscar** -> escribe el PIN -> **Emparejar**.

## Si usas Android Studio (opcional)
Existe version para Chromebook: se instala dentro de Linux (descargas el .tar.gz de developer.android.com/studio y lo descomprimes).
Necesita mucho espacio y RAM; con 30 GB no lo recomiendo. Open -> carpeta `android/` -> Build > Build APK(s).
