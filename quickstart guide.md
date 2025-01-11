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

### reference
See [`Installing Angular CLI`](https://v17.angular.io/cli#installing-angular-cli)
