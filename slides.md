# React + Typescript
#### The good, the bad and ("the ugly" as `string`)
<div><img class="custom-img" height="200" src="./react.png" /><img class="custom-img" height="200" src="./ts.png" /></div>

---

### Yvan Guidoin
Full-Stack Developer at [Ajenta](https://ajenta.net)
<div><img class="custom-img" height="60" src="./ajenta.png" /><img class="custom-img" height="60" src="./vscene.png" /></div>
<div></div>

---

## Why Typescript ?
- Consistency
- Compilation time props checking
- Avoid testing
- Tooling

---

## Tooling

- https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html
- [VSCode](https://code.visualstudio.com/)
- [atom-typescript](https://atom.io/packages/atom-typescript)
- [Prettier](https://prettier.io)
- [ts-jest](https://github.com/kulshekhar/ts-jest)

---

## Let's do some rework

---

## The good

---

### Dumb pure component
```javascript
import React from "react";
import PropTypes from "prop-types";

const FullScreenLoader = props => {
  return (
    <div className="fullscreen-loader">
      <div className="wrap">
        <div className="message">{props.message}</div>
        <div className="dots">
          <div className="dot one" />
          <div className="dot two" />
          <div className="dot three" />
        </div>
      </div>
    </div>
  );
};

FullScreenLoader.propTypes = {
  message: PropTypes.string.isRequired,
};

export default FullScreenLoader;
```

---

```javascript
import React from "react";
import PropTypes from "prop-types";

const FullScreenLoader = props => { /* render */ };

FullScreenLoader.propTypes = {
  message: PropTypes.string.isRequired,
};

export default FullScreenLoader;
```
```typescript
import React from "react";

export interface FullScreenLoaderProps {
  message: string;
}

const FullScreenLoader = (props: FullScreenLoaderProps) => { /* render */ };

export default FullScreenLoader;
```
<!-- .element: class="fragment" data-fragment-index="2" -->

---

## The bad