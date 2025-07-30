You will find the English ReadMe at the end of the document.

# Display-Erweiterung für MakeCode

MakeCode‑Erweiterung für den Calliope mini, die erweiterte Display-Funktionen über die integrierte LED-Matrix bietet (Pixel, Helligkeit, Animation usw.).

---

## 🔧 Installation

So fügst du die Erweiterung deinem MakeCode-Projekt hinzu:

1. Öffne [makecode.calliope.cc](https://makecode.calliope.cc/)
2. Erstelle ein neues Projekt
3. Klicke oben rechts auf das Zahnrad ⚙️ → **Erweiterungen**
4. Gib den GitHub-Link zur Erweiterung ein  
   `https://github.com/calliope-edu/pxt-display`
5. Du findest danach eine neue Block-Kategorie (z. B. `Display` oder `LED`) im Block-Editor.

---

## 📦 Funktionen

Die Erweiterung bietet folgende Blöcke zur Nutzung der 5×5-LED-Matrix:

- **Punkt setzen**:  
  `set pixel at x y to on/off` – Text oder Block, um das einzelne Pixel an Koordinate `(x, y)` an- oder auszuschalten  

- **Helligkeit**:  
  `brightness` – gibt den aktuellen Helligkeitswert (0–255) zurück  
  `set brightness to value` – setzt die gesamte Matrix-Helligkeit

- **Animationsteuerung**:  
  `stop animation` – stoppt alle laufenden LED-Animationen und leert die Warteschlange

- **Display-Modus wechseln**:  
  `set display mode to [mode]` – wechselt zwischen Schwarz-Weiß und Graustufen (sofern unterstützt)  
  `display mode` – liest den aktuellen Modus

- **Display aktivieren/deaktivieren**:  
  `led enable on/off` – schaltet die LED-Matrix komplett ein oder aus

- **Screenshot erzeugen**:  
  `screenshot` – nimmt ein Bild der aktuellen Matrix und gibt es als `Image` zurück

---

## 🧪 Beispiel in JavaScript

```blocks
// Zeige abwechselnd Pixel und passe die Helligkeit an
basic.forever(() => {
    display.enable(true)
    display.setBrightness(50)
    display.point(2, 2, true)
    basic.pause(500)
    display.point(2, 2, false)
    basic.pause(500)
})
```

```blocks
// Screenshot der Matrix speichern und anzeigen
let img = display.screenshot()
image.showImage(img)
```
## ℹ️ Technische Details

Anzeige-Modus: Unterstützt Standard‑PXT-Display-Modi wie blackAndWhite und greyScale.
Polling/Stromverbrauch: stopAnimation() beendet alle Hintergrundanimationen.

## 🎓 Anwendungsbeispiel

Verwende die Erweiterung, um kleinere UI-Elemente wie Ladebalken, Icons oder einfache Spiele-Displays auf der Matrix darzustellen:

Ladebalken basierend auf Helligkeit nutzen
Eigene Animation mit stopAnimation() kontrollieren
Dynamisches Anzeigen eines Punktes z. B. als Cursor oder Roboterposition



# Display extension for MakeCode

MakeCode extension for the Calliope mini that provides advanced display functions using the built-in 5×5 LED matrix — including pixel control, brightness, animation, and more.

---

## 🔧 Installation

To add the extension to your MakeCode project:

1. Open [makecode.calliope.cc](https://makecode.calliope.cc/)
2. Create a new project
3. Click the gear icon ⚙️ in the top-right → **Extensions**
4. Paste the GitHub URL for this extension:  
   `https://github.com/calliope-edu/pxt-display`
5. A new block category (e.g., `Display` or `LED`) will appear in the block editor.

---

## 📦 Features

This extension offers blocks for advanced control of the 5×5 LED matrix:

- **Set Pixel**:  
  `set pixel at x y to on/off` – Turns a specific pixel at coordinates `(x, y)` on or off.

- **Brightness**:  
  `brightness` – Returns the current global brightness level (0–255)  
  `set brightness to value` – Sets the brightness for the entire LED matrix

- **Animation Control**:  
  `stop animation` – Stops all running LED animations and clears the animation queue

- **Display Mode**:  
  `set display mode to [mode]` – Switches between black-and-white and grayscale modes (if supported)  
  `display mode` – Returns the current display mode

- **Enable/Disable Display**:  
  `led enable on/off` – Turns the LED matrix on or off entirely

- **Screenshot**:  
  `screenshot` – Captures the current LED matrix state and returns it as an `Image` object

---

## 🧪 JavaScript Example

```blocks
// Blink a pixel and adjust brightness
basic.forever(() => {
    display.enable(true)
    display.setBrightness(50)
    display.point(2, 2, true)
    basic.pause(500)
    display.point(2, 2, false)
    basic.pause(500)
})
```

## display

	Package for the LCD from Seeed Studio.

## License

MIT

## Supported target

* for PXT/calliope
