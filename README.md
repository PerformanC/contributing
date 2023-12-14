# Contributing

Guidelines for contributing to any PerformanC project.

## Table of Contents

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

## Code of Conduct

For assuring a welcoming community, please read and follow the [Code of Conduct](CODE_OF_CONDUCT.md). If you have any questions or concerns, please contact the PerformanC Organization: performancorg@gmail.com.

## Syntax

To keep a consistent style, there are rules to follow when writing code. They are not enforced by any tool, but they are enforced by the community. If you have any questions or concerns, please contact the PerformanC Organization.

### General

- USe 2 spaces for indentation.
- Use paces instead of tabs.
- Use single quotes over double quotes.
- Use camelCase for variables and functions.
- Use PascalCase for classes.
- Use SCREAMING_SNAKE_CASE for global constants or macros.
- Prohibited any telemetry or analytics.
- Prohibited any tracking or ads.

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

```js

import { foo2 } from 'bar'

function foo() {
  foo2()

  return 'bar'
}

console.log(foo())
```

### C

- Use C89 or C99 syntax, C89 is preferred.
- Use functions over macros.
- Use `#define` over `const`.
- Use `struct` over `typedef struct`.
- Use `NULL` over `0`.
- Prohibited usage of glibc or musl.
- Prohibited comments (// or /* */) in the code.
- Discounraged use of dynamic memory allocation.
- Recommended proper goto usage.

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
void main() {
  print('Hello, world!')
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
add | update | remove | fix | improve: short description

Full description of the commit.

Co-authored-by: name <email> (optional)
```

> [!WARNING]
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
  - Bad: `Fix #1`
  - Good: `Fix: Connection timed out`

- Use a descriptive description:
  - Bad: `Fixed #1`
  - Good: `Fixed the connection timeout error by adding a timeout option to the connect function.`

## License

The licenses of the projects can only be changed by the PerformanC Organization core team. If you have any questions or concerns, please contact the PerformanC Organization.

> [!WARNING]
> PerformanC Organization core team will never change the license of a project without a good reason, or with the intention of harming the community.

### Licenses

- [Original license](ORIGINAL_LICENSE): The base license of the PerformanC Organization.
- [NodeLink license](NODELINK_LICENSE): Protection 
- [PerforVNMaker license](PERFORVNMAKER_LICENSE)

> [!WARNING]
> This section is only for information purposes, the licenses of the projects can only be changed by the PerformanC Organization core team.