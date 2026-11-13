# Rundenuhr

Eine Stoppuhr mit **Auto-Runden**: Die App löst die Runden-Taste automatisch in einem festen Intervall aus. Alles läuft im Browser, ohne Installation und ohne Abhängigkeiten.

## Funktionen

- Stoppuhr mit großer Anzeige, darunter Start, Runde, Zurücksetzen, dann Auto-Runden (links) und Auto-Zeitverstellung (rechts) nach Skizze
- **Passwortsperre** für „Auto an“ und „Verstellen“: Passwort-Fenster erscheint erst beim Druck auf die Buttons und muss nach jedem Neuladen der Seite neu eingegeben werden (Passwort steht nur als SHA-256-Hash im Code; im Browser ist das nur eine Hürde, kein echter Schutz)
- **Zeit verstellen** um beliebig große Beträge (bis 10 000 Stellen, auch als 1e100), vorwärts, rückwärts oder setzen, auf Wunsch automatisch wiederholt
- **Auto-Runden** per Symbol oben rechts, Eingabe als Intervall oder als Rate (z. B. 1 Qa = 10¹⁵ Runden pro Sekunde): Intervall von Stunden **bis hinunter zu 0,00000000000000000000000000000001 s (10⁻³² s)**, mit Schnellwahl-Buttons
- **Keine Obergrenze für Runden**: Auto-Runden werden als Zeitraster gerechnet (BigInt), nicht einzeln gespeichert
- Optional: maximale Anzahl Auto-Runden
- Manuelle Runden zusätzlich möglich, beste und schlechteste Runde farbig markiert
- Liste zeigt die letzten 200 Runden, alle Rundenzahlen werden vollständig ausgeschrieben (mit Punkten), die Gesamtzahl zusätzlich in Worten
- CSV-Export (bis 200 000 Zeilen, danach ein Hinweis mit der Restzahl)
- Optionaler Signalton, Tastatursteuerung (`Leertaste`, `L`, `R`)
- Logo, Home-Bildschirm-Icon, installierbar und offline nutzbar

## Hinweis zur Genauigkeit

Browser messen Zeit nur auf etwa 1 µs genau und zeichnen rund 60-mal pro Sekunde. Auto-Runden unterhalb davon sind exakt **berechnete** Rasterpunkte (Runde n liegt bei n × Intervall) und keine einzeln gemessenen Ereignisse. Die große Zeitanzeige zeigt höchstens 5 Nachkommastellen, die Rundenzeiten in der Liste zeigen so viele Stellen, wie das Intervall braucht.

## Auf den Home-Bildschirm legen

Die App muss dafür über GitHub Pages (https) geöffnet sein.

- **iPhone/iPad (Safari):** Teilen → *Zum Home-Bildschirm*
- **Android (Chrome):** Menü ⋮ → *App installieren*

## Auf GitHub Pages veröffentlichen

1. Repository erstellen und alle Dateien hochladen (auch `icons/`, `manifest.webmanifest`, `sw.js`).
2. **Settings → Pages → Deploy from a branch → `main` / `(root)`**.
3. Die App ist unter `https://<dein-name>.github.io/<repo>/` erreichbar.

## Lizenz

MIT – siehe `LICENSE`.
