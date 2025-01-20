# How to generate a new component in Angular-CLI?

[!NOTE]
> If you think the naming is too complicated for you, you can see examples in example section, or see steps from step 4 then practice it.

1. Think your component name (named `<old-component-name>`) with `upper-camel case` (e.g. OtherComponent) naming style and must end with `Component`.
2. Remove the suffix `Component` from `<old-component-name>`, creating `<old-name>` 
3. Reflect <old-name> to a <new-name> with `hyphen-delimiter words` naming style.

Here is a rule about reflection from `upper-camel case` naming style to `hyphen-delimiter words` naming style.

  1.1 make the first letter as lowercase.
  

> [!NOTE]
> The phrase `reflect an old name (to a new name) with that naming style` means that
>
> refactor an old name (to a new name) through that naming style.

> [!TIP]
> `hyphen-delimiter words naming style` refers a naming style that join multiple words with delimiter hyphen sign (i.e. `-`).
>
> For example, `other-component`.
>
> For more details, see [`naming convention (Wiki)`](https://en.wikipedia.org/wiki/Naming_convention_(programming))

3. In command-line prompt, type these Angular-CLI commands:

```
ng generate component <reflected-name>
```

where 

`<reflected-name>` is the new name that is reflected from old component name with hyphen-delimiter words naming style.

4. Then it will generate a folder in `../src/app` directory that contains these files.

Hierarchy as follows.

```
<reflected-name> ---------> <reflected-name>.component.html
                     ---------> <reflected-name>.component.scss
                     ---------> <reflected-name>.component.spec.html
                     ---------> <reflected-name>.compoent.ts
```

And in `<reflected-name>.component.ts` file, it exports `<old-component-name>Component`

For fully illustration, I will use following examples.

## examples
### example 1
Want to create a component with class name `SecondCompoent`.

1. <old-component-name> is `SecondCompoent`.
2. Reflect 

