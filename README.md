<img width="1920" height="1080" alt="circle_art" src="https://github.com/user-attachments/assets/d91da633-5547-46fe-af04-e0cb5a241e67" />
# 🌿 Generative Study 001 — Accumulation

This project started as a minimal experiment in drawing with code.

At its core, the system is extremely simple:
each frame, a circle is drawn at the current mouse position.

```python
py5.circle(py5.mouse_x, py5.mouse_y, 50)
```

Nothing more.

---

## ⚙️ The System

The important part isn’t the circle — it’s the loop.

The `draw()` function runs continuously, meaning this line executes dozens of times per second. Instead of producing a single image, the code produces a *stream* of marks.

Crucially, the background is only set once:

```python
py5.background(0)
```

This means nothing is erased.

Every frame adds to what came before.

---

## 🧠 What the Code Actually Does

The system can be broken down into three parts:

### 1. Persistent Canvas

The screen is never cleared, so all previous frames remain visible.

### 2. Repetition Over Time

The same instruction runs repeatedly:

* same shape
* same size
* different position (based on mouse)

### 3. Input as a Variable

The only changing value is:

```python
py5.mouse_x, py5.mouse_y
```

This turns movement into data.

---

## 🌀 From Code to Behaviour

Even though the code is static, the output is not.

Because the drawing accumulates:

* overlapping circles form lines
* lines form clusters
* clusters form dense structures

The system transforms motion into texture.

What’s interesting is that complexity doesn’t come from complicated logic — it comes from **iteration + memory (the canvas)**.

---

## 🎛️ Control vs System

At first, it feels like direct control:
move mouse → draw circle

But over time, control shifts.

You’re no longer placing shapes —
you’re influencing how the system evolves frame by frame.

---

## 💾 Capturing the Output

A key press allows the current state of the system to be saved:

```python
def key_pressed():
    if py5.key_code == py5.ENTER:
        py5.save_frame("my_art.png")
```

This freezes a moment in an otherwise continuous process.

---

## 🧠 Reflection (from a coding perspective)

This was the first time I saw how little code is needed to produce something visually complex.

There’s no randomness.
No advanced math.
No large system.

Just:

* a loop (`draw`)
* a changing input (mouse position)
* and no reset

It changed how I think about writing code:

> instead of building outputs, I’m defining behaviours over time

---

## 🔭 Next Step

Right now, the system is unstructured — entirely driven by input.

Next, I want to introduce mathematical structure into the loop:

* replacing constant sizes with Fibonacci progression
* controlling spacing instead of relying on the mouse
* moving from free motion to defined patterns (spirals, growth systems)

The goal is to keep the simplicity, but make the behaviour intentional.

---

*Study 001 — starting from the smallest possible rule.*

