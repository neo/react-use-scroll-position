# react-use-scroll-position

[![npm package](https://img.shields.io/npm/v/react-use-scroll-position.svg)](https://www.npmjs.com/package/react-use-scroll-position) ![](https://img.shields.io/npm/types/react-use-scroll-position.svg)

A [react hook](https://reactjs.org/docs/hooks-intro.html) to use scroll position.

## Usage

### In a React functional component:

```tsx
import React from 'react';
// Usually you would just need to import one of the following
import { useScrollPosition, useScrollXPosition, useScrollYPosition } from 'react-use-scroll-position';

function Example() {
  const { x, y } = useScrollPosition();
  const scrollX = useScrollXPosition();
  const scrollY = useScrollYPosition();
  return (
    <>
      <p>
        {x} should equal to {scrollX}.
      </p>
      <p>
        {y} should equal to {scrollY}.
      </p>
    </>
  );
}
```

### In a custom React hook

```tsx
import { useScrollPosition } from 'react-use-scroll-position';

function useYourImagination() {
  const { x, y } = useScrollPosition();
  return getSomethingAwesomeWith(x, y);
}
```

# Implementation details

The scroll event handler is throttled by `requestAnimationFrame`.
