# Realtime-Reactive-Particles


## Projektbeschreibung

Dieses TouchDesigner-Projekt verwandelt Videoinput in ein audio-reaktives Partikelsystem. Das visuelle Ergebnis kombiniert Tiefeninformation, Feedback und Echtzeit-Reaktion auf Audiosignale.

Der Input kann wahlweise über eine Live-Webcam oder ein beliebiges Videofile eingespeist werden. Der Output lässt sich entweder direkt über einen Bildschirm ausgeben oder als Video aufzeichnen.
**Video presentation:** https://youtube.com/shorts/NUo1IY45WQo?feature=share



## Aufbau & Funktionsweise

### 1. **Input**

* **Quellen:** Webcam (`Video Device In`) oder Videodatei (`Movie File In`).
* **Keying:** Über den `Luma Keyer` wird eine Helligkeitsmaske erstellt. Der Threshold-Wert sollte je nach Quelle angepasst werden, um ein optimales Ergebnis zu erzielen.

  > **Meine verwendete MovieFileIn Datei:** https://www.swisstransfer.com/d/960c9d23-4b8f-4ff4-a8d7-e7cf723f89b3


### 2. **3D-Partikelsystem**

* Die Luma-Key-Maske wird auf eine Fläche übertragen und in ein Partikelsystem umgewandelt.
* Die Partikel verhalten sich chaotisch oder organisch, je nach Kombination mit Noise und Feedback.

> **Hinweis:** Wenn das Bild flackert, kann es helfen, den Parameter `Time Inc` in der `Particle SOP` leicht zu erhöhen.

### 3. **Feedback-Loop**

* Das erzeugte Partikelsystem wird in einen Feedback-Zyklus eingebunden.
* Die `Noise TOP` steuert Bewegungsmuster und visuelle Unruhe.
* Der Loop sorgt für Bewegungsspuren und eine visuelle Tiefe.

### 4. **Audio-Reaktivität**

* Eine Audioquelle (in diesem Fall "All Of Me" von DRTKMS) wird analysiert.
* Im aktuellen Setup reagiert das System auf die Kick-Drum des Songs.
* Getriggerte Parameter:

  * `Harmonic Gain` der `Noise TOP`
  * `Seed` der `Noise TOP`

Diese Trigger sorgen für starke Reaktionen im Feedbacksystem – jeder Kick führt zu einem visuell spürbaren Impuls.

### 5. **Output**

* **Live-Display:** via `Screen Output`
* **Videoaufnahme:** via `Movie File Out`

---

## Selbstreflexion

Ich habe mich mit diesem Projekt das erste Mal wirklich mit TouchDesigner beschäftigt. Anfangs war ich von der Oberfläche und den vielen Möglichkeiten überfordert – wie bei vielen anderen Programmen auch. Doch nach einigen Tutorials und Experimenten war ich schnell begeistert.

Mein ursprüngliches Ziel war die Integration einer Kinect-Kamera. Leider musste ich feststellen, dass diese auf macOS nicht funktioniert. Durch ein YouTube-Video bin ich dann auf die Idee gekommen, die Tiefeninformation stattdessen zu simulieren und eine normale Webcam als Videoinput zu benutzen. Für die finale Videopräsentation habe ich ein Video einer Ballettaufführung verwendet, da die Bewegungen einerseits sehr spannend für die Feedbackloops sind und der schwarze Hintergrund mit der weiß gekleideten Ballerina andererseits eine optimale Voraussetzung für den Luma Key bietet. Zusätzlich habe ich beim Erstellen der MovieFileIn-Datei mit „Gaussian Blur” und „Black Frames” gearbeitet. Diese Effekte haben den Partikel noch ein cooles Detail verliehen.

Ehrlich gesagt verstehe ich noch nicht alle Nodes im Detail – aber durch viel Trial-and-Error habe ich ein Ergebnis erzielt, das mich visuell überzeugt. Ich kann mir vorstellen, dieses Setup in Zukunft für Musikvideos oder vielleicht auch für Live-Performances einzusetzen, falls sich der richtige Use-Case ergibt.

---

