# The Application Shell

Fahrist (Contents) >

* Angular Cli ko (Install) karein
* Nai Application (New Application) Banaein.
* Application ko pesh (Serve) karein.
* Angular kai (Components)
* Application kai unwan (Title) ko tabdeel (Change) karein
* Application me (Styles) shamil (Add) karein
* Ikhtitami (Final Code Review)
* Khulasa (Summary)


## Angular Cli ko (Install) karein

Ager ap pehlay (Install) nahi kar chukay to Angular Cli ko (Install) karein.

```javascript
    npm install -g @angular/cli
```
### Aik nai (New) Application banaein

(angular-tour-of-heroes) kai nam se aik naya project (Cli Command) kai zarea (With) banaein.

```javascript
    ng new angular-tour-of-heroes 
```

Angular Cli ne aik nai (New) bunyadi (Default) Application (Supporting files) kai sath bana di hai.

Application ko pesh karein (Serve The Application)

(Project Directory) me ja kar (Application) ko chalein (Launch).

```javascript
    cd angular-tour-of-heroes
    ng serve --open
```
 
 > (ng serve) command application ko (build) karti hai, (development server) ko shoro (start) karti hai, (Source 
  files) ko dekhti hai, or jin files me ap tabdeeli (Changes) karein gain application khudba khud (Rebuild) hojaigi.

 > (--open flag) command ```http://localhost:4200/``` kai patay (Address) par browser khol degi.

App Application ko apnay browser me chaltay howay dekh pa rahay hongai.

## Angular Components

Jo page ap dekh rahay hain ye (Application Shell) hai. Ye (Shell) ```AppComponent``` nami (named) aik (Component) kai zarea controll (Controlled by) hota hai.

(Components) Angular Application kai bunyadi ta'ameeri (Building) ajzaa (Blocks) hain. Ye data ko screen par dekhatay hain, Sarif (User) kai mandarjat (Inputs) ko dekhtay hain, or un mandarjat (Inputs) kai mutabiq kam (Action) kartay hain. 

## Application kai unwaan (Title) ko tabdeel (Change) karein

Project ko apni pasandeda (Editor) ya (IDE) me kholein or ```src/app``` folder me jain.
app yahan ```AppComponent``` (Shell) ki amaldaramdi ```Implementation``` ko in teen (three) files me taqseem (Distributed) dekhein gain:

1. ```app.component.ts```— TypeScript me likha howa component class code.
2. ```app.component.html```— HTML me likha howa component Template. 
3. ```app.component.css```— Component kai zaati (CSS Styles).

Component Class file ko kholein (```app.component.ts```) or ```title``` (Property) ko tabdeel kar kai us ki (Value) ko 'Tour of Heroes' kardein.

> app.component.ts (Class Title Property)

```javascript
    title = 'Tour of Heroes';
```
Component Template file ko kholein (```app.component.ts```) or Angular Cli ki janib se banaya gaya bunyadi (Default Template) Mita (Delete) dein. or is ko man-darja zeal (HTML) line se tabdeel kardein.

> app.component.html (Template)

```javascript
    <h1>{{title}}</h1>
```

(Double Curly Braces) Angular kai *interpolation binding* (Syntax) kai hain. Ye (Interpolation Binding) component kai ```title``` (Property  Value) ko (HTML Header Tag) me dekhata hai.

Browser refresh hoga or application ka naya title dekhae ga.

## Application Kai (Style) shamil (Add) karein

Ziyada tar Applications (Most Applicatons) koshish (Strive) karti hai kai wo Application kai (Look) ko aik jesa rakhein. CLI is maqsad kai lia aik khali (Empty) ```styles.css``` ki file banati hai. Apni application ki tamam (Styles) ko yahan rakhein.

Yahan *Tour of Heroes* nami namona (Sample) Application kai ```styles.css``` se iqtisab (Excerpt) pesh kiye ja rahay hain.

> src/styles.css (Excerpt)

```css
/* Application-wide Styles */
h1 {
  color: #369;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 250%;
}
h2, h3 {
  color: #444;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: lighter;
}
body {
  margin: 2em;
}
body, input[text], button {
  color: #888;
  font-family: Cambria, Georgia;
}
/* everywhere else */
* {
  font-family: Arial, Helvetica, sans-serif;
}
```

## Code ka akhari jaiza (Review)

Is tutorial ka (Source code) or (Tour of Heroes) kai mukamal (Global Styles) [live example](https://angular.io/generated/live-examples/toh-pt0/eplnkr.html) / [download example](https://angular.io/generated/zips/toh-pt0/toh-pt0.zip)

Yahan code files mujood hain jin ko is page per (Discussed) kia gaya hai.

> src/app/app.component.ts
```javascript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Tour of Heroes';
}
```

> src/app/app.component.html
```javascript
<h1>{{title}}</h1>
```

> src/styles.css (excerpt)

```javascript
/* Application-wide Styles */
h1 {
  color: #369;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 250%;
}
h2, h3 {
  color: #444;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: lighter;
}
body {
  margin: 2em;
}
body, input[text], button {
  color: #888;
  font-family: Cambria, Georgia;
}
/* everywhere else */
* {
  font-family: Arial, Helvetica, sans-serif;
}
```

## Khulasa (Summary)

* Apnay Angular Cli ko istimal kartay howa bunyadi (Initial) Applicaiton ki Sa'akht (Structure) banaya.
* Apnay ye sekha kai (Angular Components) Data ko dekhatay hain.
* Apnay Application kai (Title) ko dekhanay kai lia (Double Curly Braces Interpolation) ko istimal kia.

