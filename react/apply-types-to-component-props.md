# Applying types to component props

You can write a functional component in React using TypeScript.

- First, you define the `ChildProps` interface.
- Next, you write the `ChildAsFC` component and use the Functional Component (FC) type provided by React's TypeScript definitions. 
- `<ChildProps>` is a TypeScript generic. It describe the props that `ChildAsFC` expects to receive.

Note: All react components can optionally provide these properties

- proTypes
- displayName
- defaultProps
- contextTypes

```typescript
import { FC, ReactNode } from "react";

interface ChildProps {
  color: string;
  onClick: () => void;
  children?: ReactNode;
}

export const ChildAsFC: FC<ChildProps> = ({ color, onClick, children }) => {
  return (
    <div>
      {color}
      {children}
      <button onClick={onClick}>Click me</button>
    </div>
  );
};
```

TypeScript checks both `Parent` and `ChildAsFC` components

- In `Parent` component, TypeScript checks if the correct props are provided to `ChildAsFC`
- In `ChildAsFC` component, TypeScript checks if `ChildProps` interface define all props `ChildAsFC` is expected to receive

```typescript
import { ChildAsFC } from "./Child";

const Parent = () => {
  return (
    <ChildAsFC color="red" onClick={() => {}}>
      Hello
    </ChildAsFC>
  );
};

export default Parent;
```
