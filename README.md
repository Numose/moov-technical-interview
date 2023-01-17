# Moov Technical Interview Questions

## TypeScript

<details>
  <summary>
    Question 1
  </summary>

  Complete the following types:

  - An array that contains numbers.

  ```TS
  type NumberArray = ;
  ```

  - An array that contains numbers **and/or** strings.

  ```TS
  type MixedArray = ;
  ```

  An array that contains numbers **or** an array that contains strings.

  ```TS
  type NumberOrStringArray = ;
  ```

  - An array that contains **exactly three** numbers.

  ```TS
  type NumberThing = ;
  ```
</details>

<details>
  <summary>
    Question 2
  </summary>

  Here are two interfaces to compare:

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
</details>

<details>
  <summary>
    Question 3
  </summary>

  Here is a utility function:

  ```TS
  const isObject = (value: unknown): value is object => typeof value === 'object';
  ```

  * What is the type `unknown`? How does it differ from `any`?

  * What does `value is object` do?

  * Please list any issues you see with this code.
</details>

<details>
  <summary>
    Question 4
  </summary>

  Here is another utility function:

  ```TS
  const pop = (value: number[]): [number, number[]] => {
      const [first, ...rest] = value;

      return [first, rest];
  }
  ```

  * Explain what the function is doing.

  * The TypeScript compiler shows _no static errors_ with this code, but it has a bug. What is the bug?
</details>

## React

<details>
  <summary>
    Question 1
  </summary>

  A Junior engineer has submitted this code to you for review.

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
</details>

<details>
  <summary>
    Question 2
  </summary>

  - Why would you use `React.useCallback()`?
</details>

## System Design

<details>
  <summary>
    Question 1
  </summary>
  
  Moov is about to...move...into its shiny new Headquarters at 100 Mill, but the management company is behind schedule. They need to find a capable coder to write the software that manages the parking garage and they want you to do it.

  - Please design the back end needed to build this software.
</details>
