# Angular
## quickstart guide
### installation Angular CLI
In terminal, type these commands:

```
npm install -g @angular/cli@<latest-version-number>
```

where 

`<latest-version-number>` is a number with latest version, released in [`Release of Angular CLI`](https://github.com/angular/angular-cli/releases)

> [!NOTE]
> At present, the latest version of Angular CLI is `v19.1.0-rc.0`.
>
> So, to install Angular CLI, type these commands:
>
> ```
> npm install -g @angular/cli@19 
> ```

### build Angular project
To create, build, and serve a new, basic Angular project on a development server, go to the parent directory of your new workspace, type these commands:

```
ng new <your-project-name>
```

Then it will ask you some questions, answer these questions.

### change the directory
To change the directory to `<your-project-name>`, type these commands:

```
cd <your-project-name>
```

### serve
To serve the project, type these commands:

```
ng serve
```

Then click the `http://localhost:4200/` link to open url `http://localhost:4200/` with web browser.

That's done. You will see a page like this:

<img width="1274" alt="image" src="https://github.com/user-attachments/assets/9201256b-b369-495c-bbb3-8ab7020491da" />

#### demo
+ See [`Demo of build a new Angular project and run the server with Angular CLI.`](https://youtu.be/0oXjoliL81I)

### How Angular Application Run?

- Angular started with main.ts.
- Then we bootstrap an angular application and we pass app.module.ts as an argument. In app.module.ts we tell angular: "There is the app component which you should know when you try to start yourself".
- And angular now analyze this app component, reading the set up we pass there and there is SELECTOR app-root.
- Now, angular is enable to handle app-root in the index.html and knows rules for the SELECTOR.
- SELECTOR should insert the app components and have some HTML code - a template attached to him - html component.
- This is how Angular application starts.

For more details, see [`How Angular Application Run? which file executes first?`](https://stackoverflow.com/questions/59625412/how-angular-application-run-which-file-executes-first)

### Dive into Angular project.

1. First, Angular started with `.../src/main.ts`.
   
Thus look at `.../src/main.ts` file. 

In `.../src/main.ts`, it bootstraps the component `AppComponent` 

(you can know it through `bootstrapApplication` function call with `AppComponent` argument).  

And `AppComponent` is defined in `.../src/app/app.config` 

(you can know it through the import statement `import { AppComponent } from './app/app.component';` in `.../src/main.ts`)

2. Thus, look at `.../src/app/app.component.ts` file.

In `.../src/app/app.component.ts` file, you will see two code snippets.

+ First code snippets

```
export class AppComponent {
  title = 'app-project';
}
```

illustrates it will export class named `AppComponent`.

+ Second code snippets

```
@Component({
  selector: 'app-root',
  imports: [RouterOutlet],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss'
})
```

defines a component with following info.

  - use selector `app-root` (you can know it through `selector: 'app-root',`).
  - use the imported component `RouterOutlet` (you can know it through `imports: [RouterOutlet],`).
  - use the template from the url `'./app.component.html'` (you can know it through `templateUrl: './app.component.html'`).
  - use the style from the url `'./app.component.scss'` (you can know it through `templateUrl: './app.component.scss'`).

Then let's dive in `.../src/app/app.component.html` first then `.../src/app/app.component.scss`.

3. In `.../src/app/app.component.html` file, you will see `<style>` tag, `<main>` tag and `<router-outlet />` tag 

+ `<style>` tag is used to define your own style.
+ `<main>` tag is used to render UI compoents. Like `<main>` in `HTML5`, all tags in it will be rendered and then display on web page.
+ `<router-outlet />` tag is a self closing tag (i.e. there is no needed to use `<router-outlet> ... </router-outlet>`), which is a directives defined in `RouterOutlet`.

For more details, see [`What is router-outlet in Angular, and where is it used?`](https://www.geeksforgeeks.org/what-is-router-outlet-in-angular-and-where-is-it-used/)

> [!WARNING]
> In `.../src/app/app.component.html`, there must be exactly one `<main>` tag.
>
> If you define more then one `<main>` tag, only at most one `<main>` tag will be rendered on web page (for which `<main>` tag, it accords to Angular).
>
> If you don't define `<main>` tag, nothing will be displayed on web page.
> 
> For best practice, I highly recommended that define exactly one `<main>` tag.   

> [!WARNING]
> Similar to `<style>` tag.
>
> In `.../src/app/app.component.html`, there must be exactly one `<main>` tag.
>
> If you define more then one `<style>` tag, only at most one `<style>` tag will be rendered on web page (for which `<style>` tag, it accords to Angular).
>
> If you don't define `<style>` tag, nothing will be displayed on web page.
> 
> For best practice, I highly recommended that define exactly one `<style>` tag.

4. In `.../src/app/app.component.scss`. file, you will see an empty file. However you can define your own style in this file.

 
   
### code snippets
Here, I will list a few important code snippets and will replace unimportant part to comments.

#### `.../src/main.ts`

```
import { bootstrapApplication } from '@angular/platform-browser';
import { appConfig } from './app/app.config';
import { AppComponent } from './app/app.component';

bootstrapApplication(AppComponent, appConfig)
  .catch((err) => console.error(err));
```

#### `.../src/app/app.component.ts`

```
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet],
  templateUrl: './app.component.html',
  styleUrl: './app.component.scss'
})
export class AppComponent {
  title = 'app-project';
}
```
#### `.../src/app/app.component.html`

```
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * * * The content below * * * * * * * * * * * -->
<!-- * * * * * * * * * * is only a placeholder * * * * * * * * * * -->
<!-- * * * * * * * * * * and can be replaced.  * * * * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * Delete the template below * * * * * * * * * -->
<!-- * * * * * * * to get started with your project! * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->

<style>
   <!-- define your style -->
</style>

<main class="main">
  <!-- render your component which will be displayed on web page -->
</main>

<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * * * The content above * * * * * * * * * * * * -->
<!-- * * * * * * * * * * is only a placeholder * * * * * * * * * * * -->
<!-- * * * * * * * * * * and can be replaced.  * * * * * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * * End of Placeholder  * * * * * * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<router-outlet />
```

For full project, see [`minimal_example_ex1.7z` at GitLab](https://gitlab.com/jayw711kb/angular/-/blob/main/minimal%20example/minimal_example_ex1.7z)
#### demo

<img width="1276" alt="image" src="https://github.com/user-attachments/assets/39f8fc14-279d-4e83-9249-c56e16d973fe" />

### reference
See [`Installing Angular CLI`](https://v17.angular.io/cli#installing-angular-cli)
