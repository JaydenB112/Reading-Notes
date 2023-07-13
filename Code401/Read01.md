# Reading Notes: Debugging Principles and Techniques

## Introduction
- Debugging is an essential skill for software developers to identify and fix code issues.
- Using a debugger allows for step-by-step code execution and helps in understanding and correcting programming mistakes.

## Clarify the Problem
- Before starting debugging, it's crucial to identify the problem you're trying to solve.
- Ask yourself questions like:
  - What was the expected behavior of the code?
  - What actually happened?
  - Did an error or exception occur? If so, it can be a starting point for investigation.
  - Examine symptoms of the problem and identify potential areas of code where it might have occurred.
  - Challenge assumptions made about the code's behavior.

## Examine Assumptions
- Identify and question assumptions that may hinder problem identification.
- Check if you're using the correct API, using it correctly, or if there are any typos in your code.
- Consider the intent of the code and spend time understanding it, especially when debugging someone else's code.
- Start with small, working code and gradually add or modify to identify errors incrementally.

## Step Through Code in Debugging Mode
- Debugging mode allows for monitoring code execution and pausing at any point to examine its state.
- Visual Studio's debugger provides features like breakpoints, which pause the code at specific lines.
- Set breakpoints by clicking in the left margin or using the F9 key.
- Debugging mode helps to observe variables, memory behavior, and code execution sequence.

## Example: Debugging a Sample App
- A sample application with bugs is provided.
- The expected output doesn't match the actual output.
- To debug the app:
  1. Set a breakpoint by right-clicking on the code and selecting "Insert Breakpoint."
  2. Start debugging using F5 or the Debug Toolbar.
  3. The app pauses at the breakpoint, allowing you to inspect variables and their values.
  4. Use hover-over functionality to examine variables.
  5. Modify the code while debugging to test potential fixes.
  6. Repeat the debugging process until the problem is resolved.

## Conclusion
- Debugging is a fundamental skill for software developers.
- Effective debugging involves clarifying the problem, examining assumptions, and stepping through code using debugging tools.
- Practice and experience are key to becoming proficient in debugging.

