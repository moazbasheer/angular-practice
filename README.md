# angular-practice

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

```bash
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

### - This is app component 

```bash
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
