---
title: X++ Coding Standards
TOCTitle: X++ Coding Standards
ms:assetid: af6b1c2a-c995-46c6-b965-1bca09f210b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa855488(v=AX.60)
ms:contentKeyID: 35249731
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Coding Standards 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides general coding principles for Microsoft Dynamics AX.

  - Declare variables as locally as possible.

  - Check the error conditions in the beginning; return/abort as early as possible.

  - Have only one successful return point in the code (typically, the last statement), with the exception of switch cases, or when checking for start conditions.

  - Keep the building blocks (methods) small and clear. A method should do a single, well-defined job. It should therefore be easy to name a method.

  - Put braces around every block of statements, even if there is only one statement in the block.

  - Put comments in your code, telling others what the code is supposed to do, and what the parameters are used for.

  - Do not assign values to, or manipulate, actual parameters that are "supplied" by value. You should always be able to trust that the value of such a parameter is the one initially supplied. Treat such parameters as constants.

  - Clean up your code; delete unused variables, methods and classes.

  - Never let the user experience a runtime error. Take appropriate actions to either manage the situation programmatically or throw an error informing the user in the **Infolog** about the problem and what actions can be taken to fix the problem.

  - Never make assignments to the "this" variable.

  - Avoid dead code. (See [Dead Code Examples](dead-code-examples.md).)

  - Reuse code. Avoid using the same lines of code in numerous places. Consider moving them to a method instead.

  - Never use infolog.add directly. Use the indirection methods: error, warning, info and checkFailed.

  - Design your application to avoid [deadlocks](deadlocks.md).

This section contains the following topics:

[X++ Layout](x-layout.md)

[X++ Standards: Comments](x-standards-comments.md)

[X++ Standards: Extra Semicolon is No Longer Recommended](x-standards-extra-semicolon-is-no-longer-recommended.md)

[X++ Standards: Constants](x-standards-constants.md)

[X++ Standards: Arrays](x-standards-arrays.md)

[X++ Standards: Dates](x-standards-dates.md)

[X++ Standards: try/catch Statements](x-standards-try-catch-statements.md)

[X++ Standards: throw Statements](x-standards-throw-statements.md)

[X++ Standards: ttsBegin and ttsCommit](x-standards-ttsbegin-and-ttscommit.md)

[X++ Standards: if ... else and switch Statements](x-standards-if-else-and-switch-statements.md)

[X++ Standards: select Statements](x-standards-select-statements.md)

[Intrinsic Functions](intrinsic-functions.md)

[Clear Code Examples](clear-code-examples.md)

[Dead Code Examples](dead-code-examples.md)

[Best Practices: XML Documentation](best-practices-xml-documentation.md)

[Best Practices: Avoiding Potential Security Issues](best-practices-avoiding-potential-security-issues.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

