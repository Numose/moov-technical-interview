# Moov Technical Interview Questions

## TypeScript

### 1. How would you type the following:

```TS
type NumberArray = ; // an array that contains numbers
```

```TS
type MixedArray = ; // an array that contains numbers and/or strings
```

```TS
type NumberOrStringArray = ; // an array that contains numbers or an array that contains strings
```

```TS
type NumberThing = ; // an array that contains exactly three numbers
```

### 2. What is the difference between ? and undefined? Here are two examples to compare:

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

### 3. Here is a utility function:

```TS
const isObject = (value: unknown): value is object => typeof value === 'object';
```

3A. What is the type `unknown`? How does it differ from `any`?

3B: What does `value is object` do?

3C: Can you spot any issues with out implementation?

### 4. Here is another utility function:

```TS
const pop = (value: number[]): [number, number[]] => {
    const [first, ...rest] = value;

    return [first, rest];
}
```

4A. Explain what the function is doing.

4B. The TypeScript compiler shows _no static errors_ with this code, but it has a bug. What is the bug?

## React

1. A Junior engineer has submitted this code to you for review. Please list any issues you see.

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

2. When would you use `React.useCallback()`?
