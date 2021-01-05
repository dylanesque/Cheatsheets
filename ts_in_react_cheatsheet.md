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

- Consider not typing functional components [at all](https://github.com/facebook/create-react-app/pull/8177)

-To type the 'children' prop, use `React.FC<OtherProps>`

-Use type inference for useState

// !null read only
-Type `useRef` like so: const sweetRef = useRef<HTMLInputElement>(!null)