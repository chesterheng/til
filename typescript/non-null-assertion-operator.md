# Non-null assertion operator

You can use non-null assertion operator `!` to tell TypeScript `element` will not be `null` or `undefined`.

```typescript
const element = document.getElementById("root");

const root = ReactDOM.createRoot(element!);
```
