# Wortuhr Firmware-Update (Browser-Flasher)

Diese Seite ermöglicht es, bereits gebaute Wortuhren direkt aus dem Chrome- oder
Edge-Browser mit einem Bugfix-Update zu versorgen — ganz ohne Arduino IDE,
ohne Bibliotheken-Installation.

Enthaltene Fixes gegenüber der ursprünglich ausgelieferten Firmware:

- „Automatische Zeitzone“ lässt sich jetzt korrekt deaktivieren und speichern.
- Das Web-Interface lädt nach dem Speichern von Einstellungen zuverlässig,
  ohne dass ein Neustart der Uhr nötig ist (Heap-Fragmentierung behoben).
- Farb- und Helligkeitsänderungen erscheinen sofort auf der Uhr statt erst
  nach 1–2 Minuten.

Die Seite nutzt [ESP Web Tools](https://esphome.github.io/esp-web-tools/) und
die Web-Serial-API des Browsers, um das kompilierte Firmware-Image direkt per
USB auf den Wemos D1 mini zu übertragen.

## Herkunft & Lizenz

Basiert auf dem quelloffenen [Wordclock-Projekt von
panbachi](https://github.com/panbachi/wordclock) ([panbachi.de](https://www.panbachi.de)),
lizenziert unter der [MIT-Lizenz](LICENSE), erweitert um eine
E-Mail-Funktion sowie die oben genannten Bugfixes.

## Hosten via GitHub Pages

1. Repo-Inhalt (`index.html`, `manifest.json`, `wordclock-email.bin`, `LICENSE`)
   in ein neues GitHub-Repository hochladen.
2. In den Repo-Einstellungen unter **Settings → Pages** die Quelle auf
   „Deploy from branch“, Branch `main`, Ordner `/ (root)` stellen.
3. Nach ein bis zwei Minuten ist die Seite unter
   `https://<benutzername>.github.io/<repo-name>/` erreichbar.

## Neue Firmware-Version veröffentlichen

Kompilierte `.bin`-Datei (Arduino IDE → Sketch → „Kompilierte Binärdatei
exportieren“) als `wordclock-email.bin` in dieses Repo hochladen und dabei die
vorhandene Datei ersetzen. Optional die `version` in `manifest.json`
aktualisieren, damit Nutzer die neue Version erkennen.
