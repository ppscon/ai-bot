# Speed Coder

A party-trick coding app: mash **any** keys and real, runnable code streams
out on a black screen — at exactly the speed you type. Stop typing and it
stops. To anyone watching, you are writing a complete program at 300 WPM.

Unlike the classic "hacker typer" apps, the output is never gibberish:
every program in the library is genuine, complete, and compiles/runs as-is.

## Run it

No build, no server, no dependencies:

```
open index.html      # or just double-click it
```

## How it works

1. **Describe your program** (optional). Whatever you write becomes the
   header comment of the file, and keyword matching picks the best program
   from the library (e.g. "raytracer with spheres" → `raytracer.py`).
2. **Or pick a program** from the grid.
3. **Choose your boost** — characters revealed per keystroke
   (1 = honest, 3 = fast, 6 = wizard).
4. Hit **START TYPING** and mash the keyboard.

- **Backspace** un-types (for that authentic "fixing a typo" look)
- **ESC** returns to the menu
- Live **WPM** and **% written** in the status bar
- When the file is done you get a `✓ compiled clean` banner

## The program library

| File | Language | What it really does |
|---|---|---|
| `life.py` | Python | Conway's Game of Life animated in the terminal |
| `snake.py` | Python | Playable Snake (curses, arrow keys) |
| `mandelbrot.c` | C | ASCII Mandelbrot renderer (C89, compiles with `cc`) |
| `matrix.js` | Node.js | Green digital-rain animation in the terminal |
| `raytracer.py` | Python | Ray-traces three glossy spheres to `out.ppm` |
| `server.js` | Node.js | Zero-dependency HTTP server with a JSON API |

Every snippet is verified: the Python files pass `py_compile`, the
JavaScript passes `node --check`, and `mandelbrot.c` builds clean with
`cc -Wall -Wextra`. Copy any of them out of the app and they actually run.

Syntax highlighting is a built-in ~100-line tokenizer (keywords, strings,
numbers, comments, function names, operators — each its own colour), so the
whole app stays a single dependency-free HTML file.
