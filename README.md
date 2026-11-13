# MusicPilot AI 0.6 – Audio-Fix für iPhone Safari

## Installation auf GitHub

1. Vorherige `index.html` und `sw.js` durch die Dateien aus diesem Paket ersetzen (im GitHub-Repository auf die Datei tippen, oben den Stift **Edit** wählen und ersetzen; alternativ Dateien via **Add file → Upload files** hochladen und vorhandene Dateien überschreiben).
2. `manifest.webmanifest`, `icon.svg` und `.nojekyll` in das Hauptverzeichnis des Repositories legen.
3. GitHub Pages: `Settings → Pages → Deploy from a branch → main → /(root)`.
4. Auf dem iPhone `https://vollpfostenpi.github.io/MusicPilotAI/?v=06` in **Safari** öffnen. Falls weiterhin die alte Version erscheint, die Website-Daten für GitHub Pages in Safari löschen oder in einem privaten Tab öffnen.

## Ton testen

1. Auf **Ton testen** tippen. Falls kein Klang ertönt, iPhone-Lautstärke erhöhen, Audio-Ausgabeziel und Stummmodus prüfen.
2. Im einfachen Modus Prompt eingeben und **Arrangement erzeugen** tippen. Danach wird zur Studioansicht gewechselt und die Wiedergabe gestartet.
3. Bei Problemen **Audio neu starten** tippen.
4. Für gesampelte Instrumente im Studio Bibliothek wählen und **Instrumente laden** tippen. Bei Netzwerkfehlern bleiben interne Klänge aktiv.

## Funktionsgrenzen

Die Prompt-Analyse ist regelbasiert; realistisch gesungene KI-Stimmen entstehen derzeit nicht automatisch innerhalb dieser App. Die externe Gesangs-Demo erfordert einen separaten Dienst, dessen Verfügbarkeit nicht garantiert ist. Das deutsche KI-Sprachmodell ist eine **Sprechstimme**, keine Gesangsstimme. WAV und MP3 Export sind vorgesehen; MP3 benötigt das freie externe JavaScript-Modul lamejs. Großes Audio-Rendering kann iPhone-Speichergrenzen erreichen.

Die App wurde auf JavaScript-Syntax und Dateistruktur kontrolliert. Ein Realgerätetest auf Safari wurde nicht durchgeführt.
