# 🍅 OBPL — Operation Based Program Language

**Version:** 1.0  
**Author:** HappyDarky  
**Live Demo:** [https://obplstudio.netlify.app](https://obplstudio.netlify.app) (or your GitHub Pages link)

## 📖 Description
OBPL is a custom programming language designed for creating 2D/3D browser games. It compiles into HTML5 and JavaScript on the fly. The language is built around the concept of "Operations" and features a unique, simplified syntax inspired by Lua.

## 📂 Project Structure
- `index.html`      : The hidden engine (compiles and runs the game).
- `operation.obpl`  : Your game code (write your logic here).
- `README.md`       : This documentation.

## 🚀 How to Run
1. Open `operation.obpl` and write your game code.
2. Save the file and refresh `index.html` in your browser.
*(Note: If hosted on GitHub Pages, the `operation.obpl` file must be served as plain text. If you encounter MIME-type errors, rename the file to `operation.txt` and update the fetch path in `index.html`).*

## 📝 Syntax Guide
1. `Ll` — Declares a local variable or function (e.g., `Ll score = 0`).
2. `#` — Equality operator (e.g., `if score # 10`). Replaces `==`.
3. `..` — String concatenation (e.g., `"Score: " .. score`).
4. `|| ... ||` — Comments.
5. `operation funct name() ... EndGame` — Function declaration.
6. `EOARL` — End Operation And Return Loop (acts as a `yield` or `return`).
7. `FO(Function Operation)` — Functional wrapper (debounce) to prevent spam.

## 🛠️ Built-in Functions
- `clearCanvas()` — Clears the game screen.
- `createGEOMETRY(type, L, H, size, height, color)` — Draws shapes. Type can be `"rect"` or `"circle"`.
- `functPrint(text, L, H, size)` — Renders text or emojis on the canvas.
- `print(text)` — Logs text to the browser console.

## 🕹️ Example Code
```obpl
|| Simple OBPL Example ||

score = 0

Ll clicked(L, H)
    score = score + 1
    print("Score: " .. score)
    EOARL
EndGame

operation funct startGame()
    clearCanvas()
    functPrint("Click anywhere!", 130, 150, 20)
EndGame