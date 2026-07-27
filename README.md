# Coder

A party-trick coding app: press **any** keys and real, runnable code streams
out on a black screen — exactly one character per deliberate key press.
Stop typing and it stops. Held keys do not auto-repeat.

Unlike the classic "hacker typer" apps, the output is never gibberish:
every program in the library is genuine, complete, and compiles/runs as-is.

## Run it

**Live:** https://ppscon.github.io/ai-bot/

Or locally — no build, no server, no dependencies:

```
open index.html      # or just double-click it
```

## How it works

1. **Type a name directly.** Entering `Ana` writes "Hello, Ana!" into the
   short website's real HTML. Choose **edit name** at any point to change it.
2. **Optionally describe another program.** Local matching recommends the
   closest preset without contacting an AI service.
3. **Or pick a program** from the grid to override the recommendation.
4. Hit **START TYPING** and type.

There is no AI service, API key, account, network request, dependency, or
build step. It runs entirely in the browser and clears the key saved by older
releases.

- **One keystroke = one character** — the code appears at exactly the
  speed you type, perfectly synchronized with your fingers
- **Held keys do not repeat**, so one physical press cannot turn into a burst
- An interrupted page reload **resumes at the same character**
- A visible **compiling progress bar** finishes before **Run It** appears
- **Backspace** un-types (for that authentic "fixing a typo" look)
- **ESC** returns to the menu (**☰ menu** button on phones)
- Live **WPM** and **% written** in the status bar
- When the file is done you get a `✓ compiled clean` banner — then hit
  **▶ RUN IT** and *the program actually works*: Snake is playable
  (arrows or swipe), Life and Matrix rain animate, the Mandelbrot prints
  its fractal, the ray tracer renders its spheres, the web server logs
  requests

## The program library

| File | Language | What it really does |
|---|---|---|
| `index.html` | HTML/CSS | Short styled Hello page personalised with a name |
| `login.html` | HTML/CSS | Compact styled login form with email and password |
| `counter.html` | HTML/CSS/JS | Button that increments a visible counter |
| `clock.html` | HTML/CSS/JS | Live digital clock updated every second |
| `colour.html` | HTML/CSS/JS | Colour picker that changes the page background |
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

The editor gutter numbers each source line as it is revealed.
