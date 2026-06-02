SemCAS Expansion Guide
======================

Goal:
-----
This file explains how to add ANY new feature to SemCAS
without breaking existing code. Think “plug-in style”, not
“rewrite the core”.

Core ideas:
-----------
1. Every feature lives in its own function.
2. The main parser (SemCAS(...)) only routes.
3. You NEVER have to delete or rewrite old code to add new stuff.

Step 1 — Find the right place
-----------------------------
Open the main SemCAS file and locate these parts:

- The helper section (expr, pretty, etc.)
- The feature functions (doe_diff, doe_simpel, doe_pyth, etc.)
- The main parser:  def SemCAS(z):

You will add:
- Your new function near the other feature functions.
- A new parser rule inside SemCAS(z).

Step 2 — Create a new feature function
--------------------------------------
Example: you want to add a new command called "demo".

Add this somewhere near the other CAS functions:

    def doe_demo(s):
        # s is a string with the user input AFTER the keyword
        # 1. Parse the expression if needed:
        #    e = expr(s)
        # 2. Do your logic:
        #    result = <whatever you want>
        # 3. Return a string (SemCAS always returns strings):
        return "Demo result: " + s

Rules:
- Input: usually a string (the rest of the user command).
- Output: ALWAYS a string (no raw SymPy objects).
- Use existing helpers like expr(...) and pretty(...) if needed.

Step 3 — Add a parser rule
--------------------------
Inside the SemCAS(z) function, you will see a lot of:

    if zl.startswith("..."):
        ...

Here:
- z  = original user input (with original casing)
- zl = lowercased version of z

To connect your new feature, add something like:

    if zl.startswith("demo "):
        # everything after "demo " is passed to your function
        return doe_demo(z[5:].strip())

Explanation:
- "demo " is 5 characters, so we slice z[5:].
- We use z (not zl) so we keep original casing for math.
- strip() removes extra spaces.

Step 4 — Test your new command
------------------------------
Run SemCAS and type:

    demo hello world

You should see:

    Demo result: hello world

If your feature uses math, for example:

    demo x^2 + 3x + 2

You can do inside doe_demo:

    e = expr(s)
    # do something with e
    return pretty(e)

Step 5 — Keep it modular
------------------------
When adding new features, follow these rules:

- One feature = one function.
- Do NOT mix multiple features into one giant function.
- Do NOT modify existing features unless you are fixing a bug.
- Add new parser rules instead of changing old ones.

Good patterns:
--------------
- New command word:
    - Add a new function:  def doe_<name>(...)
    - Add a new parser rule:  if zl.startswith("<name> "): ...

- New “explain” module (leg ... uit style):
    - Make a function that returns step-by-step text.
    - Plug it into a router or a new keyword.

Example: adding a new "explain" style feature
---------------------------------------------
1) Create:

    def leg_demo_uit(s):
        steps = []
        steps.append("Step 1: This is a demo explanation.")
        steps.append("Step 2: Input was: " + s)
        return "\n".join(steps)

2) In SemCAS(z):

    if zl.startswith("leg ") and zl.endswith(" uit"):
        inner = z[4:-4].strip()
        # For now, route everything to demo:
        return leg_demo_uit(inner)

Later you can replace that routing logic with smarter detection.

Step 6 — General tips
---------------------
- Reuse helpers: expr(), pretty(), trig_fix(), etc.
- Always catch errors where it makes sense and return a friendly message.
- Keep your function names clear and consistent.
- Do not rely on global state unless absolutely necessary.

Summary:
--------
To add something to SemCAS:

1) Write a new function that does the work and returns a string.
2) Add a new parser rule in SemCAS(z) that detects a keyword and calls your function.
3) Test it with simple inputs.
4) Keep it modular so others can add more features without touching yours.

SemCAS is designed so the community can keep stacking features on top
without waiting for a “next official update”.
