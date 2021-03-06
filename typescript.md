# General TS

- TypeScript is a structural type system: it cares about the shape of an object, ie, the names of properties and types of values.

- "Wide" and "Narrow" are used to describe the level of specificity.

- The `declare` keyword can be used in front of uninitialized variable declarations to prevent an error. This is called **ambient declaration**.

- TypeScript uses structural typing, which means that variables with different types can be assigned to one another if the types are compatible. Here are some rules we can use to determine whether types are compatible:

1) A variable, a, can be assigned to another variable, b, if the type of b is wider than the type of a
2) An object, a, can be assigned to another object, b, if a has at least the same members as b
3) A function, a, can be assigned to another function, b, if each parameter in a has a corresponding parameter in b with a compatible type

# General Guidelines

- One important component of TypeScript is being aware of the individual config settings for the project you're working on, and working within that framework, such as using `noImplicitAny` or `strictNullChecks`, or enabling `strict`.

- TS code generation isn't the same thing as it's type system, meaning that code with type errors can compile unless explictly blocked from doing so by `noEmitOnError` or a similar tactic.

- Types aren't available at runtime. If you need a type at runtime, you need some way to access it like property checking or a tagged union. 

- In TS, types aren't "sealed" or written in stone. Values that are assignable to an interface might have properties beyond those initially stated in the type declarations. This is known as structural typing.

- TS types can be thought of as sets of values. (Revisit this, item #7 in Effective TypeScript)

- In any given TS expressions, it's important to know whether or not you're in type space or value space, because keywords and operators will behave differently depending on which of the two it is.

- Prefer declaring the type rather than relying on type assertions, unless you have a very good reason for needing the latter.

- Excess type checking is something else to be aware of (and another reason to avoid assertions).

- Excess type checking happens when you assign an object literal to a variable or pass it as an arg to a function.

- Strongly consider applying type annotations to entire function expressions, rather than just parameters and return type.
  
- Use index signatures when you can't know the exact properties of an object at runtime.

- If function parameters don't get modified by the function, strongly consider making them `readonly` to prevent mutation and have clearer code.

- Understand the difference between const and readonly, and keep in mind that readonly is shallow.


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

- Values in an intersection type contain the union of properties of each of it's individual parts

## Inference & Annotations

- TS infers the type of a string const as the value of that const, NOT a string. This applies to any primitive type in TS.

- If a variable is declared without being initialized, TS will infer that it is the 'any' type.

- Avoid type annotations when TS can infer the correct type

- Type Annotations are good for function or method signatures, but not local vars within their body.

- Strongly consider annotations on object literals and function return types, even when they can be inferred.

## Scope

- It's recommended that you wrap `case`s in `switch` statements in curly brackets to lock down scope

# Mapped Types



# Objects

- You can create an object literal in TS using curly braces, like in JS. This can be 
  limiting since you need to define every member of it at initialization time.

  # Types vs Interfaces

  - When deciding whether to use one or the other in a project, consider any existing styles involving them in the project, and whether or not you should be using augmentation.



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