# General TS

- The `declare` keyword can be used in front of uninitialized variable declarations to prevent an error. This is called **ambient declaration**.

- TypeScript uses structural typing, which means that variables with different types can be assigned to one another if the types are compatible. Here are some rules we can use to determine whether types are compatible:

1) A variable, a, can be assigned to another variable, b, if the type of b is wider than the type of a
2) An object, a, can be assigned to another object, b, if a has at least the same members as b
3) A function, a, can be assigned to another function, b, if each parameter in a has a corresponding parameter in b with a compatible type

# Individual Types

- The `any` type should be avoided whenever possible, since it offers no type protection whatsoever. Strongly consider having `noImplicitAny` set
to true in your config.
- There is a `noExplicitAny` flag for your compiler if you want to banish this from your codebase entirely.

- The union of `undefined` and any other type make that declaration the `optional` type.

1) uninitialized variable: should be undefined
2) a variable clearly representing the absence of something: should be null
3) a variable representing a value: should neither be undefined, nor null

- Booleans can be inferred as false from the values `undefined`, `null`, `-0`, `0`, and `NaN`.

- Literal types are like a mini-interface, specify that it should be a certain value, for example:

`type Direction = "north" | "south" | "east" | "west";`
`let myDirection:Direction = "north";`

## Inference

- TS infers the type of a string const as the value of that const, NOT a string. This applies to any primitive type in TS.

- If a variable is declared without being initialized, TS will infer that it is the 'any' type.

## Scope

- It's recommended that you wrap `case`s in `switch` statements in curly brackets to lock down scope
- 



# TS in React

-When using CRA, use the `--typescript` flag after the project name to use TypeScript in the project, or for newer versions: `--template typescript`

-Use the `.tsx` file extension when JSX is involved, and `.ts` when it isn't.

-Typed props are one of the biggest major difference between TS React and regular React.

```   
type Props = {
  title: string,
  isActive: boolean
}

export const Head = ({ title, isActive }: Props) => {}
```

- using 'type' will cover a lot of use cases, but if your application uses a public API and you want to support 
  extension of types, use an interface instead.

- Caveat to the last point: extending types IS possible using intersections

- Consider not typing functional components [at all](https://github.com/facebook/create-react-app/pull/8177)

-To type the 'children' prop, use `React.FC<OtherProps>`

-Use type inference for useState

// !null read only
-Type `useRef` like so: const sweetRef = useRef<HTMLInputElement>(!null)