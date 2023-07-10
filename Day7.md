# Day 7

## Topics: 
###  Modules
- Modules let us split big codebases across multiple files.
- `script type = "text/javascript"`: they are accessible to global scope.
- `script type = "module"`: they are not able to access any of these variables that declare in local scope.
- JS `modules` work differently from JS `scripts`. One difference is that we can't use await outside of a function in a script.
```

<script>
    await fetch("https://dog.ceo/api/breed/hound/list");
</script>
```
- Modules create their own scope.

  ### Debugging
  - console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs.
  - You can also use the browser's debugger to pause JS and inspect what's happening.
  - The debugger statement creates a breakpoint where JS will pause and let you look around.
  ```
  function whyIsntThisWorking(input) {
    debugger;
    return thingThatDoesntWork(input);
    } 
```
- Different browsers' debuggers work differently:
1. Firefox
2. Chrome
3. Safari
