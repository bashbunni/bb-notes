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

(PS thank you muesli)
