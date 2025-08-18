# Week 1: Mathematical Thinking and Python Setup — Detailed Step-by-Step Guide

## Week 1 Overview
**Total Time:** 4–6 hours  
**Goal:** Establish mathematical thinking patterns, set up a reliable Python environment, and review fundamental concepts.  
**Approach:** ~70% setup & basics, ~30% practice problems.  
**Deliverables:** A working environment, 5–7 focused notebooks, and a short self-assessment.

---

## Day 1 (≈1.5h): Environment Setup & Mathematical Mindset

### (Optional) Step 0 — Repo & Folders (5–10 min)
- Repo (already created): `learning-math`
- Suggested structure to keep Weeks tidy:
  - `week-01/Week1-Setup.ipynb`
  - `week-01/Week1-BasicMath.ipynb`
  - `week-01/Week1-Algebra.ipynb`
  - `week-01/Week1-Applications.ipynb`
  - `week-01/Week1-Challenges.ipynb`
  - `week-01/Week1-SelfAssessment.ipynb`
  - `data/` (optional, for any CSVs later)
  - `.gitignore` (include: `.ipynb_checkpoints/`)

### Step 1 — Python Environment Setup (≈45 min)

**Install Anaconda / Miniconda (Recommended)**
1. Download for your OS (Python 3.x). Miniconda is enough for this project.
2. Install:
   - **Windows:** run installer, check “Add to PATH”.
   - **macOS/Linux:** follow terminal steps.
3. Verify in terminal:
    
        python --version
        conda --version

**Launch Jupyter Notebook**
1. Open terminal.
2. Start:
    
        jupyter notebook
    
3. In the browser UI:
   - Create folder `week-01`.
   - Create notebook `Week1-Setup.ipynb`.

*(Alt: You can use plain `pip` + `venv` if you prefer.)*

### Step 2 — Install Essential Libraries (≈15 min)
In the first cell of `Week1-Setup.ipynb`, run:

    # Install required libraries (run once)
    import sys
    !{sys.executable} -m pip install numpy matplotlib sympy scipy
    
    # Import and quick sanity checks
    import numpy as np
    import matplotlib.pyplot as plt
    import sympy as sp
    from sympy import symbols, solve, diff, integrate
    import math
    
    print("All libraries installed successfully!")
    print(f"NumPy version: {np.__version__}")
    print(f"Python version: {sys.version.split()[0]}")

### Step 3 — Mathematical Mindset (≈30 min)
- **Watch:** 3Blue1Brown Q&A on problem-solving: https://www.youtube.com/watch?v=-bc9EWhmDZg
- **Key takeaways (capture in a Markdown cell):**
  - Mathematics is pattern recognition.
  - Build visual/intuition first, proof later.
  - Question assumptions.
  - Learn from examples → generalize.

---

## Day 2 (≈1.5h): First Mathematical Computing Session

Create `week-01/Week1-BasicMath.ipynb`.

### Step 1 — Basic Python Math (≈30 min)

    # === Basic Arithmetic ===
    a = 15
    b = 4
    
    print(f"{a} + {b} = {a + b}")
    print(f"{a} - {b} = {a - b}")
    print(f"{a} * {b} = {a * b}")
    print(f"{a} / {b} = {a / b}")     # true division
    print(f"{a} // {b} = {a // b}")   # floor division
    print(f"{a} % {b} = {a % b}")     # remainder
    print(f"{a} ** {b} = {a ** b}")   # exponentiation

### Step 2 — `math` Module Essentials (≈30 min)

    import math
    
    print("=== Math Module Functions ===")
    x = 16
    y = -7.5
    
    print(f"sqrt({x}) = {math.sqrt(x)}")
    print(f"|{y}| = {abs(y)}")
    print(f"ceil({y}) = {math.ceil(y)}")
    print(f"floor({y}) = {math.floor(y)}")
    print(f"pi = {math.pi}")
    print(f"e = {math.e}")
    print(f"sin(pi/2) = {math.sin(math.pi/2)}")
    print(f"log10(100) = {math.log10(100)}")

### Step 3 — First Plot (≈30 min)

    import numpy as np
    import matplotlib.pyplot as plt
    
    # Parabola y = x^2
    x = np.linspace(-5, 5, 100)
    y = x**2
    
    plt.figure(figsize=(8, 6))
    plt.plot(x, y, label='y = x²')
    plt.axhline(0, linewidth=1)
    plt.axvline(0, linewidth=1)
    plt.grid(True)
    plt.xlabel('x')
    plt.ylabel('y')
    plt.title('My First Mathematical Plot')
    plt.legend()
    plt.show()
    
    # Exercise ideas: y = x^3, y = sin(x), y = e^x

### Reflection (MIT 18.01, ≈10–15 min)
- **Watch:** MIT 18.01 Lecture 1: https://www.youtube.com/watch?v=7K1sB05pE0A
- **Answer in Markdown:**
  1. What surprised you about the derivative concept?
  2. 3 real-world examples of rates of change?
  3. Open questions about calculus?

---

## Day 3 (≈1.5h): Algebraic Foundations

Create `week-01/Week1-Algebra.ipynb`.

### Step 1 — Quick Algebra Review (≈45 min)

    import math
    
    print("Problem 1: 3x + 7 = 22")
    x1 = (22 - 7) / 3
    print(f"x = {x1}")
    print(f"Check: 3*{x1} + 7 = {3*x1 + 7}")
    
    print("\nProblem 2: 2(x - 3) = 4x + 8")
    # Manual steps (shown as printouts)
    print("2x - 6 = 4x + 8  →  -2x = 14  →  x = -7")
    x2 = -7
    print(f"Check: LHS = 2({x2} - 3) = {2*(x2 - 3)}  |  RHS = 4({x2}) + 8 = {4*x2 + 8}")
    
    print("\nProblem 3: x² - 5x + 6 = 0 (quadratic formula)")
    a, b, c = 1, -5, 6
    D = b**2 - 4*a*c
    sqrt_D = math.sqrt(D)
    r1 = (-b + sqrt_D) / (2*a)
    r2 = (-b - sqrt_D) / (2*a)
    print(f"Roots: {r1}, {r2}")

### Step 2 — SymPy for Algebra (≈45 min)

    import sympy as sp
    x = sp.Symbol('x')
    
    # Solve equations symbolically
    sol1 = sp.solve(sp.Eq(3*x + 7, 22), x)
    print(f"3x + 7 = 22 → x = {sol1}")
    
    sol2 = sp.solve(sp.Eq(2*(x - 3), 4*x + 8), x)
    print(f"2(x - 3) = 4x + 8 → x = {sol2}")
    
    sol3 = sp.solve(sp.Eq(x**2 - 5*x + 6, 0), x)
    print(f"x² - 5x + 6 = 0 → x = {sol3}")
    
    # Expand & factor
    print("Expand (x + 3)² →", sp.expand((x + 3)**2))
    print("Factor x² + 6x + 9 →", sp.factor(x**2 + 6*x + 9))

### Step 3 — Function Concepts (optional reinforcement, 10–15 min)

    import numpy as np
    import matplotlib.pyplot as plt
    import math
    
    def f(x): return 2*x + 3
    def g(x): return x**2 - 1
    def h(x): return math.sin(x)
    
    xs = [-2, -1, 0, 1, 2]
    print("x\tf(x)\tg(x)\th(x)")
    print("-"*25)
    for xv in xs:
        print(f"{xv}\t{f(xv)}\t{g(xv)}\t{h(xv):.3f}")
    
    x_plot = np.linspace(-3, 3, 200)
    plt.figure(figsize=(12, 4))
    
    plt.subplot(1, 3, 1); plt.plot(x_plot, 2*x_plot + 3); plt.title('f(x) = 2x + 3'); plt.grid(True)
    plt.subplot(1, 3, 2); plt.plot(x_plot, x_plot**2 - 1); plt.title('g(x) = x² - 1'); plt.grid(True)
    plt.subplot(1, 3, 3); plt.plot(x_plot, np.sin(x_plot)); plt.title('h(x) = sin(x)'); plt.grid(True)
    
    plt.tight_layout(); plt.show()

---

## Day 4 (≈1.5h): Applied Problems & Review

Create `week-01/Week1-Applications.ipynb`.

### Step 1 — Real-World Applications (≈45 min)

    import math
    
    # Areas
    def rectangle_area(length, width): return length * width
    def circle_area(radius): return math.pi * radius**2
    def triangle_area(base, height): return 0.5 * base * height
    
    print("Areas")
    print("Rectangle 5×3 →", rectangle_area(5, 3))
    print("Circle r=2.5 →", f"{circle_area(2.5):.2f}")
    print("Triangle b=4, h=6 →", triangle_area(4, 6))
    
    # Temperatures
    def c_to_f(c): return (c * 9/5) + 32
    def f_to_c(f): return (f - 32) * 5/9
    
    temps_c = [-10, 0, 20, 37]
    print("\nTemperature Conversions (C → F)")
    for t in temps_c:
        print(f"{t:>5}°C  →  {c_to_f(t):>6.1f}°F")
    
    temps_f = [32, 68, 86, 98.6]
    print("\nTemperature Conversions (F → C)")
    for t in temps_f:
        print(f"{t:>5.1f}°F →  {f_to_c(t):>6.1f}°C")
    
    # Compound interest
    def compound_interest(P, r, t, n=1):
        return P * (1 + r/n)**(n*t)
    
    initial, rate, years = 1000, 0.05, 10
    final = compound_interest(initial, rate, years)
    print(f"\nInvestment: ${initial} at {rate*100:.1f}% for {years} years")
    print(f"Final amount: ${final:.2f}  |  Interest: ${final - initial:.2f}")

### Step 2 — Mixed Practice Set (≈45 min)

    import sympy as sp
    import math
    x = sp.Symbol('x')
    
    print("=== WEEK 1 PRACTICE PROBLEMS ===\n")
    
    # 1) Linear
    print("1) Solve: 4x - 7 = 2x + 9")
    sol = sp.solve(sp.Eq(4*x - 7, 2*x + 9), x)
    print("   Solution:", sol[0])
    print(f"   Check LHS={4*sol[0]-7}, RHS={2*sol[0]+9}\n")
    
    # 2) Quadratic
    print("2) Solve: x² + 3x - 10 = 0")
    solq = sp.solve(sp.Eq(x**2 + 3*x - 10, 0), x)
    print("   Solutions:", solq)
    for s in solq:
        check = s**2 + 3*s - 10
        print(f"   Check x={s}: {check}")
    print()
    
    # 3) Function eval
    print("3) f(x) = x³ - 2x + 1 → f(-2), f(0), f(3)")
    def f(xv): return xv**3 - 2*xv + 1
    for val in [-2, 0, 3]:
        print(f"   f({val}) = {f(val)}")
    print()
    
    # 4) Distance
    print("4) Distance between (3,4) and (7,1)")
    def distance(x1, y1, x2, y2):
        return math.sqrt((x2-x1)**2 + (y2-y1)**2)
    d = distance(3, 4, 7, 1)
    print(f"   Distance = {d}  (should be 5)")
    print()
    
    # 5) Percentages
    print("5) 15% of 240, and what percent is 36 of 150?")
    percent_of = 0.15 * 240
    what_percent = (36 / 150) * 100
    print(f"   15% of 240 = {percent_of}")
    print(f"   36 is {what_percent}% of 150")

---

## Day 5–7 (≈30 min each): Consolidation & Challenges

### Day 5 — Pattern Recognition (≈30 min)

    # Express sequences with formulas where possible
    sequences = [
        [2, 4, 6, 8, 10],      # 2n
        [1, 4, 9, 16, 25],     # n^2
        [3, 6, 12, 24, 48],    # 3 * 2^(n-1)
        [1, 3, 6, 10, 15]      # n(n+1)/2 (triangular)
    ]
    
    for i, seq in enumerate(sequences, start=1):
        print(f"Sequence {i}: {seq}")
        # Try to write the nth term a_n and test it for n = 1..len(seq)

### Day 6 — Graphing Practice (≈30 min)

    import numpy as np
    import matplotlib.pyplot as plt
    
    functions = [
        ("Linear",       lambda x: 2*x + 1),
        ("Quadratic",    lambda x: x**2 - 3),
        ("Cubic",        lambda x: x**3 - x),
        ("Square Root",  lambda x: np.sqrt(np.abs(x))),
        ("Exponential",  lambda x: np.exp(x/2)),
        ("Logarithmic",  lambda x: np.log(np.abs(x) + 1))
    ]
    
    x = np.linspace(-3, 3, 400)
    fig, axes = plt.subplots(2, 3, figsize=(15, 10), layout="constrained")
    axes = axes.flatten()
    
    for i, (name, func) in enumerate(functions):
        axes[i].plot(x, func(x))
        axes[i].set_title(name)
        axes[i].grid(True)
        axes[i].set_xlabel('x')
        axes[i].set_ylabel('y')
        axes[i].set_xlim(-3, 3)     # fixed axes → makes comparisons clearer
        axes[i].axhline(0, linewidth=1)
        axes[i].axvline(0, linewidth=1)
    
    plt.show()

### Day 7 — Week Review Challenge (≈30–45 min)

    import numpy as np
    import matplotlib.pyplot as plt
    import math
    
    print("=== WEEK 1 CHALLENGE PROBLEMS ===")
    
    # Challenge 1: Quadratic solver
    def solve_quadratic(a, b, c):
        """Solve ax² + bx + c = 0 (real solutions if discriminant ≥ 0)."""
        D = b**2 - 4*a*c
        if D < 0:
            return "No real solutions"
        elif D == 0:
            return [-b / (2*a)]
        else:
            sqrt_D = math.sqrt(D)
            return [(-b + sqrt_D) / (2*a), (-b - sqrt_D) / (2*a)]
    
    for (a, b, c) in [(1, -5, 6), (1, -2, 1), (1, 0, 1)]:
        print(f"{a}x² + {b}x + {c} = 0 → {solve_quadratic(a, b, c)}")
    
    # Challenge 2: Transformations of y = x²
    x = np.linspace(-5, 5, 400)
    transforms = [
        ("Original",     lambda x: x**2),
        ("Shifted up",   lambda x: x**2 + 2),
        ("Shifted right",lambda x: (x-1)**2),
        ("Stretched",    lambda x: 2*x**2),
        ("Reflected",    lambda x: -x**2),
    ]
    
    plt.figure(figsize=(10, 6))
    for name, f in transforms:
        plt.plot(x, f(x), label=name)
    plt.axhline(0, linewidth=1); plt.axvline(0, linewidth=1)
    plt.grid(True)
    plt.title("Transformations of y = x² (fixed axes for clarity)")
    plt.xlim(-5, 5); plt.ylim(-6, 10)   # fixed limits → shifts/stretch are visually obvious
    plt.legend()
    plt.show()

---

## Week 1 Assessment

### Self-Check (What you should be able to do)
1. **Python Setup**
   - ✅ Launch Jupyter, manage notebooks
   - ✅ Import and use NumPy/Matplotlib/SymPy
   - ✅ Make basic plots with labels/grid

2. **Math Concepts**
   - ✅ Solve linear equations
   - ✅ Evaluate and reason about functions
   - ✅ Recognize simple patterns (arithmetic/geometric/triangular)

3. **Problem Solving**
   - ✅ Translate word problems → math expressions
   - ✅ Verify solutions two ways (algebraic + computational)
   - ✅ Visualize functions & transformations

### Mini-Quiz (Test Yourself — write answers before checking)

    # Week 1 Self-Assessment (no peeking!)
    # Q1: Solve 3(x + 2) = 15
    # Q2: If f(x) = x² + 3x - 1, find f(2)
    # Q3: Vertex of y = x² - 4x + 3
    # Q4: Convert 75°F to Celsius
    # Q5: Area of a circle with radius 3.5

### (Optional) Interactive Checker — one cell you can copy

    import math
    
    class QuizChecker:
        def __init__(self):
            self._answers = {
                1: 3,          # 3(x+2)=15 → x=3
                2: 9,          # f(2) where f(x)=x²+3x-1
                3: (2, -1),    # vertex of y=x²-4x+3
                4: 23.9,       # 75°F → °C
                5: 38.48       # circle area r=3.5
            }
            self.score = 0
    
        def check_q1(self, x_value):
            if abs(x_value - self._answers[1]) < 1e-2:
                print("✅ Q1 CORRECT"); self.score += 1
            else:
                print("❌ Q1 Try again (hint: expand then isolate x)")
    
        def check_q2(self, f2):
            if abs(f2 - self._answers[2]) < 1e-2:
                print("✅ Q2 CORRECT"); self.score += 1
            else:
                print("❌ Q2 Try again (hint: substitute x=2)")
    
        def check_q3(self, xv, yv):
            cx, cy = self._answers[3]
            ok = abs(xv - cx) < 1e-2 and abs(yv - cy) < 1e-2
            if ok:
                print("✅ Q3 CORRECT"); self.score += 1
            else:
                print("❌ Q3 Try again (hint: x = -b/(2a))")
    
        def check_q4(self, c):
            if abs(c - self._answers[4]) < 0.1:
                print("✅ Q4 CORRECT"); self.score += 1
            else:
                print("❌ Q4 Try again (hint: C = (F-32)*5/9)")
    
        def check_q5(self, area):
            if abs(area - self._answers[5]) < 0.1:
                print("✅ Q5 CORRECT"); self.score += 1
            else:
                print("❌ Q5 Try again (hint: A = πr²)")
    
        def final(self):
            print(f"\n🎯 Score: {self.score}/5")
            if self.score == 5: print("🎉 Perfect! Ready for Week 2")
            elif self.score >= 4: print("👍 Great job — review any misses")
            elif self.score >= 3: print("👌 Good start — practice missed areas")
            else: print("📚 Keep going — revisit Week 1")
    
    checker = QuizChecker()
    print("Use: checker.check_q1(...), ..., checker.final()")

---

## Next Week Preparation
- Organize notebooks inside `week-01/` and commit.
- Review any shaky topics; add short notes in Markdown cells.
- Confirm environment runs cleanly (no missing packages).
- Get ready for **Week 2: Functions & Trigonometry**.

---

