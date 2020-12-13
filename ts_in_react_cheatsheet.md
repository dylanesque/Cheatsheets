-When using CRA, use the `--typescript` flag after the project name to use TypeScript in the project.

-Typed props are one of the biggest major difference between TS React and regular React.

`type Props = {
    title: string,
    isActive: boolean
}

export const Head = ({ title, isActive }: Props) => {}`

-To type the 'children' prop, use `React.FC<OtherProps>`

-Use type inference for useState

// !null read only
-Type `useRef` like so: const sweetRef = useRef<HTMLInputElement>(!null)