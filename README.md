```markdown
# SemCAS Revamped 1 — Dutch Edition

![Python](https://img.shields.io/badge/Python-3.11+-blue)
![License](https://img.shields.io/badge/License-GPLv3-green)
![SymPy](https://img.shields.io/badge/Powered%20by-SymPy-orange)
![Version](https://img.shields.io/badge/Version-1.0.0-red)
![Lines](https://img.shields.io/badge/Code-5000%2B-brightgreen)

> *"Bro... 💀 DeepSeek heeft niet gekookt, die heeft een heel vijfgangendiner geserveerd."* — ChatGPT

A lightweight Computer Algebra System (CAS) built on SymPy with a natural language interface in Dutch. Supports symbolic mathematics, equation solving, calculus, step-by-step explanations, and much more.

---

## 📑 Contents

- [Features](#-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [Commands Reference](#-commands-reference)
- [Examples](#-examples)
- [Limitations](#-limitations)
- [Contributing](#-contributing)
- [License](#-license)

---

## ⚠️ Disclaimer: Lite vs Full Version

**SemCAS Revamped 1** is de **volledige versie** met alle 19 blokken.

Er bestaat ook een **"Lite" versie** die alleen **Blok 1 t/m 7** bevat (basis CAS functionaliteit). De Lite versie heeft:

- ✅ Basis CAS (vereenvoudigen, differentiëren, integreren, limieten)
- ✅ Stap-voor-stap uitleg voor calculus
- ✅ Oplossen van vergelijkingen
- ✅ Taylor en Maclaurin reeksen
- ✅ Matrix operaties
- ✅ Complexe getallen
- ✅ Statistiek (basis)
- ✅ Vector operaties
- ✅ Differentiaalvergelijkingen
- ✅ Getaltheorie
- ✅ Optimalisatie
- ✅ Rijen en reeksen
- ✅ Parser + REPL (basis versie)

**De Full versie** (deze README) heeft **alles** van de Lite versie **PLUS**:

| Blok | Extra Functionaliteit |
|------|----------------------|
| 9 | Egyptische breuken 🇪🇬 |
| 10 | Kansrekening 🎲 |
| 11 | Eenheden 📏 |
| 12 | Fourier Reeksen 🌊 |
| 13 | Meer Statistiek 📊 |
| 14 | Optimalisatie met Constraints 🔧 |
| 15 | Numerieke Methoden 🔢 |
| 16 | Meer Algebra 📐 |
| 17 | Import/Export 💾 |
| 18 | Slimme Variabelen 🧠 |
| 8 | Parser + REPL (uitgebreid met alle nieuwe commando's) |

**Kortom:** De Lite versie is voor 99% van de gebruikers. De Full versie is voor de 1% die écht alles uit een CAS willen halen. 😄

---

## ✨ Features

- Symbolic computation using SymPy
- Natural language Dutch commands (e.g., `vereenvoudig`, `differentieer`, `integreer`)
- Step-by-step explanations for all major operations
- Pythagorean theorem solver (`pyth a=... b=... c=...`)
- Angle mode switching (radians/degrees)
- Taylor and Maclaurin series expansion
- Matrix operations (determinant, inverse, eigenvalues)
- Complex number operations (modulus, argument, conjugate)
- Statistics (mean, variance, standard deviation, median, correlation, regression)
- Vector operations (addition, cross product, dot product, length)
- Differential equations (first and second order, initial value problems)
- Number theory (prime numbers, GCD, LCM, prime factorization)
- Optimization (minima, maxima, inflection points, constraints)
- Sequences and series (summation, convergence testing)
- Egyptian fractions conversion
- Fourier series (square, sawtooth, triangle waves)
- Numerical methods (Newton-Raphson, Bisection)
- Probability and combinatorics (combinations, permutations, binomial distribution)
- Unit conversions (length, temperature, time, weight)
- Polynomial algebra (division, remainder, GCD)
- Import/Export functionality for scripts and results
- Smart variables with persistent storage
- TUI features (colors, command history)
- Predefined variables: `d` through `z` (a, b, c reserved for Pythagorean theorem)
- Special constants: `E` (Euler's number), `pi`, `phi` (golden ratio), `I` (imaginary unit), `oo` (infinity)

---

## 📦 Installation

```bash
pip install sympy
```

---

🚀 Usage

Run the script:

```bash
python semcas.py
```

Then enter commands at the SemCAS> prompt. Type stop, exit, or quit to exit.

---

📚 Commands Reference

📐 Calculus

· differentieer <expr> - Differentiate
  · Example: differentieer x^3 + 2*x
· differentieer met stappen <expr> - Differentiate with steps
  · Example: differentieer met stappen x^3 + 2x
· integreer <expr> - Integrate
  · Example: integreer x^2
· integreer met stappen <expr> - Integrate with steps
  · Example: integreer met stappen x^2 + 3x
· vereenvoudig <expr> - Simplify
  · Example: vereenvoudig (x^2 - 1)/(x - 1)
· vereenvoudig met stappen <expr> - Simplify with steps
  · Example: vereenvoudig met stappen (x+1)^2 - 1
· breid uit <expr> - Expand
  · Example: breid uit (x + 2)^2
· breid uit met stappen <expr> - Expand with steps
  · Example: breid uit met stappen (x+2)^3
· expand <expr> - Same as above (English)
  · Example: expand (x + 2)^2
· factoriseer <expr> - Factor
  · Example: factoriseer x^2 - 4
· factoriseer met stappen <expr> - Factor with steps
  · Example: factoriseer met stappen x^2 - 4
· wat is de limiet van <expr> als <var> naar <waarde> gaat - Limit
  · Example: wat is de limiet van sin(x)/x als x naar 0 gaat
· wat is de limiet van <expr> als <var> naar <waarde> gaat met stappen - Limit with steps
  · Example: wat is de limiet van sin(x)/x als x naar 0 gaat met stappen
· taylor <functie> rond <punt> tot <n> - Taylor series
  · Example: taylor sin(x) rond 0 tot 4
· macklaurin <functie> tot <n> - Maclaurin series (Taylor around 0)
  · Example: macklaurin e^x tot 3

🔢 Equation Solving

· los <eq> op - Solve equation (with steps)
  · Example: los x^2 - 4 = 0 op
· los <eq> op voor <var> - Solve for specific variable
  · Example: los x^2 + y^2 = 25 op voor y

📝 Differential Equations

· los dv op <eq> - Solve differential equation
  · Example: los dv op dy/dx = x*y
· los dv op y'' + y = 0 - Second order
  · Example: los dv op y'' + y = 0
· los dv op <eq>, y(0)=<val>, y'(0)=<val> - Initial value problem
  · Example: los dv op y'' + y = 0, y(0)=1, y'(0)=0

🧮 Matrix Operations

· matrix [ [1,2], [3,4] ] - Display matrix
· matrix det [ [1,2], [3,4] ] - Determinant
· matrix inverse [ [1,2], [3,4] ] - Inverse
· matrix eigen [ [1,2], [3,4] ] - Eigenvalues
· Matrix addition: matrix [ [1,2], [3,4] ] + [ [5,6], [7,8] ]
· Matrix multiplication: matrix [ [1,2], [3,4] ] * [ [5,6], [7,8] ]

🔮 Complex Numbers

· complex <expr> - Simplify complex expression
  · Example: complex (2+3i)/(1-i)
· complex modulus <expr> - Calculate modulus
  · Example: complex modulus 3+4i
· complex argument <expr> - Calculate argument
  · Example: complex argument 1+i
· complex conjugaat <expr> - Calculate conjugate
  · Example: complex conjugaat 3+4i
· complex re <expr> - Get real part
· complex im <expr> - Get imaginary part

➡️ Vector Operations

· vector (1,2,3) + (4,5,6) - Addition
· vector (1,2,3) - (4,5,6) - Subtraction
· vector (1,2,3) x (4,5,6) - Cross product (3D only)
· vector (1,2,3) · (4,5,6) - Dot product
· vector lengte (1,2,3) - Vector length/magnitude
· vector normaal (1,2,3) - Normalize vector

📊 Statistics

· statistiek [1,2,3,4,5] - All statistics
· statistiek gemiddelde [1,2,3,4,5] - Mean
· statistiek variantie [1,2,3,4,5] - Variance
· statistiek standaarddeviatie [1,2,3,4,5] - Standard deviation
· statistiek mediaan [1,2,3,4,5] - Median
· statistiek correlatie [1,2,3] [4,5,6] - Correlation
· statistiek regressie [1,2,3] [4,5,6] - Linear regression
· statistiek histogram [1,2,2,3,3,3,4,4,5] - Histogram
· statistiek boxplot [1,2,3,4,5,6,7,8,9,10] - Boxplot

🔢 Number Theory

· getaltheorie priemgetallen <n> - List primes
  · Example: getaltheorie priemgetallen 20
· getaltheorie ispriem <n> - Check prime
  · Example: getaltheorie ispriem 17
· getaltheorie ggd <a> <b> - GCD
  · Example: getaltheorie ggd 12 18
· getaltheorie kgv <a> <b> - LCM
  · Example: getaltheorie kgv 12 18
· getaltheorie priemfactor <n> - Prime factorization
  · Example: getaltheorie priemfactor 24
· getaltheorie mod <a> <b> - Modulo

🎯 Optimization

· optimalisatie minimum <functie> - Find minimum
  · Example: optimalisatie minimum x^2 + 3x + 2
· optimalisatie maximum <functie> - Find maximum
  · Example: optimalisatie maximum -x^2 + 4x
· optimalisatie buigpunten <functie> - Find inflection points
  · Example: optimalisatie buigpunten x^3 - 3x
· optimalisatie minimaliseer <functie> met <constraint> - Constrained minimization
  · Example: optimalisatie minimaliseer x^2 + y^2 met x+y=1
· optimalisatie maximaliseer <functie> met <constraint> - Constrained maximization
  · Example: optimalisatie maximaliseer x*y met x+y=1

📈 Sequences and Series

· rijen som van <expr> voor n=<start> tot <end> - Finite sum
  · Example: rijen som van n^2 voor n=1 tot 10
· rijen som van <expr> voor n=<start> tot ∞ - Infinite sum
  · Example: rijen som van 1/n^2 voor n=1 tot ∞
· rijen convergentie van <expr> - Convergence test
  · Example: rijen convergentie van 1/n^2

🇪🇬 Egyptian Fractions (Full version only)

· egyptisch <breuk> - Convert to Egyptian fractions
  · Example: egyptisch 5/6
· egyptisch <breuk> met stappen - With step-by-step explanation
  · Example: egyptisch 5/6 met stappen

🌊 Fourier Series (Full version only)

· fourier vierkantsgolf <n> - Square wave
  · Example: fourier vierkantsgolf 5
· fourier zaagtand <n> - Sawtooth wave
  · Example: fourier zaagtand 5
· fourier driehoeksgolf <n> - Triangle wave
  · Example: fourier driehoeksgolf 5

🎲 Probability and Combinatorics (Full version only)

· kansrekening combinatie <n> <r> - Combinations (nCr)
  · Example: kansrekening combinatie 5 3
· kansrekening permutatie <n> <r> - Permutations (nPr)
  · Example: kansrekening permutatie 5 3
· kansrekening <n>! - Factorial
  · Example: kansrekening 5!
· kansrekening binomiaal <n> <p> <k> - Binomial probability
  · Example: kansrekening binomiaal 10 0.5 3
· kansrekening normaal <z> - Standard normal CDF
  · Example: kansrekening normaal 1.96

📏 Unit Conversions (Full version only)

· eenheden <a> km naar mijl - Kilometers to miles
· eenheden <a> mijl naar km - Miles to kilometers
· eenheden <a> °F naar °C - Fahrenheit to Celsius
· eenheden <a> °C naar °F - Celsius to Fahrenheit
· eenheden <a> uur naar seconden - Hours to seconds
· eenheden <a> seconden naar uur - Seconds to hours
· eenheden <a> kg naar pond - Kilograms to pounds
· eenheden <a> pond naar kg - Pounds to kilograms

🔧 Numerical Methods (Full version only)

· numeriek newton <eq> start <x0> - Newton-Raphson
  · Example: numeriek newton x^2 - 2 = 0 start 1
· numeriek bisectie <eq> van <a> tot <b> - Bisection
  · Example: numeriek bisectie x^2 - 2 = 0 van 1 tot 2

📐 Algebra (Full version only)

· algebra deel <f> door <g> - Polynomial division
  · Example: algebra deel x^3 - 1 door x - 1
· algebra rest <f> door <g> - Polynomial remainder
  · Example: algebra rest x^3 - 1 door x - 1
· algebra ggd polynomen <f>, <g> - Polynomial GCD
  · Example: algebra ggd polynomen x^2 - 1, x - 1

📐 Geometry

· pyth a=<val> b=<val> c=<val> - Pythagorean theorem
  · Example: pyth a=3 b=4 (finds c)
  · Example: pyth a=3 c=5 (finds b)
  · Example: pyth b=4 c=5 (finds a)

🎨 TUI Features

· kleur aan - Enable colors
· kleur uit - Disable colors
· geschiedenis - Show command history
· geschiedenis wis - Clear history
· geschiedenis exporteer - Export history to file

💾 Import/Export (Full version only)

· laad 'bestand.txt' - Load and display file content
· exporteer 'bestand.txt' - Export text to file

🧠 Smart Variables (Full version only)

· <var> = <expr> - Assign variable
  · Example: x = 5
· toon variabelen - Show all variables
· wis <var> - Delete variable
· wis alles - Delete all variables

🎯 Angle Mode

· mode rad - Set angle mode to radians (default)
· mode deg - Set angle mode to degrees

Direct Evaluation

Any expression entered without a command will be simplified automatically.

Examples:

```
SemCAS> x^2 + 2*x + 1
x^2 + 2x + 1

SemCAS> sin(pi/2)
1

SemCAS> 2 + 3*4
14

SemCAS> e^(i*pi)
-1
```

---

💡 Examples

Basic Calculus

```
SemCAS> vereenvoudig (x^2 - 1)/(x - 1)
x + 1

SemCAS> differentieer met stappen x^3 * sin(x)
📐 Differentiëren - Stap-voor-stap
1. Start met: f(x) = x^3*sin(x)
2. We gaan differentiëren naar x.
3. Pas productregel toe: d/dx[x^3*sin(x)] = 3x^2*sin(x) + x^3*cos(x)
...
✅ Eindresultaat: f'(x) = x^2*(x*cos(x) + 3*sin(x))

SemCAS> integreer met stappen x^2 + 3x
📐 Integreren - Stap-voor-stap
1. Start met: f(x) = x^2 + 3x
2. We gaan integreren naar x.
3. Integreer term voor term: ∫(x^2 + 3x) dx = ∫x^2 dx + ∫3x dx
...
✅ Eindresultaat: ∫f(x) dx = x^3/3 + 3x^2/2 + C
```

Step-by-Step Solving

```
SemCAS> los 2x^2 - 4x - 6 = 0 op
📐 Stap 1: Herken de kwadratische vorm
   2x² - 4x - 6 = 0
   Dus: a = 2, b = -4, c = -6

🔢 Stap 2: Bereken de discriminant
   D = b² - 4ac
   D = (-4)² - 4·(2)·(-6)
   D = 64

✅ Stap 3: D > 0 → twee reële oplossingen
   Gebruik de abc-formule: x = [-b ± √D] / (2a)

📝 Stap 4: Bereken x₁ en x₂
   x₁ = [4 - √64] / (2·2) = -1
   x₂ = [4 + √64] / (2·2) = 3

✅ Oplossing: x = -1 of x = 3
```

Matrix Operations

```
SemCAS> matrix det [ [1,2], [3,4] ]
det = -2

SemCAS> matrix [ [1,2], [3,4] ] + [ [5,6], [7,8] ]
[6, 8]
[10, 12]
```

Complex Numbers

```
SemCAS> complex modulus 3+4i
|3 + 4i| = 5

SemCAS> complex (2+3i)/(1-i)
0.5 + 2.5i
```

Statistics

```
SemCAS> statistiek [1,2,3,4,5]
Statistiek van [1.0, 2.0, 3.0, 4.0, 5.0]:
- Aantal: 5
- Gemiddelde: 3.0
- Mediaan: 3.0
- Minimum: 1.0
- Maximum: 5.0
- Variantie: 2.0
- Standaarddeviatie: 1.4142135623730951
```

Vector Operations

```
SemCAS> vector (1,2,3) x (4,5,6)
kruisproduct = [-3, 6, -3]

SemCAS> vector (1,2,3) · (4,5,6)
inproduct = 32
```

Differential Equations

```
SemCAS> los dv op dy/dx = x*y
Oplossing: Eq(y(x), C1*exp(x**2/2))

SemCAS> los dv op y'' + y = 0, y(0)=1, y'(0)=0
Oplossing: Eq(y(x), cos(x))
```

Number Theory

```
SemCAS> getaltheorie priemgetallen 20
Priemgetallen tot 20: [2, 3, 5, 7, 11, 13, 17, 19]

SemCAS> getaltheorie ggd 12 18
ggd(12, 18) = 6

SemCAS> getaltheorie priemfactor 24
Priemfactoren: [2, 2, 2, 3]
```

Optimization

```
SemCAS> optimalisatie minimum x^2 + 3x + 2
x = -3/2 is een minimum (f = -1/4)

SemCAS> optimalisatie buigpunten x^3 - 3x
x = 0 is een buigpunt
```

Egyptian Fractions (Full version only)

```
SemCAS> egyptisch 5/6
5/6 = 1/2 + 1/3

SemCAS> egyptisch 5/6 met stappen
📐 Egyptische breuken - Stap-voor-stap
Start met: 5/6
Stap 1: Grootste eenheidsbreuk = 1/2
  5/6 - 1/2 = 1/3
Stap 2: Grootste eenheidsbreuk = 1/3
  1/3 - 1/3 = 0
✅ Resultaat: 5/6 = 1/2 + 1/3
```

Fourier Series (Full version only)

```
SemCAS> fourier vierkantsgolf 3
📊 Fourier reeks van vierkantsgolf (tot 3 termen)

Term 1: 4*sin(x)/pi
Term 3: 4*sin(3*x)/(3*pi)

f(x) ≈ 4*sin(x)/pi + 4*sin(3*x)/(3*pi)
```

Unit Conversions (Full version only)

```
SemCAS> eenheden 5 km naar mijl
5 km = 3.1069 mijl

SemCAS> eenheden 32 °F naar °C
32°F = 0.00°C

SemCAS> eenheden 3 uur naar seconden
3 uur = 10800 seconden
```

Smart Variables (Full version only)

```
SemCAS> x = 5
x = 5

SemCAS> y = x^2 + 3*x + 2
y = 42

SemCAS> toon variabelen
📋 Gedefinieerde variabelen:
  x = 5
  y = 42
```

---

⚠️ Limitations

· Only variables d through z are available (a, b, c are reserved for Pythagorean theorem)
· Equation solving uses SymPy's solve() (works for algebraic equations)
· Differential equations support first and second order ODEs
· Cross product only works for 3D vectors
· Step-by-step explanation is available for: differentiation, integration, simplification, expansion, factorization, limits, equation solving, and Egyptian fractions
· The root function may not work as expected in all cases
· Fourier series only supports square, sawtooth, and triangle waves

---

🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (git checkout -b feature/amazing-feature)
3. Commit your changes (git commit -m 'Add some amazing feature')
4. Push to the branch (git push origin feature/amazing-feature)
5. Open a Pull Request

---

📄 License

Licensed under the GNU General Public License v3.0.

Copyright (C) 2026 SemCAS Contributors

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see https://www.gnu.org/licenses/

```
