# Forma Studio Android — versione 3.7.0

Progetto Android Studio che integra Forma Studio 3.7 in una WebView locale. L'app non richiede connessione Internet per usare il generatore.

## Funzioni Android integrate
- File HTML incluso in `app/src/main/assets/index.html`.
- Esportazione di STL ASCII, STL binario, OBJ, 3MF e JSON nella cartella `Download/Forma Studio`.
- Apertura di progetti JSON tramite selettore documenti Android.
- Nessun permesso Internet richiesto.

## Compilazione APK
1. Aprire la cartella `forma-studio-android` con Android Studio.
2. Installare Android SDK Platform 35 e una versione compatibile di Android Gradle Plugin.
3. Attendere la sincronizzazione Gradle.
4. Selezionare **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. APK debug atteso: `app/build/outputs/apk/debug/app-debug.apk`.

## Note
Il codice sorgente è predisposto per Android Studio, ma il file APK non è incluso in questo archivio: nell'ambiente di creazione non è installato Android SDK/Gradle, quindi non è stato possibile compilare e verificare un APK. Eseguire un test sul dispositivo per verificare esportazioni e caricamento file prima di distribuirlo.

## Compilazione automatica APK (senza Android Studio locale)

Il repository include `.github/workflows/android-apk.yml`. Dopo aver caricato il progetto in un repository GitHub, aprire **Actions > Build Forma Studio APK** e avviare `Run workflow`. Il job installa Java/Android SDK, compila `assembleDebug` e pubblica `forma-studio-debug-apk` come artifact scaricabile per 14 giorni. Il workflow non firma una release per il Play Store: produce un APK debug per test e installazione manuale.

Nota: il progetto è stato preparato ma, in questo ambiente, non è stato possibile eseguire la compilazione perché Android SDK/Gradle non sono installati e l'accesso di rete per scaricarli non è disponibile. Il workflow va eseguito su GitHub per ottenere il binario e verificare la build.
