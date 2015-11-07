# es6 impressions

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

