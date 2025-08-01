# Week 1: Mathematical Thinking and Python Setup - Detailed Step-by-Step Guide

## Week 1 Overview
**Total Time**: 4-6 hours  
**Goal**: Establish mathematical thinking patterns, set up Python environment, and review fundamental concepts  
**Approach**: 70% setup and basics, 30% practice problems

---

## Day 1 (1.5 hours): Environment Setup and Mathematical Mindset

### Step 1: Python Environment Setup (45 minutes)

**Install Anaconda (Recommended)**
1. **Download Anaconda**: Visit https://www.anaconda.com/ and download Python 3.x version
2. **Install Anaconda**: Follow the installation guide
   - Windows: Run the .exe file, check "Add Anaconda to PATH"
   - Mac/Linux: Follow terminal instructions
3. **Verify Installation**: Open terminal/command prompt and type:
```
python --version
conda --version
```
**Launch Jupyter Notebook**
1. Open terminal/command prompt
2. Type: `jupyter notebook`
3. Your browser should open with Jupyter interface
4. Create a new folder called "Math-Learning-Week1"
5. Create your first notebook: "Week1-Setup.ipynb"

**Alternative Setup Guide**: Watch tutorial at https://www.youtube.com/watch?v=2WL-XTl2QYI

### Step 2: Install Essential Libraries (15 minutes)
In your first Jupyter notebook cell, run:
```
# Install required libraries (run once)
import sys
!{sys.executable} -m pip install numpy matplotlib sympy scipy

# Import and test libraries
import numpy as np
import matplotlib.pyplot as plt
import sympy as sp
from sympy import symbols, solve, diff, integrate
import math

print("All libraries installed successfully!")
print(f"NumPy version: {np.__version__}")
print(f"Python version: {sys.version}")
```

### Step 3: Mathematical Mindset Introduction (30 minutes)

**Watch**: 3Blue1Brown Q&A on mathematical problem-solving: https://www.youtube.com/watch?v=-bc9EWhmDZg

**Key Takeaways to Note**:
- Mathematics is about pattern recognition
- Visual intuition before formal proof
- Question everything, even basic assumptions
- Build understanding from examples

---

## Day 2 (1.5 hours): First Mathematical Computing Session

### Step 1: Basic Python Math Operations (30 minutes)

Create a new notebook: "Week1-BasicMath.ipynb"

**Exercise Set 1: Basic Operations**
```
# Basic arithmetic in Python
print("=== Basic Arithmetic ===")
a = 15
b = 4

print(f"{a} + {b} = {a + b}")
print(f"{a} - {b} = {a - b}")
print(f"{a} * {b} = {a * b}")
print(f"{a} / {b} = {a / b}")
print(f"{a} // {b} = {a // b}")  # Floor division
print(f"{a} % {b} = {a % b}")    # Remainder
print(f"{a} ** {b} = {a ** b}")  # Exponentiation
```
**Exercise Set 2: Math Module Functions**
```
import math

Practice with math functions
print("=== Math Module Functions ===")
x = 16
y = -7.5

print(f"Square root of {x}: {math.sqrt(x)}")
print(f"Absolute value of {y}: {abs(y)}")
print(f"Ceiling of {y}: {math.ceil(y)}")
print(f"Floor of {y}: {math.floor(y)}")
print(f"π (pi): {math.pi}")
print(f"e: {math.e}")
print(f"sin(π/2): {math.sin(math.pi/2)}")
print(f"log(10): {math.log10(100)}")
```
### Step 2: First Visualization (30 minutes)

**Exercise Set 3: Basic Plotting**
```
import matplotlib.pyplot as plt
import numpy as np

Create your first mathematical plot
x = np.linspace(-5, 5, 100) # 100 points from -5 to 5
y = x**2 # Parabola

plt.figure(figsize=(8, 6))
plt.plot(x, y, 'b-', label='y = x²')
plt.grid(True)
plt.xlabel('x')
plt.ylabel('y')
plt.title('My First Mathematical Plot')
plt.legend()
plt.show()

#Exercise: Try plotting y = x³, y = sin(x), y = e^x**
```

### Step 3: Introduction to MIT 18.01 (30 minutes)

**Watch**: MIT 18.01 Lecture 1: https://www.youtube.com/watch?v=7K1sB05pE0A

**Take Notes On**:
- What is a derivative conceptually?
- How does slope relate to rate of change?
- Why does calculus matter?

**Create a reflection cell in your notebook**:
```
Reflection Questions (answer in markdown cells):
1. What surprised you most about the derivative concept?
2. Can you think of 3 real-world examples of rates of change?
3. What questions do you have about calculus?
```
---

## Day 3 (1.5 hours): Algebraic Foundations

### Step 1: Algebra Review and Practice (45 minutes)

Create notebook: "Week1-Algebra.ipynb"

**Exercise Set 4: Basic Algebra Problems**
```
#Solve these algebraically, then verify with Python
Problem 1: Solve 3x + 7 = 22
print("Problem 1: 3x + 7 = 22")

#Your algebraic solution: x = ?
x1 = (22 - 7) / 3
print(f"Solution: x = {x1}")
print(f"Verification: 3({x1}) + 7 = {3*x1 + 7}")

#Problem 2: Solve 2(x - 3) = 4x + 8
print("\nProblem 2: 2(x - 3) = 4x + 8")
#Your algebraic solution: x = ?
#Expand: 2x - 6 = 4x + 8
#Rearrange: 2x - 4x = 8 + 6
#Simplify: -2x = 14
x2 = -14 / 2
print(f"Solution: x = {x2}")
print(f"Verification: 2({x2} - 3) = {2*(x2 - 3)}, 4({x2}) + 8 = {4*x2 + 8}")

#Problem 3: Solve x² - 5x + 6 = 0
print("\nProblem 3: x² - 5x + 6 = 0")
#Factor: (x - 2)(x - 3) = 0
#Solutions: x = 2 or x = 3
x3_solutions =
for sol in x3_solutions:
    print(f"x = {sol}: {sol**2 - 5*sol + 6}")
```
**Exercise Set 5: Using SymPy for Algebra**
```
import sympy as sp

Define symbolic variable
x = sp.Symbol('x')

#Solve equations symbolically
eq1 = sp.Eq(3*x + 7, 22)
solution1 = sp.solve(eq1, x)
print(f"3x + 7 = 22: x = {solution1}")

eq2 = sp.Eq(2*(x - 3), 4*x + 8)
solution2 = sp.solve(eq2, x)
print(f"2(x - 3) = 4x + 8: x = {solution2}")

eq3 = x**2 - 5*x + 6
solution3 = sp.solve(eq3, x)
print(f"x² - 5x + 6 = 0: x = {solution3}")

#Expand and factor expressions
expr = (x + 3)**2
expanded = sp.expand(expr)
print(f"(x + 3)² = {expanded}")

expr2 = x**2 + 6*x + 9
factored = sp.factor(expr2)
print(f"x² + 6x + 9 = {factored}")
```

### Step 2: Function Concepts (45 minutes)

**Exercise Set 6: Functions and Their Properties**
```
#Define and explore functions
def f(x):
return 2*x + 3

def g(x):
return x**2 - 1

def h(x):
return math.sin(x)

#Evaluate functions at different points
x_values = [-2, -1, 0, 1, 2]
print("x\tf(x)\tg(x)\th(x)")
print("-" * 25)
for x in x_values:
print(f"{x}\t{f(x)}\t{g(x)}\t{h(x):.3f}")

#Plot multiple functions
x_plot = np.linspace(-3, 3, 100)
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.plot(x_plot, 2*x_plot + 3, 'r-')
plt.title('f(x) = 2x + 3')
plt.grid(True)

plt.subplot(1, 3, 2)
plt.plot(x_plot, x_plot**2 - 1, 'g-')
plt.title('g(x) = x² - 1')
plt.grid(True)

plt.subplot(1, 3, 3)
plt.plot(x_plot, np.sin(x_plot), 'b-')
plt.title('h(x) = sin(x)')
plt.grid(True)

plt.tight_layout()
plt.show()
```
---

## Day 4 (1.5 hours): Applied Problems and Review

### Step 1: Real-World Applications (45 minutes)

Create notebook: "Week1-Applications.ipynb"

**Exercise Set 7: Mathematical Modeling**
```
#Problem 1: Area calculations
def rectangle_area(length, width):
return length * width

def circle_area(radius):
return math.pi * radius**2

def triangle_area(base, height):
return 0.5 * base * height

#Calculate areas for specific measurements
rect_area = rectangle_area(5, 3)
circ_area = circle_area(2.5)
tri_area = triangle_area(4, 6)

print(f"Rectangle (5×3): {rect_area} square units")
print(f"Circle (r=2.5): {circ_area:.2f} square units")
print(f"Triangle (b=4, h=6): {tri_area} square units")

#Problem 2: Temperature conversion
def celsius_to_fahrenheit(celsius):
return (celsius * 9/5) + 32

def fahrenheit_to_celsius(fahrenheit):
return (fahrenheit - 32) * 5/9

#Convert temperatures
temps_c =
print("\nTemperature Conversions:")
print("Celsius\tFahrenheit")
print("-" * 18)
for temp in temps_c:
f_temp = celsius_to_fahrenheit(temp)
print(f"{temp}°C\t{f_temp}°F")

#Problem 3: Compound interest
def compound_interest(principal, rate, time, compounds_per_year=1):
return principal * (1 + rate/compounds_per_year)**(compounds_per_year * time)

#Calculate investment growth
initial = 1000 # $1000
rate = 0.05 # 5% annual interest
years = 10
final_amount = compound_interest(initial, rate, years)
print(f"\nInvestment: ${initial} at {rate*100}% for {years} years")
print(f"Final amount: ${final_amount:.2f}")
print(f"Interest earned: ${final_amount - initial:.2f}")
```
### Step 2: Practice Problem Set (45 minutes)

**Exercise Set 8: Mixed Practice Problems**

Solve these problems both algebraically and computationally:
```
#Problem Set for Week 1 Review
print("=== WEEK 1 PRACTICE PROBLEMS ===\n")

1. Linear Equations
print("1. Solve: 4x - 7 = 2x + 9")

#Algebraic steps: 4x - 2x = 9 + 7 → 2x = 16 → x = 8
x = sp.Symbol('x')
eq = sp.Eq(4x - 7, 2x + 9)
sol = sp.solve(eq, x)
print(f" Solution: x = {sol}")
print(f" Check: 4({sol}) - 7 = {4sol - 7}, 2({sol}) + 9 = {2sol + 9}\n")

#2. Quadratic Equations
print("2. Solve: x² + 3x - 10 = 0")
eq2 = x2 + 3*x - 10
solutions = sp.solve(eq2, x)
print(f" Solutions: x = {solutions}")
for s in solutions:
check = s2 + 3*s - 10
print(f" Check x = {s}: ({s})² + 3({s}) - 10 = {check}")
print()

#3. Function Evaluation
print("3. If f(x) = x³ - 2x + 1, find f(-2), f(0), f(3)")
def f(x):
return x**3 - 2*x + 1

test_values = [-2, 0, 3]
for val in test_values:
result = f(val)
print(f" f({val}) = {result}")
print()

#4. Distance Formula
print("4. Find distance between points (3, 4) and (7, 1)")
def distance(x1, y1, x2, y2):
return math.sqrt((x2-x1)**2 + (y2-y1)**2)

d = distance(3, 4, 7, 1)
print(f" Distance = √[(7-3)² + (1-4)²] = √[16 + 9] = √25 = {d}")
print()

#5. Percentage Problems
print("5. What is 15% of 240? What percent is 36 of 150?")
percent_of = 0.15 * 240
what_percent = (36 / 150) * 100
print(f" 15% of 240 = {percent_of}")
print(f" 36 is {what_percent}% of 150")
```
---

## Day 5-7 (30 minutes each): Consolidation and Preparation

### Additional Practice Resources

**Free Worksheets for Self-Study**:
- Kuta Software Basic Algebra: https://www.kutasoftware.com/freeipa.html
- Math Salamanders Basic Algebra: https://www.math-salamanders.com/basic-algebra-worksheets.html
- w3resource Python Math Exercises: https://www.w3resource.com/python-exercises/math/

### Daily Mini-Exercises (15 minutes each)

**Day 5: Pattern Recognition**
```
# Find patterns and express algebraically
sequences = [
    [2, 4, 6, 8, 10],      # 2n
    [1, 4, 9, 16, 25],     # n²
    [3, 6, 12, 24, 48],    # 3×2^(n-1)
    [1, 3, 6, 10, 15]      # n(n+1)/2
]

for i, seq in enumerate(sequences):
    print(f"Sequence {i+1}: {seq}")
    # Try to find the pattern and express it as a function
```

**Day 6: Graphing Practice**
```
# Create a gallery of basic function graphs
functions = [
    ("Linear", lambda x: 2*x + 1),
    ("Quadratic", lambda x: x**2 - 3),
    ("Cubic", lambda x: x**3 - x),
    ("Square Root", lambda x: np.sqrt(np.abs(x))),
    ("Exponential", lambda x: np.exp(x/2)),
    ("Logarithmic", lambda x: np.log(np.abs(x) + 1))
]

x = np.linspace(-3, 3, 100)
fig, axes = plt.subplots(2, 3, figsize=(15, 10))
axes = axes.flatten()

for i, (name, func) in enumerate(functions):
    axes[i].plot(x, func(x))
    axes[i].set_title(name)
    axes[i].grid(True)
    axes[i].set_xlabel('x')
    axes[i].set_ylabel('y')

plt.tight_layout()
plt.show()
```

**Day 7: Week Review Challenge*
```
# Challenge Problems for Week 1
print("=== WEEK 1 CHALLENGE PROBLEMS ===")

# Challenge 1: Create a function that solves any quadratic equation
def solve_quadratic(a, b, c):
    """Solve ax² + bx + c = 0"""
    discriminant = b**2 - 4*a*c
    if discriminant < 0:
        return "No real solutions"
    elif discriminant == 0:
        return [-b / (2*a)]
    else:
        sqrt_d = math.sqrt(discriminant)
        return [(-b + sqrt_d) / (2*a), (-b - sqrt_d) / (2*a)]

# Test your function
test_cases = [(1, -5, 6), (1, -2, 1), (1, 0, 1)]
for a, b, c in test_cases:
    solutions = solve_quadratic(a, b, c)
    print(f"{a}x² + {b}x + {c} = 0: {solutions}")

# Challenge 2: Plot multiple transformations of y = x²
x = np.linspace(-5, 5, 100)
transformations = [
    ("Original", lambda x: x**2),
    ("Shifted up", lambda x: x**2 + 2),
    ("Shifted right", lambda x: (x-1)**2),
    ("Stretched", lambda x: 2*x**2),
    ("Reflected", lambda x: -x**2)
]

plt.figure(figsize=(10, 6))
for name, func in transformations:
    plt.plot(x, func(x), label=name)
plt.legend()
plt.grid(True)
plt.title("Transformations of y = x²")
plt.show()
```
---

## Week 1 Assessment

### Self-Check Questions
At the end of Week 1, you should be able to:

1. **Python Setup**: 
   - ✅ Install and run Jupyter notebooks
   - ✅ Import and use mathematical libraries
   - ✅ Create basic plots

2. **Mathematical Concepts**:
   - ✅ Solve linear equations algebraically and computationally
   - ✅ Understand function notation and evaluation
   - ✅ Recognize basic mathematical patterns

3. **Problem Solving**:
   - ✅ Translate word problems into mathematical expressions
   - ✅ Verify solutions using multiple methods
   - ✅ Create visualizations of mathematical concepts

### Week 1 Self-Assessment Quiz
**Mini-Quiz (Test Yourself)***
```
# Week 1 Self-Assessment Quiz
# Try to solve these without looking at your notes first

print("WEEK 1 SELF-ASSESSMENT")
print("======================")

# Question 1: Solve 3(x + 2) = 15
# Question 2: If f(x) = x² + 3x - 1, find f(2)
# Question 3: Plot y = x² - 4x + 3 and identify its vertex
# Question 4: Convert 75°F to Celsius
# Question 5: Find the area of a circle with radius 3.5 units

# Work these out, then run the solutions below to check
```

### Creating an INTERACTIVE CHECKER
Create a single cell with this complete interactive system:
```
# COMPLETE INTERACTIVE CHECKER - Copy this entire block
import math

class QuizChecker:
    def __init__(self):
        # Correct answers (hidden in the class)
        self._answers = {
            1: 3,           # 3(x+2)=15 → x=3
            2: 9,           # f(2) where f(x)=x²+3x-1
            3: (2, -1),     # vertex of y=x²-4x+3
            4: 23.9,        # 75°F to Celsius
            5: 38.48        # area of circle r=3.5
        }
        self.score = 0
    
    def check_q1(self, x_value):
        """Check: Solve 3(x + 2) = 15"""
        if abs(x_value - self._answers[1]) < 0.01:
            print("✅ Question 1: CORRECT!")
            self.score += 1
        else:
            print("❌ Question 1: Try again!")
            print("Hint: Expand 3(x+2), then solve for x")
    
    def check_q2(self, f_of_2):
        """Check: f(2) where f(x) = x² + 3x - 1"""
        if abs(f_of_2 - self._answers[2]) < 0.01:
            print("✅ Question 2: CORRECT!")
            self.score += 1
        else:
            print("❌ Question 2: Try again!")
            print("Hint: f(2) = (2)² + 3(2) - 1")
    
    def check_q3(self, x_vertex, y_vertex):
        """Check: Vertex of y = x² - 4x + 3"""
        correct_x, correct_y = self._answers[3]
        x_ok = abs(x_vertex - correct_x) < 0.01
        y_ok = abs(y_vertex - correct_y) < 0.01
        
        if x_ok and y_ok:
            print("✅ Question 3: CORRECT!")
            self.score += 1
        else:
            print("❌ Question 3: Try again!")
            if not x_ok:
                print("Hint: x-coordinate = -b/(2a) where a=1, b=-4")
            if not y_ok:
                print("Hint: Substitute x-coordinate back into equation")
    
    def check_q4(self, celsius):
        """Check: 75°F to Celsius"""
        if abs(celsius - self._answers[4]) < 0.1:
            print("✅ Question 4: CORRECT!")
            self.score += 1
        else:
            print("❌ Question 4: Try again!")
            print("Hint: C = (F - 32) × 5/9")
    
    def check_q5(self, area):
        """Check: Area of circle with radius 3.5"""
        if abs(area - self._answers[5]) < 0.1:
            print("✅ Question 5: CORRECT!")
            self.score += 1
        else:
            print("❌ Question 5: Try again!")
            print("Hint: A = πr²")
    
    def final_score(self):
        print(f"\n🎯 Final Score: {self.score}/5")
        if self.score == 5:
            print("🎉 Perfect! Ready for Week 2!")
        elif self.score >= 4:
            print("👍 Great job! Review any missed questions.")
        elif self.score >= 3:
            print("👌 Good start! Practice the concepts you missed.")
        else:
            print("📚 Keep studying! Review Week 1 materials.")

# Initialize the checker
checker = QuizChecker()
print("🧮 Week 1 Quiz Checker Ready!")
print("Use checker.check_q1(your_answer) to check each question")
print("-" * 50)
```
Now use it like this
```
# Question 1: Solve 3(x + 2) = 15
# Work it out on paper first, then check:
checker.check_q1(3)  # Replace 3 with your answer

# Question 2: If f(x) = x² + 3x - 1, find f(2)
checker.check_q2(9)  # Replace 9 with your answer

# Question 3: Vertex of y = x² - 4x + 3
checker.check_q3(2, -1)  # Replace with your (x, y) coordinates

# Question 4: Convert 75°F to Celsius
checker.check_q4(23.9)  # Replace with your answer

# Question 5: Area of circle with radius 3.5
checker.check_q5(38.48)  # Replace with your answer

# Get final score
checker.final_score()
```

### Next Week Preparation
- Ensure all notebooks are organized and saved
- Review any concepts that felt challenging
- Make sure your Python environment is working smoothly
- Get excited for functions and trigonometry in Week 2!

This detailed Week 1 guide provides approximately 5-6 hours of structured learning, combining theoretical understanding with practical coding skills. Each exercise builds upon the previous one, creating a solid foundation for your mathematical journey ahead.
