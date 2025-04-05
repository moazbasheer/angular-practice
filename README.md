# angular-practice

## - Components

### - This version is Angular 19
### - Run this command to setup angular on your machine:

```bash
npm i -g @angular/cli
```
### - Then run this command to create a new angular project: 
```bash
ng new my-app
```
### - Then run this command to publish the project:
```bash
cd my-app
ng serve
```
### or
```bash
ng serve --open
```

### - Run this command to create a header component:
```bash
ng g c header
```

### - In src/index.html, this code is written.
#### File: `src/index.html`
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>MyApp</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <app-root></app-root>
</body>
</html>
```

- app-root is the app component.

### - This is the code of the app component.
#### File: `app.component.ts`
```typescript
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet],
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'my-app';
}

```

- tag name is written in the selector attribute - ``` selector: 'app-root', ```
and this is the used word in the html.

### - To put header component in the app component, you have at first to pass the class of header component in the imports of the app components and use it as you want in the app component and then you have to import the component in the app component class file.
#### File: `app.component.ts`
```typescript
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';
import { HeaderComponent } from './header/header.component';

@Component({
  selector: 'app-root',
  imports: [RouterOutlet, HeaderComponent],
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'my-app';
}
```
### - Write the word header works! in the html of the header component.
#### File: `header.component.html`
```html
<p>header works!</p>

```
### - Write the header component in the html of the app component.
#### - File: `app.component.html`
```html
<app-header></app-header>
```

![image-1.PNG](image-1.PNG)

### - And Then the header component appear in the app component as in the image.

## - Data Binding

![data-binding.PNG](data-binding.PNG)

## - Directives

### - ngIf
- To make an If condition on a div in html, you have to write this syntax.
- If the condition is true the div will be displayed, otherwise the div won't be displayed.
```html
<div *ngIf="status == true">Display</div>
```

### - ngFor
- To view students in a web page, you have to write this syntax in the ts file.
```typescript
import { CommonModule } from '@angular/common';
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-header',
  imports: [FormsModule, CommonModule],
  templateUrl: './header.component.html',
  styleUrl: './header.component.css'
})
export class HeaderComponent {
  public name: string
  students: any[]
  constructor() {
    this.name = "moaz"
    this.students = [
      {id: 1, name: "abc"},
      {id: 2, name: "deg"},
      {id: 3, name: "hij"}
    ]
  }
}
```
- and write this syntax in the html.

```html
<ul>
    <li *ngFor="let student of students; let i = index">{{student.name}} - {{students.length}}</li>
</ul>
```
### - ng-template

### - ng-container

## - Custom Directives



## - Setuping any package globally in angular.

- Run this command.

```bash
npm i bootstrap jquery
```

- Put files' paths in styles and scripts in build in bootstrap.json

#### File: `bootstrap.json`

```json
"styles": [
  "src/styles.css",
  "node_modules/bootstrap/dist/css/bootstrap.css"
],
"scripts": [
  "node_modules/bootstrap/dist/js/bootstrap.js",
  "node_modules/jquery/dist/jquery.js"
],

```

## - Routing

- To route the components, write this code in app.routes.ts.
- Make an object in routes array, this object contains the path of the page in the path attribute and the component in the component attribute.

#### File: `app.routes.ts`
```typescript
import { Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ServiceComponent } from './service/service.component';

export const routes: Routes = [
    {path: "", component: HomeComponent},
    {path: "about", component: AboutComponent},
    {path: "service", component: ServiceComponent},
];

```

- In app component html, write this code.
#### File: `app.component.html`

```html
<router-outlet></router-outlet>
```

- you can use the hyperlink in routerLink attribute.
```html
<a routeLink="/about">About</a>
```
