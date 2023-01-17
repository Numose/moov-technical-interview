# Moov Technical Interview Questions

## TypeScript

<details>
  <summary>
    ### 1. Typing
  </summary>

How would you type the following:

- An array that contains numbers.

```TS
type NumberArray = ;
```

- An array that contains numbers and/or strings.

```TS
type MixedArray = ;
```

An array that contains numbers or an array that contains strings.

```TS
type NumberOrStringArray = ;
```

- An array that contains exactly three numbers.

```TS
type NumberThing = ;
```
</details>

### 2. Here are two interfaces to compare:

```TS
interface PropsA {
  readonly data?: DataType;
}
```

```TS
interface PropsB {
  readonly data: DataType | undefined;
}
```

- What is the difference between `?` and `undefined` for the prop field `data`?

### 3. Here is a utility function:

```TS
const isObject = (value: unknown): value is object => typeof value === 'object';
```

* What is the type `unknown`? How does it differ from `any`?

* What does `value is object` do?

* Can you spot any issues with out implementation?

### 4. Here is another utility function:

```TS
const pop = (value: number[]): [number, number[]] => {
    const [first, ...rest] = value;

    return [first, rest];
}
```

* Explain what the function is doing.

* The TypeScript compiler shows _no static errors_ with this code, but it has a bug. What is the bug?

## React

1. A Junior engineer has submitted this code to you for review.

```TSX
type PropsDataType = {
  readonly id: string;
}

type CompDataType = {
  readonly id: number;
}

interface ComponentProps {
  readonly data: PropsDataType;
}

export const Component = (props: ComponentProps) => {
  const convertData = (propsData: PropsDataType): CompDataType => ({ id: Number.parseInt(propsData) });

  const [data, setData] = useState(convertData(props.data));

  useEffect(() => {
    setData(convertData);
  }, [props.data, convertData]);

  return (
    <div>{data}</div>
  );
}
```

- Please list any issues you see with this code.

2. React has some lesser-used hooks.

- When would you use `React.useCallback()`?

## System Design

1. Moov is about to...move...into its shiny new Headquarters at 100 Mill, but the management company is behind schedule. They need to find a capable coder to write the software that manages the parking garage and they want you to do it.

- Please design the back end needed to build this software.
