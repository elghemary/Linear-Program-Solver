# LP Solver

**Projet Recherche Opérationnelle**

## Project Overview
This project is an interactive Python application for solving **Linear Programming (LP)** problems with two variables using the **Simplex / HiGHS** algorithm from SciPy. It is designed for educational and practical use, providing a graphical interface for easy input and visualization of LP problems.

![Application Interface](https://github.com/elghemary/Linear-Program-Solver/blob/main/Images/1.png?raw=true)

The tool is ideal for:
- Students learning about linear programming and optimization
- Teachers demonstrating LP concepts in class
- Anyone needing to quickly solve and visualize small LP problems

## Mathematical Formulation
The application solves problems of the form:

      Maximize:   Z = c₁·x₁ + c₂·x₂
      Subject to: a₁·x₁ + a₂·x₂ ≤ b   (for each constraint)
                        x₁ ≥ 0, x₂ ≥ 0

Where:
- **c₁, c₂**: Objective function coefficients
- **a₁, a₂, b**: Constraint coefficients and right-hand side
- Up to 5 constraints can be entered

## How the GUI Works
The graphical interface is built with Tkinter and includes:
- **Objective Function Inputs:** Enter c₁ and c₂
- **Constraint Table:** Up to 5 rows for a₁, a₂, b (leave unused rows blank)
- **Preset Dropdown:** Load example problems for quick testing
- **Buttons:**
   - **Solve:** Compute the optimal solution
   - **Plot (2D):** Visualize constraints and solution (if matplotlib is installed)
   - **Clear:** Reset all fields
   - **Help:** Show usage instructions
- **Result Box:** Displays solution, solver status, and iteration count

## Example Problem
Suppose you want to solve:

      Maximize Z = 3x₁ + 2x₂
      Subject to:
            x₁ + 2x₂ ≤ 18
            2x₁ + x₂ ≤ 14
            x₁ ≥ 0, x₂ ≥ 0

**Steps:**
1. Enter `3` for c₁ and `2` for c₂
2. Enter `1`, `2`, `18` in the first constraint row
3. Enter `2`, `1`, `14` in the second constraint row
4. Click **Solve** to see the optimal solution
5. Click **Plot (2D)** to visualize

![Solution and Graph](https://github.com/elghemary/Linear-Program-Solver/blob/main/Images/2.png?raw=true)

## Presets
The app includes several built-in example problems (presets) for quick demonstration. Select a preset from the dropdown and click **Load** to auto-fill the fields.

![Built-in Example Problems](https://github.com/elghemary/Linear-Program-Solver/blob/main/Images/3.png?raw=true)

## Troubleshooting & Tips
- If you see an error, check that all coefficients are numbers and at least one constraint is entered.
- All constraints must be of the ≤ type.
- The plot feature requires matplotlib. If the button is disabled, install matplotlib with `pip install matplotlib`.
- For infeasible or unbounded problems, the solver will display a warning.

## Customization
- You can add or modify presets in the `DEFAULT_PRESETS` dictionary in `app_gui.py`.
- The code can be extended to support more variables, different constraint types, or additional solver options.

## Folder Structure

```
LP_Solver_Project/
├── app_gui.py           # Main GUI + solver code
├── requirements.txt     # Library dependencies
├── README.md            # Documentation
```

## Features

- Solves problems of the form  
  **Maximize:** `Z = c1*x1 + c2*x2`  
  **Subject to:** `a1*x1 + a2*x2 ≤ b`
- Supports up to **five constraints**
- Enforces non-negativity: `x1 ≥ 0`, `x2 ≥ 0`
- Displays:
  - Optimal values of `x1`, `x2`
  - Maximum value `Zmax`
  - Iteration count and solver status
- Optional **2D plot** of constraints and the optimal point

## Installation and Execution

1. **Open a terminal** and navigate to the project folder:
   ```bash
   cd "/path/to/LP_Solver_Project"
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate      # macOS / Linux
   .venv\Scripts\Activate         # Windows
   ```

3. **Install required libraries:**
   ```bash
   pip install numpy scipy matplotlib
   ```

4. **Run the application:**
   ```bash
   python app_gui.py
   ```

The application window will open automatically.

## How to Use

1. Enter the coefficients **c1** and **c2** of the objective function.  
2. Fill in each constraint row with coefficients **a1**, **a2**, and the constant **b** for `a1*x1 + a2*x2 ≤ b`.  
   Leave unused rows blank.  
3. Click **Solve** to compute the optimal solution.  
4. Click **Plot (2D)** to visualize the constraints and optimal point.  
5. Click **Clear** to reset all inputs.

## Limitations

- Only **two decision variables** (`x1`, `x2`) for visualization simplicity  
- Constraints must be **≤ type**  
- All variables are **non-negative**  
- No integer or binary decisions  
- Does not display the simplex tableau steps  
- No sensitivity or duality analysis  
- Large coefficients may lead to numerical warnings  
- The 2D plot shows constraint lines and the optimum but not the shaded region

## Technologies Used

- **Python 3.10+**
- **tkinter** – graphical interface  
- **SciPy** – `scipy.optimize.linprog` solver  
- **NumPy** – numerical operations  
- **Matplotlib** – 2D plotting (optional)  
- **PyInstaller** – packaging into `.exe`  
