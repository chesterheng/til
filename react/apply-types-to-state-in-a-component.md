# Apply types to state in a component

- `guests` state is type `<string[]>`

```typescript
const GuestList: FC = () => {
  const [guests, setGuests] = useState<string[]>([]);

  return (
    <div>
      <h3>Guest List</h3>
    </div>
  );
};
```

- `user` state is type union `User` or `undefined`

```typescript
interface User {
  name: string;
  age: number;
}

const users = [
  { name: "Sarah", age: 20 },
  { name: "Alex", age: 20 },
  { name: "Michael", age: 20 },
];

const UserSearch: FC = () => {
  const [user, setUser] = useState<User | undefined>();

  return (
    <div>
      <h3>User Search</h3>
    </div>
  );
};
```