# Week 2: Functions and Their Behavior - Detailed Step-by-Step Guide

## Overview
This week focuses on understanding function concepts deeply, visualizing function transformations, and connecting algebraic and graphical representations. You'll work with MIT lectures, 3Blue1Brown videos, and Python programming to build a solid foundation in functions and limits.

## Learning Goals
- **Conceptual Understanding**: Develop deep understanding of function concepts
- **Visual Learning**: Visualize function transformations and their behavior
- **Mathematical Connections**: Connect algebraic and graphical representations
- **Computational Skills**: Implement functions in Python with advanced plotting

## Prerequisites
- Python environment set up with NumPy, Matplotlib, SymPy
- Basic understanding of algebra from Week 1
- Familiarity with coordinate planes
- **Required**: Week 2 Practice Exercises file (accompanying this guide)

---

## Daily Breakdown

### **Day 1: Function Fundamentals and Limits Introduction**

#### Morning Study (1.5-2 hours)
1. **Watch MIT 18.01 Lecture 2: Limits and Continuity**
   - URL: https://www.youtube.com/watch?v=ryLdyDrBfvI
   - Focus on understanding the concept of limits
   - Take detailed notes on discontinuities and their types

2. **Review Function Basics**
   - Study function evaluation and notation concepts
   - **Practice**: Complete Day 1 Exercises 1-6 from Week 2 Practice Exercises
   - Focus on function evaluation problems (20 problems total)

#### Afternoon Practical Work (1.5 hours)
3. **Python Setup and Basic Functions**
   ```python
   import numpy as np
   import matplotlib.pyplot as plt
   import sympy as sp

   # Define your first Python function
   def f(x):
       return x**2 + 2*x + 1

   # Plot the function
   x = np.linspace(-5, 3, 100)
   y = f(x)
   plt.plot(x, y)
   plt.title('My First Function: f(x) = x² + 2x + 1')
   plt.grid(True)
   plt.show()
   ```

4. **Practice Problems**
   - **Domain and Range**: Complete Day 1 Exercises 7-9 from Practice Exercises (15 problems)
   - **Function Notation**: Complete Day 1 Exercises 10-11 from Practice Exercises (10 problems)
   - Use Python to verify your solutions

#### Resources:
- MIT 18.01 Lecture 2: https://www.youtube.com/watch?v=ryLdyDrBfvI
- Week 2 Practice Exercises: Day 1 problems (45 total problems)

---

### **Day 2: Function Transformations and Behavior**

#### Morning Study (2 hours)
1. **3Blue1Brown Functions Content**
   - Watch any function-related videos from the 3Blue1Brown catalog
   - Focus on visual understanding of function behavior

2. **Study Function Transformations**
   - Review transformation concepts: shifts, stretches, reflections
   - **Practice**: Complete Day 2 Exercises 12-17 from Practice Exercises
   - Focus on identifying transformations (25 problems)

#### Afternoon Implementation (2 hours)
3. **Python Function Transformations**
   ```python
   import matplotlib.pyplot as plt
   import numpy as np

   def parent_function(x):
       return x**2

   def transformed_function(x, a=1, b=0, h=0, k=0):
       """
       General transformation: f(x) = a(bx - h) + k
       a: vertical stretch/compression
       b: horizontal stretch/compression
       h: horizontal shift
       k: vertical shift
       """
       return a * (b * (x - h))**2 + k

   x = np.linspace(-5, 5, 100)

   # Plot multiple transformations
   plt.figure(figsize=(12, 8))
   plt.plot(x, parent_function(x), 'b-', label='f(x) = x²', linewidth=2)
   plt.plot(x, transformed_function(x, a=2), 'r-', label='f(x) = 2x²')
   plt.plot(x, transformed_function(x, h=2), 'g-', label='f(x) = (x-2)²')
   plt.plot(x, transformed_function(x, k=3), 'm-', label='f(x) = x² + 3')
   plt.legend()
   plt.grid(True)
   plt.title('Function Transformations')
   plt.show()
   ```

4. **Practice Exercises**
   - **Graph Sketching**: Complete Day 2 Exercises 18-20 from Practice Exercises (15 problems)
   - Practice transformation problems
   - Use Python to verify your sketches

#### Resources:
- Week 2 Practice Exercises: Day 2 problems (40 total problems)
- Interactive visualization tools for verification

---

### **Day 3: MIT Lecture 3 and Advanced Function Analysis**

#### Morning Study (2 hours)
1. **Watch MIT 18.01 Lecture 3: Continuity**
   - Available in the MIT 18.01 playlist: https://www.youtube.com/playlist?list=PL590CCC2BC5AF3BC1
   - Focus on continuity concepts and applications

2. **Study "Doing Math with Python" Chapter 2**
   - Read sections on graphing and visualization
   - Focus on creating graphs with mathematical functions

#### Afternoon Coding (2 hours)
3. **Advanced Function Plotting**
   ```python
   import numpy as np
   import matplotlib.pyplot as plt
   import sympy as sp

   # Define symbolic variables
   x = sp.Symbol('x')

   # Create various function types
   functions = {
       'Linear': x + 2,
       'Quadratic': x**2 - 4*x + 3,
       'Cubic': x**3 - 3*x**2 + 2,
       'Rational': (x**2 - 1)/(x - 2),
       'Exponential': sp.exp(x),
       'Logarithmic': sp.log(x),
       'Trigonometric': sp.sin(x)
   }

   # Plot all functions
   fig, axes = plt.subplots(2, 4, figsize=(16, 8))
   axes = axes.flatten()

   for i, (name, func) in enumerate(functions.items()):
       # Convert to numpy function for plotting
       f_lambdified = sp.lambdify(x, func, 'numpy')

       if name == 'Logarithmic':
           x_vals = np.linspace(0.1, 10, 100)
       elif name == 'Rational':
           x_vals = np.linspace(-5, 5, 1000)
           x_vals = x_vals[np.abs(x_vals - 2) > 0.1]  # Remove discontinuity
       else:
           x_vals = np.linspace(-5, 5, 100)

       try:
           y_vals = f_lambdified(x_vals)
           axes[i].plot(x_vals, y_vals)
           axes[i].set_title(f'{name}: {func}')
           axes[i].grid(True)
           axes[i].set_ylim(-10, 10)
       except:
           axes[i].text(0.5, 0.5, f'Error plotting\n{name}',
                       ha='center', va='center', transform=axes[i].transAxes)

   plt.tight_layout()
   plt.show()
   ```

4. **Practice Problems**
   - **Function Composition**: Complete Day 3 Exercises 21-24 from Practice Exercises (20 problems)
   - **Inverse Functions**: Complete Day 3 Exercises 25-26 from Practice Exercises (15 problems)
   - **Piecewise Functions**: Complete Day 3 Exercises 27-28 from Practice Exercises (10 problems)

#### Resources:
- MIT 18.01 Playlist: https://www.youtube.com/playlist?list=PL590CCC2BC5AF3BC1
- Doing Math with Python (free): https://www.kea.nu/files/textbooks/humblepy/doingmathwithpython.pdf
- Week 2 Practice Exercises: Day 3 problems (45 total problems)

---

### **Day 4: Limits and Numerical Analysis**

#### Morning Theory (2 hours)
1. **Deep Dive into Limits**
   - Study limit concepts from MIT lectures
   - Review trigonometric limits (sin(x)/x, etc.)
   - **Practice**: Complete Day 4 Exercises 29-33 from Practice Exercises
   - Focus on basic limit evaluation (30 problems)

2. **One-Sided Limits**
   - Study one-sided limit concepts
   - **Practice**: Complete Day 4 Exercises 34-35 from Practice Exercises (15 problems)

#### Afternoon Computation (2 hours)
3. **Numerical Limits with SymPy**
   ```python
   import sympy as sp
   import numpy as np
   import matplotlib.pyplot as plt

   x = sp.Symbol('x')

   # Famous limits
   limits_to_study = [
       (sp.sin(x)/x, 0, "sin(x)/x as x→0"),
       ((1-sp.cos(x))/x, 0, "(1-cos(x))/x as x→0"),
       ((1 + 1/x)**x, sp.oo, "(1+1/x)^x as x→∞"),
       ((x**2 - 1)/(x - 1), 1, "(x²-1)/(x-1) as x→1"),
       (sp.exp(x)/x, sp.oo, "e^x/x as x→∞")
   ]

   print("Calculating Famous Limits:")
   print("=" * 40)

   for expr, point, description in limits_to_study:
       try:
           limit_value = sp.limit(expr, x, point)
           print(f"{description}: {limit_value}")

           # Numerical verification
           if point == 0:
               test_values = [0.1, 0.01, 0.001, 0.0001]
           elif point == 1:
               test_values = [1.1, 1.01, 1.001, 1.0001]
           elif point == sp.oo:
               test_values = [10, 100, 1000, 10000]

           f_lambdified = sp.lambdify(x, expr, 'numpy')
           print("Numerical verification:")
           for val in test_values:
               try:
                   result = f_lambdified(val)
                   print(f"  f({val}) = {result:.6f}")
               except:
                   print(f"  f({val}) = undefined")
           print()
       except Exception as e:
           print(f"Error calculating {description}: {e}")
           print()
   ```

4. **Visualization of Limits**
   ```python
   def visualize_limit(expr, point, range_around_point=2):
       x = sp.Symbol('x')
       f = sp.lambdify(x, expr, 'numpy')

       if point == sp.oo:
           x_vals = np.linspace(1, 100, 1000)
       else:
           x_vals = np.linspace(point - range_around_point,
                               point + range_around_point, 1000)
           # Remove the point if it causes division by zero
           x_vals = x_vals[np.abs(x_vals - float(point)) > 0.001]

       try:
           y_vals = f(x_vals)

           plt.figure(figsize=(10, 6))
           plt.plot(x_vals, y_vals, 'b-', linewidth=2)

           if point != sp.oo:
               plt.axvline(x=float(point), color='r', linestyle='--', alpha=0.7)
               limit_val = sp.limit(expr, x, point)
               if limit_val.is_finite:
                   plt.axhline(y=float(limit_val), color='g', linestyle='--', alpha=0.7)
                   plt.title(f'Function: {expr}\nLimit as x→{point} = {limit_val}')
               else:
                   plt.title(f'Function: {expr}\nLimit as x→{point} = {limit_val}')
           else:
               plt.title(f'Function: {expr}\nLimit as x→∞')

           plt.grid(True)
           plt.xlabel('x')
           plt.ylabel('f(x)')
           plt.show()
       except Exception as e:
           print(f"Error plotting: {e}")

   # Visualize the famous sin(x)/x limit
   visualize_limit(sp.sin(x)/x, 0, 3)
   ```

5. **Continuity Practice**
   - **Practice**: Complete Day 4 Exercises 36-38 from Practice Exercises (20 problems)

#### Resources:
- SymPy Limits Tutorial: https://docs.sympy.org/latest/tutorial/calculus.html
- Week 2 Practice Exercises: Day 4 problems (65 total problems)

---

### **Day 5: Interactive Function Exploration**

#### Morning Projects (2 hours)
1. **Create Interactive Function Explorer**
   ```python
   import matplotlib.pyplot as plt
   import numpy as np
   from matplotlib.widgets import Slider

   # Create interactive function transformation tool
   def interactive_function_transformer():
       fig, ax = plt.subplots(figsize=(12, 8))
       plt.subplots_adjust(bottom=0.35)

       # Initial parameters
       x = np.linspace(-10, 10, 1000)
       a_init, b_init, h_init, k_init = 1, 1, 0, 0

       def f(x, a, b, h, k):
           return a * (b * (x - h))**2 + k

       line, = ax.plot(x, f(x, a_init, b_init, h_init, k_init), 'b-', linewidth=2)
       ax.set_xlim([-10, 10])
       ax.set_ylim([-20, 20])
       ax.grid(True)
       ax.set_title('Interactive Function Transformer: f(x) = a(b(x-h))² + k')

       # Create sliders
       ax_a = plt.axes([0.1, 0.25, 0.8, 0.03])
       ax_b = plt.axes([0.1, 0.20, 0.8, 0.03])
       ax_h = plt.axes([0.1, 0.15, 0.8, 0.03])
       ax_k = plt.axes([0.1, 0.10, 0.8, 0.03])

       slider_a = Slider(ax_a, 'a (vertical stretch)', -3, 3, valinit=a_init)
       slider_b = Slider(ax_b, 'b (horizontal compress)', 0.1, 3, valinit=b_init)
       slider_h = Slider(ax_h, 'h (horizontal shift)', -5, 5, valinit=h_init)
       slider_k = Slider(ax_k, 'k (vertical shift)', -10, 10, valinit=k_init)

       def update(val):
           a = slider_a.val
           b = slider_b.val
           h = slider_h.val
           k = slider_k.val
           line.set_ydata(f(x, a, b, h, k))
           ax.set_title(f'f(x) = {a:.1f}({b:.1f}(x-{h:.1f}))² + {k:.1f}')
           fig.canvas.draw()

       slider_a.on_changed(update)
       slider_b.on_changed(update)
       slider_h.on_changed(update)
       slider_k.on_changed(update)

       plt.show()

   # Note: This requires matplotlib with interactive backend
   print("Interactive function explorer created!")
   print("Adjust sliders to see real-time transformations")
   ```

2. **Function Analysis Tools**
   ```python
   def analyze_function(func_str):
       """Comprehensive function analysis tool"""
       x = sp.Symbol('x')
       try:
           func = sp.sympify(func_str)
           print(f"Analyzing function: f(x) = {func}")
           print("=" * 50)

           # Domain analysis
           print("1. DOMAIN ANALYSIS:")
           print("   (Checking for common domain restrictions)")

           # Check for division by zero
           denominators = []
           if func.as_numer_denom()[1] != 1:
               denom = func.as_numer_denom()[1]
               zeros = sp.solve(denom, x)
               if zeros:
                   print(f"   Division by zero at: x = {zeros}")
                   print(f"   Domain: All real numbers except {zeros}")
               else:
                   print("   No division by zero found")

           # Check for square roots
           if func.has(sp.sqrt):
               print("   Contains square root - check for negative values")

           # Find critical points
           print("\n2. CRITICAL POINTS:")
           derivative = sp.diff(func, x)
           critical_points = sp.solve(derivative, x)
           print(f"   f'(x) = {derivative}")
           print(f"   Critical points: {critical_points}")

           # Find limits at infinity
           print("\n3. BEHAVIOR AT INFINITY:")
           limit_pos_inf = sp.limit(func, x, sp.oo)
           limit_neg_inf = sp.limit(func, x, -sp.oo)
           print(f"   lim(x→+∞) f(x) = {limit_pos_inf}")
           print(f"   lim(x→-∞) f(x) = {limit_neg_inf}")

           # Plot the function
           print("\n4. GENERATING PLOT...")
           x_vals = np.linspace(-10, 10, 1000)
           f_lambdified = sp.lambdify(x, func, 'numpy')

           try:
               y_vals = f_lambdified(x_vals)

               plt.figure(figsize=(12, 8))
               plt.plot(x_vals, y_vals, 'b-', linewidth=2)
               plt.title(f'f(x) = {func}')
               plt.xlabel('x')
               plt.ylabel('f(x)')
               plt.grid(True)

               # Mark critical points
               if critical_points:
                   for cp in critical_points:
                       if cp.is_real:
                           cp_val = float(cp)
                           if -10 <= cp_val <= 10:
                               y_cp = f_lambdified(cp_val)
                               plt.plot(cp_val, y_cp, 'ro', markersize=8)
                               plt.annotate(f'({cp_val:.1f}, {y_cp:.1f})',
                                          (cp_val, y_cp), xytext=(5, 5),
                                          textcoords='offset points')

               plt.show()
           except Exception as e:
               print(f"   Error plotting: {e}")

       except Exception as e:
           print(f"Error analyzing function: {e}")

   # Example usage
   test_functions = [
       "x**2 + 3*x - 4",
       "(x**2 - 1)/(x - 1)",
       "sin(x)/x",
       "exp(x)",
       "log(x)"
   ]

   print("Function Analysis Tool")
   print("Available test functions:")
   for i, func in enumerate(test_functions):
       print(f"{i+1}. {func}")

   # Analyze a sample function
   analyze_function("x**3 - 3*x**2 + 2")
   ```

#### Afternoon Practice (2 hours)
3. **Function Families Practice**
   - **Practice**: Complete Day 5 Exercises 39-41 from Practice Exercises (25 problems)
   - Focus on quadratic, rational, and absolute value functions

4. **Real-world Function Modeling**
   ```python
   # Model real-world scenarios with functions

   # 1. Projectile Motion
   def projectile_height(t, v0=50, h0=0):
       """Height of projectile at time t"""
       g = 9.81  # gravity
       return h0 + v0*t - 0.5*g*t**2

   # 2. Population Growth
   def population_growth(t, P0=1000, r=0.05):
       """Exponential population growth"""
       return P0 * np.exp(r * t)

   # 3. Temperature Change
   def temperature_change(t, T_ambient=20, T_initial=100, k=0.1):
       """Newton's law of cooling"""
       return T_ambient + (T_initial - T_ambient) * np.exp(-k * t)

   # Plot all models
   fig, axes = plt.subplots(1, 3, figsize=(15, 5))

   # Projectile motion
   t1 = np.linspace(0, 10, 100)
   h1 = [projectile_height(t) for t in t1]
   axes[0].plot(t1, h1)
   axes[0].set_title('Projectile Motion')
   axes[0].set_xlabel('Time (s)')
   axes[0].set_ylabel('Height (m)')
   axes[0].grid(True)

   # Population growth
   t2 = np.linspace(0, 50, 100)
   p2 = [population_growth(t) for t in t2]
   axes[1].plot(t2, p2)
   axes[1].set_title('Population Growth')
   axes[1].set_xlabel('Time (years)')
   axes[1].set_ylabel('Population')
   axes[1].grid(True)

   # Temperature change
   t3 = np.linspace(0, 30, 100)
   temp3 = [temperature_change(t) for t in t3]
   axes[2].plot(t3, temp3)
   axes[2].set_title('Cooling Process')
   axes[2].set_xlabel('Time (minutes)')
   axes[2].set_ylabel('Temperature (°C)')
   axes[2].grid(True)

   plt.tight_layout()
   plt.show()
   ```

5. **Function Analysis Challenge**
   - **Practice**: Complete Day 5 Exercises 42-44 from Practice Exercises (15 problems)

#### Resources:
- Matplotlib Interactive Examples: https://matplotlib.org/stable/gallery/widgets/
- Week 2 Practice Exercises: Day 5 problems (40 total problems)

---

### **Day 6: Advanced Applications and Modeling**

#### Morning Study (2 hours)
1. **Real-world Function Applications**
   - Study economics functions (supply/demand, cost/revenue)
   - Physics applications (motion, waves, decay)
   - Biology applications (population dynamics, enzyme kinetics)

2. **Advanced Function Types**
   ```python
   import numpy as np
   import matplotlib.pyplot as plt

   # Explore advanced function families
   x = np.linspace(-5, 5, 1000)

   # Rational functions
   def rational_function(x, a=1, b=1, c=1, d=1):
       return (a*x + b)/(c*x + d)

   # Piecewise functions
   def piecewise_function(x):
       return np.where(x < 0, x**2, np.where(x < 2, 2*x, -x + 6))

   # Absolute value functions
   def abs_function(x, a=1, h=0, k=0):
       return a * np.abs(x - h) + k

   # Step functions
   def step_function(x):
       return np.floor(x)

   # Create comprehensive plot
   fig, axes = plt.subplots(2, 2, figsize=(12, 10))

   # Rational function
   y1 = rational_function(x, 1, 2, 1, -1)
   # Remove discontinuities for plotting
   y1 = np.where(np.abs(x - 1) < 0.01, np.nan, y1)
   axes[0,0].plot(x, y1)
   axes[0,0].set_title('Rational: (x+2)/(x-1)')
   axes[0,0].set_ylim(-10, 10)
   axes[0,0].grid(True)

   # Piecewise function
   y2 = piecewise_function(x)
   axes[0,1].plot(x, y2)
   axes[0,1].set_title('Piecewise Function')
   axes[0,1].grid(True)

   # Absolute value function
   y3 = abs_function(x, 2, 1, -3)
   axes[1,0].plot(x, y3)
   axes[1,0].set_title('Absolute Value: 2|x-1|-3')
   axes[1,0].grid(True)

   # Step function
   y4 = step_function(x)
   axes[1,1].plot(x, y4, 'b-', linewidth=2)
   axes[1,1].set_title('Floor Function')
   axes[1,1].grid(True)

   plt.tight_layout()
   plt.show()
   ```

#### Afternoon Projects (2 hours)
3. **Function Optimization Problems**
   ```python
   # Optimization using functions and derivatives

   def optimization_example():
       """Find maximum area of rectangle with fixed perimeter"""
       x = sp.Symbol('x', positive=True)

       # Given: perimeter = 20, find dimensions for maximum area
       perimeter = 20
       width = x
       length = (perimeter - 2*x)/2
       area = width * length

       print("Optimization Problem: Maximum Rectangle Area")
       print(f"Perimeter = {perimeter}")
       print(f"Width = {width}")
       print(f"Length = {length}")
       print(f"Area = {area}")

       # Find critical points
       area_derivative = sp.diff(area, x)
       critical_points = sp.solve(area_derivative, x)

       print(f"\nArea derivative: {area_derivative}")
       print(f"Critical points: {critical_points}")

       # Evaluate area at critical point
       optimal_width = critical_points[0]
       optimal_length = length.subs(x, optimal_width)
       max_area = area.subs(x, optimal_width)

       print(f"\nOptimal dimensions:")
       print(f"Width = {optimal_width}")
       print(f"Length = {optimal_length}")
       print(f"Maximum area = {max_area}")

       # Plot area function
       x_vals = np.linspace(0.1, 9.9, 100)
       area_func = sp.lambdify(x, area, 'numpy')
       area_vals = area_func(x_vals)

       plt.figure(figsize=(10, 6))
       plt.plot(x_vals, area_vals, 'b-', linewidth=2)
       plt.plot(float(optimal_width), float(max_area), 'ro', markersize=10)
       plt.annotate(f'Maximum: ({float(optimal_width):.1f}, {float(max_area):.1f})',
                   (float(optimal_width), float(max_area)),
                   xytext=(10, 10), textcoords='offset points')
       plt.xlabel('Width')
       plt.ylabel('Area')
       plt.title('Area vs Width for Fixed Perimeter')
       plt.grid(True)
       plt.show()

   optimization_example()
   ```

4. **Function Composition and Inverse Functions**
   ```python
   # Function composition and inverses

   def function_composition_demo():
       x = sp.Symbol('x')

       # Define functions
       f = x**2 + 1
       g = 2*x - 3
       h = sp.sqrt(x)

       print("Function Composition Demo")
       print(f"f(x) = {f}")
       print(f"g(x) = {g}")
       print(f"h(x) = {h}")
       print()

       # Compositions
       fog = f.subs(x, g)  # f(g(x))
       gof = g.subs(x, f)  # g(f(x))
       foh = f.subs(x, h)  # f(h(x))

       print("Compositions:")
       print(f"(f∘g)(x) = f(g(x)) = {fog}")
       print(f"(g∘f)(x) = g(f(x)) = {gof}")
       print(f"(f∘h)(x) = f(h(x)) = {foh}")
       print()

       # Find inverse of f
       y = sp.Symbol('y')
       inverse_eq = sp.Eq(y, f)
       f_inverse = sp.solve(inverse_eq, x)

       print("Inverse Functions:")
       print(f"To find f⁻¹(x) where f(x) = {f}")
       print(f"Solve y = {f} for x")
       print(f"f⁻¹(x) = {f_inverse}")

       # Plot functions and their composition
       x_vals = np.linspace(-3, 3, 100)

       f_func = sp.lambdify(x, f, 'numpy')
       g_func = sp.lambdify(x, g, 'numpy')
       fog_func = sp.lambdify(x, fog, 'numpy')

       plt.figure(figsize=(12, 8))

       plt.subplot(2, 2, 1)
       plt.plot(x_vals, f_func(x_vals), 'b-', label='f(x)')
       plt.title('f(x) = x² + 1')
       plt.grid(True)
       plt.legend()

       plt.subplot(2, 2, 2)
       plt.plot(x_vals, g_func(x_vals), 'r-', label='g(x)')
       plt.title('g(x) = 2x - 3')
       plt.grid(True)
       plt.legend()

       plt.subplot(2, 2, 3)
       plt.plot(x_vals, fog_func(x_vals), 'g-', label='(f∘g)(x)')
       plt.title('(f∘g)(x) = f(g(x))')
       plt.grid(True)
       plt.legend()

       plt.subplot(2, 2, 4)
       plt.plot(x_vals, f_func(x_vals), 'b-', label='f(x)', alpha=0.7)
       # Plot inverse on same graph
       y_vals = f_func(x_vals)
       plt.plot(y_vals, x_vals, 'r--', label='f⁻¹(x)', alpha=0.7)
       plt.plot(x_vals, x_vals, 'k:', label='y=x', alpha=0.5)
       plt.title('Function and its Inverse')
       plt.grid(True)
       plt.legend()

       plt.tight_layout()
       plt.show()

   function_composition_demo()
   ```

5. **Applied Problems Practice**
   - **Practice**: Complete Day 6 Exercises 45-51 from Practice Exercises (35 problems)
   - Focus on modeling and real-world applications

#### Resources:
- Week 2 Practice Exercises: Day 6 problems (35 total problems)
- Optimization Problems: https://tutorial.math.lamar.edu/classes/calci/optimization.aspx

---

### **Day 7: Review and Assessment**

#### Morning Review (2 hours)
1. **Comprehensive Review Session**
   - Review all concepts from the week
   - Create summary notes for each day's learning
   - Identify areas that need more practice

2. **Self-Assessment Quiz**
   ```python
   # Create a self-assessment tool

   def self_assessment_quiz():
       """Interactive quiz for Week 2 concepts"""
       questions = [
           {
               'question': 'What is the domain of f(x) = 1/(x-2)?',
               'options': ['All real numbers', 'x ≠ 2', 'x > 0', 'x ≥ 2'],
               'correct': 1
           },
           {
               'question': 'What transformation does f(x-3) represent?',
               'options': ['Left 3', 'Right 3', 'Up 3', 'Down 3'],
               'correct': 1
           },
           {
               'question': 'What is lim(x→0) sin(x)/x?',
               'options': ['0', '1', '∞', 'undefined'],
               'correct': 1
           },
           {
               'question': 'If f(x)=x² and g(x)=x+1, what is (f∘g)(x)?',
               'options': ['x²+1', '(x+1)²', 'x²+x+1', 'x³+x²'],
               'correct': 1
           }
       ]

       score = 0
       total = len(questions)

       print("Week 2 Self-Assessment Quiz")
       print("=" * 30)

       for i, q in enumerate(questions):
           print(f"\nQuestion {i+1}: {q['question']}")
           for j, option in enumerate(q['options']):
               print(f"  {j}. {option}")

           # In a real implementation, you'd get user input
           # For demo, we'll show the correct answer
           print(f"Correct answer: {q['options'][q['correct']]}")
           print()

       print(f"Review complete! Make sure you understand all concepts.")

   self_assessment_quiz()
   ```

#### Afternoon Practice and Projects (2 hours)
3. **Final Projects and Challenges**
   ```python
   # Week 2 Capstone Project: Function Explorer Tool

   class FunctionExplorer:
       def __init__(self):
           self.functions = {}

       def add_function(self, name, expression):
           """Add a function to explore"""
           x = sp.Symbol('x')
           try:
               func = sp.sympify(expression)
               self.functions[name] = func
               print(f"Added function {name}: f(x) = {func}")
           except:
               print(f"Error: Could not parse expression '{expression}'")

       def analyze_all(self):
           """Analyze all stored functions"""
           if not self.functions:
               print("No functions to analyze. Add some first!")
               return

           x = sp.Symbol('x')
           fig, axes = plt.subplots(2, 2, figsize=(15, 10))
           axes = axes.flatten()

           for i, (name, func) in enumerate(self.functions.items()):
               if i >= 4:  # Only plot first 4 functions
                   break

               try:
                   # Create plot
                   x_vals = np.linspace(-10, 10, 1000)
                   f_lambdified = sp.lambdify(x, func, 'numpy')
                   y_vals = f_lambdified(x_vals)

                   axes[i].plot(x_vals, y_vals, linewidth=2)
                   axes[i].set_title(f'{name}: f(x) = {func}')
                   axes[i].grid(True)
                   axes[i].set_ylim(-20, 20)

                   # Add analysis
                   derivative = sp.diff(func, x)
                   print(f"\nAnalysis for {name}:")
                   print(f"  Function: f(x) = {func}")
                   print(f"  Derivative: f'(x) = {derivative}")

                   # Find critical points
                   critical_points = sp.solve(derivative, x)
                   if critical_points:
                       print(f"  Critical points: {critical_points}")

                   # Limits at infinity
                   limit_pos = sp.limit(func, x, sp.oo)
                   limit_neg = sp.limit(func, x, -sp.oo)
                   print(f"  lim(x→+∞): {limit_pos}")
                   print(f"  lim(x→-∞): {limit_neg}")

               except Exception as e:
                   axes[i].text(0.5, 0.5, f'Error plotting\n{name}',
                               ha='center', va='center', transform=axes[i].transAxes)
                   print(f"Error analyzing {name}: {e}")

           plt.tight_layout()
           plt.show()

   # Example usage
   explorer = FunctionExplorer()
   explorer.add_function("Quadratic", "x**2 - 4*x + 3")
   explorer.add_function("Rational", "(x-1)/(x+1)")
   explorer.add_function("Trigonometric", "sin(x)*cos(x)")
   explorer.add_function("Exponential", "exp(-x**2)")

   explorer.analyze_all()
   ```

4. **Week 2 Challenge Problems**
   - Create a function that models real-world data
   - Implement numerical limit calculator
   - Design function transformation visualizer
   - Build function composition tool

#### Final Assessment
5. **Complete Practice Exercises Review**
   - **Practice**: Complete Day 7 Exercises 52-59 from Practice Exercises (40 problems)
   - Work through comprehensive review and challenging applications
   - **Bonus**: Attempt Challenge Problems 60-62 from Practice Exercises (10 problems)

---

## Weekly Practice Problems Summary

### Complete Practice Exercises Distribution
- **Day 1**: 45 problems (Function evaluation, domain/range, notation)
- **Day 2**: 40 problems (Transformations, graph sketching)
- **Day 3**: 45 problems (Composition, inverses, piecewise)
- **Day 4**: 65 problems (Limits, continuity)
- **Day 5**: 40 problems (Function families, analysis)
- **Day 6**: 35 problems (Modeling, applications)
- **Day 7**: 50 problems (Review, assessment, challenges)

**Total**: 320+ practice problems organized by difficulty and topic

### Exercise Categories (as outlined in Practice Exercises file)
- **Conceptual Problems (30%)**: Focus on understanding
- **Computational Practice (40%)**: Python implementation and verification
- **Applied Problems (20%)**: Real-world applications
- **Review and Synthesis (10%)**: Connecting concepts

---

## Essential Resources

### Primary Learning Materials
- **MIT 18.01 Lectures 2-3**: https://www.youtube.com/playlist?list=PL590CCC2BC5AF3BC1
- **3Blue1Brown**: Function-related videos from catalog
- **Doing Math with Python**: Chapter 2 (free PDF available)
- **Week 2 Practice Exercises**: Complete problem sets with solutions

### Additional Tools
- **GeoGebra**: https://www.geogebra.org/graphing (for interactive function exploration)
- **Desmos Graphing Calculator**: https://www.desmos.com/calculator
- **SymPy Documentation**: https://docs.sympy.org/latest/tutorial/calculus.html

### Programming Resources
- **Matplotlib Gallery**: https://matplotlib.org/stable/gallery/
- **NumPy Documentation**: https://numpy.org/doc/stable/
- **Python Mathematical Computing**: https://patrickwalls.github.io/mathematicalpython/

---

## Success Tips for Week 2

1. **Visual First**: Always start with 3Blue1Brown videos for conceptual understanding
2. **Hands-on Coding**: Implement every concept in Python immediately after learning
3. **Progressive Complexity**: Start with simple functions, gradually increase complexity
4. **Connect Concepts**: Actively look for relationships between algebraic and graphical representations
5. **Practice Regularly**: Solve problems daily from the Practice Exercises file
6. **Document Learning**: Keep detailed notes with code examples and insights
7. **Ask Questions**: Use online forums and communities when stuck
8. **Review Daily**: Spend 15 minutes each day reviewing previous concepts

## Assessment Checklist

By the end of Week 2, you should be able to:
- [ ] Define and evaluate functions confidently
- [ ] Identify and apply function transformations
- [ ] Calculate limits both analytically and numerically
- [ ] Create comprehensive function visualizations in Python
- [ ] Analyze function behavior (domain, range, continuity)
- [ ] Model real-world situations using appropriate functions
- [ ] Use SymPy for symbolic function manipulation
- [ ] Connect graphical and algebraic representations
- [ ] Solve function composition and inverse problems
- [ ] Apply functions to optimization problems

This comprehensive guide provides a structured approach to mastering functions and their behavior. Remember to adapt the pace according to your learning style and spend extra time on challenging concepts. The combination of theoretical understanding, visual learning, practical implementation, and extensive practice through the Exercise file will give you a solid foundation for advanced calculus topics in the coming weeks.
