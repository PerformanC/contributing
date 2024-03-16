# Contributing

Guidelines for contributing to any PerformanC project.

## Table of Contents

- [Security Policy](#security-policy)
- [Code of Conduct](#code-of-conduct)
- [Syntax](#syntax)
  - [General](#general)
  - [JavaScript / TypeScript (Node.js)](#javascript--typescript-nodejs)
  - [C](#c)
  - [Dart](#dart)
  - [HTML, CSS, and JavaScript (Web)](#html-css-and-javascript-web)
- [Commit Messages](#commit-messages)
- [Issues](#issues)
- [Pull Requests](#pull-requests)
- [License](#license)
  - [Licenses](#licenses)

## Security Policy

To ensure proper security of all PerformanC projects, please follow the [Security Policy](SECURITY.md), documenting the security guidelines and procedures.

## Code of Conduct

Any PerformanC contributor must follow the [Code of Conduct](CODE_OF_CONDUCT.md), allowing better communication and collaboration between the community.

## Syntax

To keep a consistent style, there are rules to follow when writing code. They are not enforced by any tool, but they are enforced by the community. If you have any questions or concerns, please contact The PerformanC Organization.

### Project information

PerformanC projects are divided into three categories:

- Leading standard: Projects that follows all standards from The PerformanC Organization, and are used as examples for the community and new projects. They are cherry-picked by The PerformanC Organization core team.

- Standard compliant: Projects following all the standards from The PerformanC Organization. Not leading standard projects, but are strictly following the standards of The PerformanC Organization.

- Semi-Standard compliant: Projects that either use outdated standards, or are not following all the standards from The PerformanC Organization.

- Non-compliant: Projects that do not follow the standards from The PerformanC Organization.

> [!NOTE]
> The PerformanC Organization is constantly working on improving the standards, and assuring that all projects are following them.

### General

- USe 2 spaces for indentation.
- Use spaces instead of tabs.
- Use single quotes over double quotes.
- Use camelCase for variables and functions. `C` is an exception.
- Use PascalCase for classes.
- Use SCREAMING_SNAKE_CASE for global constants (immutable) or macros.

### JavaScript / TypeScript (Node.js)

- Use ES6 syntax.
- Use `===` over `==`.
- Use `!==` over `!=`.
- Use `const` over `let` when possible.
- Use arrow functions over function expressions.
- Prohibited usage of `var`.
- Prohibited usage of `;`, unless it is required.
- Prohibited usage of `let`, or `const` without a value, must set to `null`.
- Prohibited comments (// or /* */) in the code.
- Prohibited `,` in the last item of an array or object.
- Prohibited usage of CommonJS, use ES6 instead.
- Prohibited usage of `"`.
- Prohibited usage of global Node.js modules without importing (`process`, `Buffer`, etc)
- Order of imports:
  - Node.js built-in modules. Must have `node:` prefix.
  - Project modules.
  - Third-party modules.
  - With a space between each group.
- Functions may be declared before usage.
- Code must be created as a function if used more than once, with `_` prefix. (private)
- `const`s must be defined first than `let`s, save when it is required.
- `return`s without a value must have a `;` at the end.


```js

import { foo2 } from 'bar'

function foo(value) {
  const firstLetter = value[0]
  let lastLetter = value[value.length - 1]
  lastLetter = lastLetter === '!' ? '?' : lastLetter

  if (firstLetter === 'n') return;

  return `${firstLetter.toUpperCase()}${value.slice(1, -1)}${lastLetter}`
}

console.log(foo('yes!'))
console.log(foo('no'))
```

> [!NOTE]
> The code above is only an example of the syntax, it is not a good example of code as doesn't make sense.

### C

- Use C89 or C99, C89 is preferred.
- Use snake_case for variables and functions, with `libname_` prefix.
- Use functions over macros.
- Use `#define` over `const`.
- Use `struct` over `typedef struct`.
- Use `NULL` over `0`.
- Prohibited usage of glibc or musl.
- Prohibited comments (// or /* */) in the code.
- Prohibited usage of GNU extensions.
- Discounraged use of dynamic memory allocation.
- Recommended goto usage when appropriate.
- Order of imports:
  - C standard libraries, `stdio.h` and `stdlib.h` must be first.
  - System libraries.
  - Project libraries.
  - Third-party libraries.
  - Headers of the file, separated from all other imports.
  - With a space between each group.

```c
#include <stdio.h>

void foo(int i) {
  if (i == 0) goto error;

  printf("Hello, world!\n");

  return;

  error:
    printf("Error!\n");
}

int main(void) {
  int i = 11;
  int *i_ptr = &i;

  printf("Hello, world! %p\n", i_ptr);

  foo(0);

  return 0;
}
```

### Dart

- Use Dart 3 syntax.
- Use `const` over `final` when possible.
- Same rules as JavaScript.

```dart
/* Same code as JavaScript */
import 'package:bar/bar.dart';

String foo(String value) {
  const firstLetter = value[0];
  final lastLetter = value[value.length - 1];
  lastLetter = lastLetter == '!' ? '?' : lastLetter;

  if (firstLetter == 'n') return;

  return '${firstLetter.toUpperCase()}${value.substring(1, value.length - 1)}$lastLetter';
}

void main() {
  final foo = Foo();

  print(foo('yes!'));
  print(foo('no'));
}
```

## HTML, CSS, and JavaScript (Web)

- Use HTML 2 syntax.
- Prohibited to use external CSS or JavaScript.
- Prohibited requests to external resources, except if it is required for the project.
- Prohibited to use any HTML, CSS or JavaScript framework or library.
- Prohibited comments (<\!-- -->) in the code.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
  </body>
</html>
```

## Commit Messages

```txt
add | update | remove | fix | improve | merge: short description (#PR merged)

Full description of the commit.

Co-authored-by: name <email> (optional)
```

> [!NOTE]
> A project maintainer may change the commit message if it does not follow the guidelines.

## Issues

Issues are used to track bugs, feature requests, and more. Please follow the guidelines below when creating an issue.

- Use a descriptive title:
  - Bad: `.connect() error`
  - Good: `connect: Connection timed out`

- Use a descriptive description:
  - Bad: `I can't connect to the server.`
  - Good: `When I try to connect to the server, I get the following error:`
    ```
    Error: Connection timed out
        at connect (index.js:1:1)
        at main (index.js:2:1)
        ...
    ```
## Pull Requests

Pull requests are used to contribute to the project. Please follow the guidelines below when creating a pull request.

- Use a descriptive title:
  - Bad: `[BUG]: Network error` / `[BUG]: Connection error`
  - Good: `[BUG]: Connection timed out`

- Use a descriptive description:
  - Bad: `Fixed #1`
  - Good: `Fixed the connection timeout error by adding a timeout option to the connect function. See #1 for more details.`

