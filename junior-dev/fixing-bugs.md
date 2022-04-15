# Tips for Fixing Bugs
1. Make it reproducible. It's very hard to catch a bug that only happens sometimes.
    - You need to clearly identify the circumstances in which it occurs
2. Assume nothing and go through the code line-by-line. You'll often find the bug just doing this. 
3. For non-trivial cases i.e. bugs that involve some deeper state:
    - print debugging can be helpful, especially with Bubble Tea (in which case you would log to file)
    - you can to evaluate how state changes as the program executes and runs into the bug
    - Piecing that information together will let you solve a fair amount of bugs
4. For really bothersome bugs, you'll want to pull out your debugger so you can keep track of the entire state line-by-line through the entire execution of the program
5. Worst of all are race conditions which are bugs that only manifest under certain timing conditions. 
    - this would include code that executes in the background and one part of the code finished before another, but only sometimes

## Types of Bugs
"a Heisenbug is a software bug that seems to disappear or alter its behavior when one attempts to study it"
"a Schroedinbug is a bug that manifests itself in running software after a programmer notices that the code should never have worked in the first place."
"a Hindenbug is a bug with catastrophic behavior."
"a higgs-bugson is a bug that is predicted to exist based upon other observed conditions but is difficult, if not impossible, to artificially reproduce in a development or test environment."
"a Mandelbug (from Mandelbrot fractals): you discover a bug and while trying to fix it, you uncover 50 other & worse bugs"
"a Bohrbug: a good, solid piece of bug. Easy to identify, easy to fix, little to no side-effects"

(PS thank you muesli)
