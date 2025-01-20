# How to generate a new component in Angular-CLI?

[!NOTE]
> If you think the naming is too complicated for you, you can see examples in example section, or see steps from step 4 then practice it.

1. Think your component name (named `<old-component-name>`) with `upper-camel case` (e.g. OtherComponent) naming style and must end with `Component`.
2. Remove the suffix `Component` from `<old-component-name>`, creating `<old-name>` 
3. Reflect <old-name> to a <new-name> with `hyphen-delimiter words` naming style.

Here is a rule about reflection from `upper-camel case` naming style to `hyphen-delimiter words` naming style.

a. lowercase it for first letter.

b. After that, for all uppercase letter, replace it to a hypen sign (i.e. `-`) followed by its corresponding lowercase.

For example, 

`PageNotFound` will be `pageNotFound` after step a. 

Then it will be `page-not-found` after b.

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

4. In command-line prompt, type these Angular-CLI commands:

```
ng generate component <reflected-name>
```

where 

`<reflected-name>` is the new name that is reflected from old component name with hyphen-delimiter words naming style.

5. Then it will generate a folder in `../src/app` directory that contains these files.

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
Want to create a component with class name `PageNotFoundCompoent`.

1. <old-component-name> is `PageNotFoundCompoent`.
2. Remove suffix `PageNotFoundCompoent`, <old-name> is `PageNotFound`.
3. Reflect <old-name> to a <new-name> with `hyphen-delimiter words` naming style.

a. `PageNotFound` => `pageNotFound`

b. `pageNotFound` => `page-not-found`

So <reflected-name> is `page-not-found`.

4. In command-line prompt, type

```
ng generate component page-not-found 
```

<img width="557" alt="image" src="https://github.com/user-attachments/assets/d5a5c035-69a7-4103-ab5e-5e063ebadf04" />

5. Then it will generate a folder in `../src/app` directory that contains these files.

Hierarchy as follows.

```
page-not-found ---------> page-not-found.component.html
               ---------> page-not-found.component.scss
               ---------> page-not-found.component.spec.html
               ---------> page-not-found.compoent.ts
```

<img width="611" alt="image" src="https://github.com/user-attachments/assets/58e88305-5ef3-41e6-a1be-e87b027a084f" />

In `page-not-found.compoent.ts` file, you will see the following code snippets.

```
import { Component } from '@angular/core';

@Component({
  selector: 'app-page-not-found',
  imports: [],
  templateUrl: './page-not-found.component.html',
  styleUrl: './page-not-found.component.scss'
})
export class PageNotFoundComponent {

}
```

<img width="401" alt="image" src="https://github.com/user-attachments/assets/25ace2a0-3c4d-44ba-9471-764060624421" />

