# MusicPilot AI 0.5 – iPhone-Musikstudio

Ein kostenloses, responsives, statisches Musikstudio für **Safari auf dem iPhone** und andere moderne Browser. Alle Dateien dieser Mappe gehören **direkt in die oberste Ebene** eines GitHub-Repositorys. Kein Build, kein Node.js, keine API-Schlüssel und kein kostenpflichtiger Dienst notwendig.

## ⚡ In 5 Minuten auf GitHub Pages veröffentlichen

**GitHub-Benutzer:** `vollpfostenpi` (falls dein GitHub-Account weiterhin so heißt).

1. In Safari auf **https://github.com/new** gehen, anmelden.
2. Repository Name: **`MusicPilotAI`**, **Public** wählen und **Create repository** tippen. GitHub Pages auf Free-Accounts benötigt üblicherweise ein öffentliches Repository.
3. Die `MusicPilotAI_GitHub_Upload.zip` in der iPhone-App **Dateien** öffnen und **Dekomprimieren/Entpacken** wählen. Die Dateien `index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `.nojekyll` und `README.md` auswählen.
4. Das neue Repository im Browser öffnen, **Add file → Upload files** wählen, die genannten **einzelnen entpackten Dateien**, nicht die ZIP, hochladen und mit **Commit changes** bestätigen. Falls der mobile Browser die Mehrfachauswahl nicht gut anbietet, in Safari über **aA → Desktop-Website anfordern** wechseln. Alternativ Dateien einzeln hinzufügen.
5. Repository → **Settings → Pages → Build and deployment**: **Deploy from a branch**, Branch **`main`**, Folder **`/(root)`**, **Save**. GitHub benötigt gewöhnlich wenige Minuten.
6. Nach erfolgreicher Veröffentlichung ist die Adresse voraussichtlich **https://vollpfostenpi.github.io/MusicPilotAI/** (exakte URL steht unter *Settings → Pages*). Dort in Safari öffnen. Danach **Teilen → Zum Home-Bildschirm**.
7. **Falls eine alte Version angezeigt wird:** Webseite neu laden oder das Home-Screen-Symbol schließen und erneut öffnen. Der Cache heißt `musicpilot-v05`.

Offizielle Pages-Anleitung: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Was tatsächlich funktioniert

- Sechs 16-Schritt-Spuren (Kick, Snare, Hi-Hat, Bass, Akkorde, Melodie), Lautstärke und Stummschalten
- Einfacher Prompt-Modus zur *regelbasierten* Erstellung/Variation von Beats und Akkordmustern, 6 Stilrichtungen, Tempo, Tonart und Dur/Moll
- Instrumente aus den kostenlosen Browser-SoundFont-Quellen FluidR3 GM, Musyng Kite und FatBoy über https://gleitz.github.io/midi-js-soundfonts/ ; Fallback auf WebAudio-Synthesizer
- Songtext-Editor mit 6.000 Zeichen
- Echte **KI-Sprechstimme in Deutsch** (kein Singen!) mit `Xenova/mms-tts-deu` und Transformers.js im Browser; Text pro Durchgang maximal 450 Zeichen; Modell wird auf Abruf von Hugging Face geladen
- Sprachvorschau aus der systemeigenen Stimme, Mikrofonaufnahmen (HTTPS / Mikrofonberechtigung)
- Aufnahmen und KI-Stimme als WAV separat speichern, in Gesamtexport mischen
- MP3 mit 128 bis 320 kbit/s oder WAV; MP3 benötigt den kostenlosen `lamejs`-Encoder aus einem CDN
- Lokale Projektspeicherung und JSON-Export/Import

## Ehrliche Grenzen

- **Keine generative komplette Musik-KI**: Der Prompt-Komponist interpretiert Stichworte regelbasiert, nicht durch ein großes Sprachmodell. Es gibt keinen sicheren kostenlosen, unbegrenzten Musik-Generierungs-Webdienst.
- **Kein KI-Gesang**: Die enthaltene neuronale Stimme spricht. Ein Modell wie DiffSinger/ähnlich muss getrennt angebunden und gehostet werden, kann nicht gratis und zuverlässig über GitHub Pages betrieben werden. Eigenes Aufnehmen von *Gesang* funktioniert.
- **iPhone-Leistung**: Das deutsche KI-Sprachmodell ist speicherintensiv und kann auf Safari fehlschlagen oder lange laden. Auf Desktop eher zuverlässig. Das ist nicht auf echtem iPhone getestet. Sprachvorschau über iOS-Stimmen als Alternative.
- **KI-Modell-Lizenz**: Das zugrunde liegende Meta MMS-TTS-Modell ist **CC BY-NC 4.0** – nur für nichtkommerzielle Nutzung. Siehe https://huggingface.co/facebook/mms-tts-deu und https://huggingface.co/Xenova/mms-tts-deu. Veröffentliche kommerziell nichts, was du mit diesem Modell erzeugt hast, ohne die Rechte vorher zu prüfen.
- Samples haben jeweils eigene Lizenzen (z. B. CC BY/CC BY-SA); vor kommerzieller Veröffentlichung prüfen.
- Instrumentensamples/Transformer-Module brauchen beim ersten Mal Internet; auch MP3 braucht CDN-Zugriff.
- *Deine Songs und Stimmen werden nicht auf GitHub gespeichert*. Nur Anwendungscode liegt im öffentlichen Repo. Audioaufnahmen und KI-Clips sind derzeit temporär und **nicht in der JSON-Projektdatei** enthalten; einzeln herunterladen.
- Es gibt **keine automatische Cloud-Synchronisierung**. Bei Löschung von Safari-Website-Daten kann die lokale Projektspeicherung verloren gehen.
- Ein öffentlicher GitHub-Pages-Link ist von jedem aufrufbar, aber die im Browser eingegebenen privaten Texte gehen bei normalen Studiofunktionen nicht in das Repo.

## Testplan nach Veröffentlichung

1. Safari-Seite über **HTTPS** öffnen und auf „Einfach → Arrangement erzeugen“ tippen.
2. Auf „▶ Abspielen“ tippen (Safari benötigt eine echte Nutzergeste für Audio).
3. Studio → bei einer Instrumentenspur Instrument wählen → **Instrumente laden** → Klangprobe.
4. Texte & Stimme → kurzen deutschen Text eingeben → **KI-Stimme erzeugen**, beim ersten Mal Download abwarten. Bei Fehlern **Einfache Sprachvorschau**.
5. MP3 oder WAV exportieren, über „Downloads“/„Dateien“ anhören.

**Versionsstatus:** 0.5 – Syntax geprüft, nicht mit echtem iPhone/produktivem Hosting Ende-zu-Ende getestet.


## Neuer KI-Gesang (Version 0.5)

**Reale Gesangssynthese mit SoulX-Singer als externer kostenloser Demo-Workflow:** Das offene Modell kann anhand einer vorgegebenen Melodie Gesang generieren. Modelldemo: https://huggingface.co/spaces/Soul-AILab/SoulX-Singer ; Quellcode: https://github.com/Soul-AILab/SoulX-Singer . Besonders Englisch und chinesische Sprachen werden dokumentiert; für deutsche Songtexte besteht keine Qualitätsgarantie. Nutzbarkeit und kostenfreie Kapazität der Demo sind nicht garantiert. Es wird **keine unbegrenzte kostenlose API behauptet**.

1. Im Studio ein Arrangement erstellen und Melodienoten setzen.
2. Im Bereich Texte & Stimme eine Liedzeile einfügen, auf **Gesang vorbereiten**, anschließend auf **MIDI-Melodie** tippen. Das MIDI enthält eine wiederholte Melodiespur als Leitlinie; Rhythmik und Textsilben müssen im externen Modell ggf. korrigiert werden.
3. **Echte KI-Sänger-Demo öffnen** antippen. Liedtext und Melodie dort eingeben bzw. MIDI im Editor bearbeiten (falls von der Demo unterstützt). Eine direkte Ein-Klick-Generierung aus MusicPilot AI existiert aktuell **nicht**.
4. Das fertig generierte Audio herunterladen und über **Gesangs-Audiodatei importieren** in die App laden. Beim Export die Checkbox **Aufnahmen und KI-Stimmen beim Export dazumischen** aktiviert lassen.

GitHub Pages kann den externen GPU-Rechner nicht selbst bereitstellen. Die neue Integration ist ein echter Austausch-Workflow mit einem KI-Gesangsmodell, **kein** lokal im iPhone laufendes Gesangsmodell und **keine garantierte automatische Online-Generierung**. KI-Songs für kommerzielle Veröffentlichung erfordern separate Prüfung der Modell-, Sample- und Stimmdatenrechte.
