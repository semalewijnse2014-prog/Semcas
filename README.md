# SemCAS 11.1 — Dutch Edition

A lightweight Computer Algebra System (CAS) built on SymPy with a natural language interface in Dutch. Supports symbolic mathematics, equation solving, calculus, and step-by-step explanations.

## Features

- **Symbolic computation** using SymPy
- **Natural language Dutch commands** (e.g., `vereenvoudig`, `differentieer`, `integreer`)
- **Pythagorean theorem** solver (`pyth a=... b=... c=...`)
- **Angle mode** switching (radians/degrees)
- **Step-by-step explanations** using `leg ... uit`
- **Predefined variables**: `d` through `z` (a, b, c reserved for Pythagorean theorem)
- **Special constants**: `E` (Euler's number), `pi`, `phi` (golden ratio), `I` (imaginary unit), `oo` (infinity)

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.

## Installation

```bash
pip install sympy
```

## Usage

Run the script:

```bash
python semcas11-1_nl.py
```

Then enter commands at the `SemCAS>` prompt. Type `stop`, `exit`, or `quit` to exit.

## Commands Reference

### Basic Operations

| Command | Description | Example |
|---------|-------------|---------|
| `vereenvoudig <expr>` | Simplify an expression | `vereenvoudig (x^2 - 1)/(x - 1)` |
| `breid uit <expr>` | Expand an expression | `breid uit (x + 2)^2` |
| `expand <expr>` | Same as above (English) | `expand (x + 2)^2` |
| `factoriseer <expr>` | Factor an expression | `factoriseer x^2 - 4` |

### Calculus

| Command | Description | Example |
|---------|-------------|---------|
| `differentieer <expr>` | Differentiate with respect to variable | `differentieer x^3 + 2*x` |
| `integreer <expr>` | Integrate with respect to variable | `integreer x^2` |
| `wat is de limiet van <expr> als <var> naar <waarde> gaat` | Compute a limit | `wat is de limiet van sin(x)/x als x naar 0 gaat` |

### Equation Solving

| Command | Description | Example |
|---------|-------------|---------|
| `los <eq> op` | Solve equation | `los x^2 - 4 = 0 op` |
| `los <eq> op voor <var>` | Solve for specific variable | `los x^2 + y^2 = 25 op voor y` |

### Geometry

| Command | Description | Example |
|---------|-------------|---------|
| `pyth a=<val> b=<val> c=<val>` | Solve Pythagorean theorem (leave one unknown) | `pyth a=3 b=4` (finds c) |
| | | `pyth a=3 c=5` (finds b) |
| | | `pyth b=4 c=5` (finds a) |

### Angle Mode

| Command | Description | Example |
|---------|-------------|---------|
| `mode rad` | Set angle mode to radians (default) | `mode rad` |
| `mode deg` | Set angle mode to degrees | `mode deg` |

### Step-by-Step Explanations

| Command | Description | Example |
|---------|-------------|---------|
| `leg <expr> uit` | Show step-by-step simplification | `leg (x^2 - 1)/(x - 1) uit` |
| `leg vereenvoudig <expr> uit` | Alternative syntax | `leg vereenvoudig x^2 + 2*x + 1 uit` |

### Direct Evaluation

Any expression entered without a command will be simplified automatically.

**Examples:**
```
SemCAS> x^2 + 2*x + 1
x^2 + 2x + 1

SemCAS> sin(pi/2)
1

SemCAS> 2 + 3*4
14
```

## Variable System

- **Available variables**: `d`, `e`, `f`, `g`, `h`, `i`, `j`, `k`, `l`, `m`, `n`, `o`, `p`, `q`, `r`, `s`, `t`, `u`, `v`, `w`, `x`, `y`, `z`
- **Reserved variables** (for Pythagorean theorem only): `a`, `b`, `c`
- **Constants**: `E`, `pi`, `phi`, `I`, `oo`

## Syntax Tips

- Use `^` for exponentiation (converted to `**` internally)
- Multiplication is implicit between numbers and variables: `2x` → `2*x`
- Multiplication is implicit between variables: `xy` → `x*y`
- Use `=` for equations in `los` commands
- Use `oo` or `inf` for infinity in limits

## Examples

```
SemCAS> vereenvoudig (x^2 - 1)/(x - 1)
x + 1

SemCAS> breid uit (x + 2)^3
x^3 + 6x^2 + 12x + 8

SemCAS> differentieer x^3 * sin(x)
3x^2*sin(x) + x^3*cos(x)

SemCAS> los x^2 - 5*x + 6 = 0 op
2, 3

SemCAS> pyth a=3 b=4
5

SemCAS> wat is de limiet van sin(x)/x als x naar 0 gaat
1

SemCAS> leg (x^2 + 2*x + 1) uit
(x + 1)^2

Stap 1: Begin met de expressie: x^2 + 2x + 1.
Stap 2: Pas indien nodig de hoekmodus (rad/deg) toe.
Stap 3: Combineer gelijksoortige termen en vereenvoudig de structuur.
Stap 4: De vereenvoudigde vorm is: (x + 1)^2.

SemCAS> mode deg
Hoekmodus ingesteld op deg.

SemCAS> sin(90)
1
```

## Limitations

- Only variables `d` through `z` are available (a, b, c are reserved)
- Equation solving uses SymPy's `solve()` (works for algebraic equations)
- Step-by-step explanation is currently limited to simplification
- The `root` function may not work as expected in all cases

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Copyright

Copyright (C) 2026 SemCAS Contributors

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```
