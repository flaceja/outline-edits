---
name: outline-edits
description: "Erstelle und überarbeite kurze 3D-Outline- oder Blueprint-Video-Edits aus vorgegebener Musik und einem Thema; ein Originalvideo ist optional. Verwende diesen Skill für Edits im Stil unseres Starship-Edits mit weißem Code-Text, musikgerechten Shakes und flüssigen Detailfahrten. Erzeugt fertige MP4-Dateien."
---

# 3D-Outline-Edits

Erzeuge den tatsächlichen Edit zum gewünschten Thema. **Musik und Thema genügen.** Entwickle Konzept, Bildfolge, Texte, Modellierung, Kamerafahrten und Effekte selbstständig im unten beschriebenen Stil. Ein Originalvideo ist optional. Dieser Skill fasst den erprobten Starship-Ablauf zusammen, verallgemeinert aber weder Raketen-Geometrie noch konkrete Sekundenwerte auf andere Themen.

## Auftrag und Ausgangspunkt

- Leite Thema, Musik und jüngste Korrekturen zuerst aus dem laufenden Auftrag ab. Ohne Originalvideo direkt nach [Musik und Thema](references/music-driven.md) arbeiten; keine Referenz, fertigen Texte oder ein Storyboard verlangen. Nicht vorgegebene gestalterische Entscheidungen selbst treffen, einschließlich eines passenden Musikausschnitts, der Dauer und des Bildformats. Frage nur nach Informationen, die tatsächlich blockieren, etwa einer nicht eindeutig identifizierbaren Musikversion.
- Bei einem vorhandenen Projekt auf der letzten korrigierten Szene und dem letzten Export aufbauen. Eine neue Anweisung wie „Blitze entfernen“ betrifft die entsprechende Effektebene; starte nicht unbemerkt von einer älteren Fassung.
- Für Aufträge mit diesem Skill gelten die untenstehenden Stilvorgaben als Ausgangspunkt. Neue ausdrückliche Wünsche haben Vorrang. Bei einer zusätzlichen Videoreferenz deren Bildsprache und Bewegung untersuchen; bei neu vorgegebener Musik das Timing daran anpassen.
- Eine neue `/goal`-Anweisung über die verfügbaren Goal-Funktionen bearbeiten; ein normaler Edit-Auftrag erzeugt nicht automatisch ein Ziel oder eine Automation.

## Stilvorgaben für diesen Edit-Typ

- Schwarzer Hintergrund, dunkler **blickdichter** Körper, weiße sichtbare Konturen. Kein transparentes Gitter, durch das sämtliche hinteren Kanten sichtbar sind.
- Weißer Monospace-Text mit kurzen Code-Überschriften, optional `//`, Zeilennummern und Cursor. Überschrift und Inhalt schnell Zeichen für Zeichen schreiben; keine vollständigen Absätze auf einmal einblenden. Lesbar bleiben, nicht durch technische Dekoration überladen.
- Das Objekt fliegt bereits während des aktiven Übergangs-Shakes ins Bild. Objekt, Überschrift und schreibender Absatz werden gemeinsam verformt. Der typische Shake besteht aus kurzem seitlichem Ausschlag, Linsenkrümmung, Rückstoß und raschem Abklingen, nicht gleichmäßigem Dauerzittern.
- Intro: tatsächliche Drehung des Objekts und ein zusammenhängender Kamerazug auf ein passendes Detail, mit allmählicher Ausrichtung. Bei Raketen z. B. ins Triebwerk; bei anderen Themen ein dafür geeignetes, vorhandenes Detail wählen.
- Moderates Tempo, saubere Beschleunigung und Verzögerung. Keine unbeabsichtigten Kamera-Sprünge oder Achsenwechsel.
- **Keine weißen Vollbild-Blitze an den Schnitten. Kein Fade-out als Ersatz für den Übergang ins Triebwerk/Detail.** Ein Schluss-Fade ist eine eigene gestalterische Entscheidung, kein Schnitt-Effekt.
- Die vorgegebene Musik verwenden, einschließlich der gewünschten Version und eines vorgegebenen Ausschnitts. Schnitte und Bewegungsakzente an ihr ausrichten. Nur bei einem entsprechenden Referenzauftrag dessen Originalton übernehmen. Ein Logo-/Plattform-Outro nur dann übernehmen, wenn es zum gewünschten Clip gehört.

## Arbeitsablauf

1. **Musik analysieren und Bildfolge entwerfen.** Den tatsächlichen Track auf Phrasen, Akzente, Aufbau und Drop untersuchen. Daraus eine eigene Szenenfolge mit passenden Enthüllungen, Detailfahrten, Einflügen und kurzen Texten entwickeln; siehe [Musik und Thema](references/music-driven.md). **Falls eine Videoreferenz vorliegt:** zusätzlich jeden wichtigen Frame ihrer Einflüge, Shakes, Schreibanimationen und Kamerafahrten prüfen; siehe [Referenzanalyse](references/reference-analysis.md). Bei anderer Musik deren Rhythmus folgen statt alte Sekundenwerte zu kopieren.
2. **Thema fachlich und visuell umsetzen.** Reale Proportionen, Variante, charakteristische Bauteile und Textaussagen anhand geeigneter Quellen prüfen. Passende Modelle/Footage online beschaffen, wenn sie das Ergebnis verbessern; Quelle und Nutzungsbedingungen mitführen. Vorhandene brauchbare Geometrie wiederverwenden, fehlerhafte Teile gezielt neu bauen. Ein beliebiges Ersatzmodell ist keine ausreichende Themenanpassung.
3. **Szene und Bewegung bauen.** Kamera, Objektbewegung, Texte und Effekte getrennt halten. Zuerst problematische Ansichten und kurze Bewegungsproben rendern. Die Detailfahrt, Blickdichtigkeit, Abstände und Drehachsen vor dem langen Render prüfen. Verfahren und Blender-Helfer: [3D und Bewegung](references/blender-motion.md).
4. **Text und Effekte komponieren.** Den selbst entwickelten Musik-Zeitplan umsetzen; bei einem Referenzauftrag dessen passende Bewegungsmerkmale übernehmen. Modell und Fakten müssen zum Thema passen. Das Shake-Preset an Akzente, Szenendauer und Lesbarkeit anpassen; seine alten Einsatzzeiten nicht kopieren. Parameter und Beispiele: [Compositing](references/compositing.md).
5. **Fertigen Export prüfen.** Die tatsächlich gespeicherte MP4 decodieren und die geänderten Übergänge sequenziell kontrollieren, auch bei einem Edit ohne Originalvideo. Musik und Bild gemeinsam prüfen: Akzente treffen die beabsichtigten Bewegungen und Schnitte. Shake und Einflug überlappen; Text schreibt sichtbar; Kamera richtet sich kontinuierlich aus; keine ungewollten Blitze, Ausblendungen, schwarzen Zwischenbilder oder sichtbaren Durchdringungen. Abgeklungene Shakes kehren ohne Sprung zur neutralen Ansicht zurück. Audio, Dauer, FPS, Auflösung und Reihenfolge stimmen. Nicht bloß ein Vorschauprojekt für geprüft erklären.
6. **Ausgeben.** Eine neue eindeutig benannte MP4 im vorgesehenen Ausgabeordner ablegen und direkt verlinken/anzeigen. Relevante Grenzen ehrlich nennen. Nur bei gewünschtem Upload den passenden Abschnitt in [Veröffentlichung](references/publishing.md) anwenden.

## Wiederverwendbare Bausteine

- `scripts/reference_frames.py`: Video **sequenziell** lesen; Übersicht, Zeit-/Frame-Index und Detail-Frames zu gewählten Zeitfenstern speichern. Keine unzuverlässigen zufälligen Suchsprünge beim Prüfen.
- `scripts/edit_effects.py`: unabhängiges Modul für den gemessenen Shake mit Bewegungsunschärfe, schnelle weiße Code-Schreibanimation und Bewegungsunschärfe einzelner RGBA-Objekte. CLI `--demo` erzeugt eine kleine Prüfung auf einem synthetischen Motiv.
- `scripts/blender_motion.py`: in Blender importierbare Hilfen für stabil ausgerichtete Kameras, echte Drehung um eine Weltachse und Wahl einer gemeinsamen Drehmitte.
- `assets/outline-impact.json`: finales, auf die Bildgröße normiertes Shake-Preset der letzten Fassung, einschließlich zeitlicher Rückstöße; enthält keine Blitz-Ebene.
- [Starship-Fall](references/starship-case.md): überprüfte Zeitwerte und Geometrie-Lektionen aus dem ursprünglichen Beispiel; keine erforderlichen lokalen Projektdateien.

Die Helfer haben keine Abhängigkeit von alten `work/v2`–`work/v14`-Imports. Python benötigt NumPy und Pillow, die Videoanalyse zusätzlich FFmpeg/FFprobe; Blender-Helfer laufen in Blender. Vorhandene Laufzeiten bevorzugen. Einen kompletten neuen Render nur dann wiederholen, wenn die Änderung oder eine fehlgeschlagene Prüfung ihn rechtfertigt.
