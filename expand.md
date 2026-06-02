SemCAS Expansion Guide
======================

Purpose
-------
This document explains how to add ANY new feature to SemCAS.
SemCAS is modular, safe to extend, and designed so contributors
can add features without breaking anything.

------------------------------------------------------------
1. Core Principles
------------------------------------------------------------
- Every feature lives in its own function.
- The main parser only routes input.
- No feature depends on another feature.
- You NEVER rewrite old code to add new code.
- Everything returns strings, not raw objects.

------------------------------------------------------------
2. How to ADD a new feature
------------------------------------------------------------

STEP A — Create a new function
------------------------------
Example: adding a command called "demo".

    def doe_demo(s):
        # s = the user input AFTER the keyword
        # parse if needed:
        #   e = expr(s)
        # do your logic:
        result = "Demo result: " + s
        return result   # ALWAYS return a string

Rules:
- No print()
- No input()
- No global state changes
- Keep it simple and modular

STEP B — Add a parser rule
--------------------------
Inside SemCAS(z):

    if zl.startswith("demo "):
        return doe_demo(z[5:].strip())

Rules:
- zl = lowercase version for detection
- z  = original version for math
- slice correctly ("demo " is 5 chars)
- strip() recommended

STEP C — Test it
----------------
Now type the command that activates your function.

Example:

    demo hello world

If it works and returns your output:
Congratulations — you added a new SemCAS feature.

------------------------------------------------------------
3. Adding a new “leg ... uit” explanation module
------------------------------------------------------------

STEP A — Create the explanation function
----------------------------------------
    def leg_demo_uit(expr_str):
        steps = []
        steps.append("Step 1: This is a demo explanation.")
        steps.append("Step 2: Input was: " + expr_str)
        return "\n".join(steps)

STEP B — Add routing logic
--------------------------
Inside the "leg ... uit" router:

    if is_demo(expr_str):
        return leg_demo_uit(expr_str)

STEP C — (Optional) Add a detector
----------------------------------
    def is_demo(expr_str):
        return "demo" in expr_str

------------------------------------------------------------
4. What NOT to do
------------------------------------------------------------

DO NOT:
-------
1. Do NOT modify existing functions unless fixing a bug.
2. Do NOT merge multiple features into one giant function.
3. Do NOT hardcode logic inside SemCAS(z) that belongs in a module.
4. Do NOT return raw SymPy objects — ALWAYS return strings.
5. Do NOT use print() inside feature functions.
6. Do NOT use input() anywhere except the REPL.
7. Do NOT change global variables (ANGLE_MODE is the only exception).
8. Do NOT break naming conventions (doe_xxx, leg_xxx_uit).
9. Do NOT delete or rewrite other people's modules.
10. Do NOT create circular dependencies between features.

If you break these rules, your feature may become unmaintainable.

DO:
---
1. Add new functions.
2. Add new parser rules.
3. Add new detectors.
4. Add new explanation templates.
5. Keep everything modular and readable.
6. Keep everything returning strings.
7. Keep everything open-source friendly.

------------------------------------------------------------
5. Minimal Template (copy/paste)
------------------------------------------------------------

    def doe_newfeature(s):
        steps = []
        steps.append("Step 1: ...")
        steps.append("Step 2: ...")
        return "\n".join(steps)

    if zl.startswith("newfeature "):
        return doe_newfeature(z[11:].strip())

------------------------------------------------------------
6. Credits
------------------------------------------------------------
SemCAS was created by Sem.
All contributors must keep Sem credited as the original author.

------------------------------------------------------------
7. License
------------------------------------------------------------
Use any open-source license you prefer (MIT recommended).
All contributions must remain open-source.
