# 🥁 JS Drum Kit

A simple interactive drum kit built with vanilla JavaScript. Play drum sounds by clicking on-screen buttons or pressing keys on your keyboard.

## Features

- 🖱️ Click drum pad buttons to play sounds
- ⌨️ Press keyboard keys to play the same sounds
- ✨ Visual "pressed" animation feedback on each trigger
- 🎧 Lightweight, no external libraries required

## Demo

Open `index.html` in your browser, then either:
- Click any drum pad on the screen, **or**
- Press one of the mapped keys on your keyboard

## Key Mapping

| Key | Sound         |
|-----|---------------|
| W   | Tom 1         |
| A   | Tom 2         |
| S   | Tom 3         |
| D   | Tom 4         |
| J   | Snare         |
| K   | Crash         |
| L   | Kick / Bass   |

## Project Structure

```
├── index.html
├── style.css
├── index.js          # main logic (event listeners, sound + animation)
└── sound/
    ├── sounds_tom-1.mp3
    ├── sounds_tom-2.mp3
    ├── sounds_tom-3.mp3
    ├── sounds_tom-4.mp3
    ├── sounds_snare.mp3
    ├── sounds_crash.mp3
    └── sounds_kick-bass.mp3
```

> **Note:** Each drum pad button and its keyboard key should share the same class/key name (e.g. a button with class `w` matches the `"w"` keypress) so `buttonAnimation()` can correctly select and animate it.

## How It Works

- **Click events:** Every element with the `.drum` class gets a `click` listener attached in a loop. On click, the button's inner text (e.g. `"w"`) is used to determine which sound to play.
- **Keyboard events:** A single `keypress` listener on `document` reads `event.key` and passes it to the same `makeSound()` and `buttonAnimation()` functions.
- **`makeSound(key)`:** Uses a `switch` statement to map a key to an `Audio` object and play it.
- **`buttonAnimation(key)`:** Adds a `pressed` CSS class to the matching element, then removes it after 100ms to create a brief flash/press effect.

## Setup

1. Clone or download this repository.
2. Make sure the `sound/` folder with all `.mp3` files sits alongside `index.js`.
3. Open `index.html` in any modern browser — no build step or server required.

