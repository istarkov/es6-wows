# es6 impressions

There are a lot of really cool features in es6. 
Here I place only *IMHOWOW* code blocks!!!

## match expression like

instead of nested ternary expressions or switch

```javascript
const {true: a} = {
  [x > 0]: 1,
  [x < 0]: -1,
  [x === 0]: 'wow',
};
```

## get property or default

instead of this `const x = y && y.x || A;` and this `const x = y && y.x !== undefined ? y.x : A`

```javascript
const {x = A} = y || {};
// or
const {x = A} = {...y};
```

## reduce without explicit `return`

```javascript
blbla.reduce((r, {key, val}) => ({
  ...r,
  [key]: val
}));
```

## pick, pick and rename

```javascript
const obj = {x: 1, y: 2, z: 3, w: 4};
const b = (({ x: a, y: b, z: c }) => ({a, b, c}))(obj);
```

## async await

```javascript
const sleep = async (timeout) => new Promise(r => setTimeout(r, timeout));

const shome = async () => {
  console.log(1);
  await sleep(3000);
  console.log(2);
};

shome();
```

# Required values

Want to require that people populate values in your JS functions? Self referential defaulting works.

```javascript
function foo(T=T) {}
foo() // throws T can't resolve
```

