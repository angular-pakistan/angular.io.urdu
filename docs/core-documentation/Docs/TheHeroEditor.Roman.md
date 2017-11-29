# Hero Edit karna

Fahrist (Contents)
* Hero (Component) banaein
  * Hero ki (Property) shamil (Add) karein
  * Hero ko dekhaein
* (Heroes Component View) ko dekhaein
* Hero Ki (Class) banaein
* Hero kai (Object) ko dekhaein
* (UpercasePipe) kai zarea Tashkeel (Format) karein
* Hero ko Edit karein
  * Do tarfa (Two-way Binding)
  * Gumshuda (Missing) (FormsModule)
* (AppModule)
  * (FormsModule) ko dar-amad (import) karein
  * (Heroes Component) ko (Declare) karein
* Ikhtitami (Final Code Review)
* Khulasa (Summary)

Ab Application kai pas ibtidaee (Basic) (Title) aa chuka hai. Agai ap Hero ki maloomat (Information) ko dekhanay kai lia aik naya component banaein gai or is component ko (Application Shell) me rakh dein gai.

## (Heroes Component) Banaein

Angular (CLI) ko istimal (Using) kartay howay (heroes) nami (Named) aik naya component banaein.

```javascript
 
 ng generate component heroes

```

(CLI) aik naya folder, ```src/app/heroes/``` or  ```HeroesComponent``` ki Teen (three) files bana degi.

```HeroesComponent``` (Class) file is tarah hai:

> app/heroes/heroes.component.ts (initial version)

```javascript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-heroes',
  templateUrl: './heroes.component.html',
  styleUrls: ['./heroes.component.css']
})
export class HeroesComponent implements OnInit {

  constructor() { }

  ngOnInit() {
  }

}
```

Ap hamesha (Always) Angular ki (Core Library) me se ```Component``` ko dar-amad (import) kartay hain
or ```@Component``` kai zarea component class ki tashreeh (Annotate) kartay hain.

```@Component``` aik (Decorator Function) hai jo kai component kai lia (Angular Metadata) (Specifies) karta hai.

(CLI) teen (Three) (metadata Properties) banati hai:
  1. ```selector```— Component ka (CSS element selector).
  2. ```templateUrl```— Component ki (Template file) ka pata (Location).
  3. ```styleUrls```— Component kai zaati (CSS Styles) ka pata (Location).


[CSS element selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors), ```'app-heroes'``` , ye us (HTML element) kai nam (Name) se milta (Match) hai kai jo (Parent Component) kai (Template) me is component ki shanaakht (Identifies) kar raha hai.

```ngOnInit``` aik [LifeCycle Hook](https://angular.io/guide/lifecycle-hooks#oninit) hai. Angular ```ngOnInit``` ko component banany kai kuch hi dair bad call kar leta hai. Ibtidaee (Initialization Logic) ko rakhnay kai lia ye achi jaga hai.

Hameesha (Component Class) ko ```export``` kia karein takai ap is ko kahein or se ```import``` kar sakein jesa kai ```AppModule``` me.

## Hero ki (Property) shamil (Add) karein

"Windstorm" nami (Named) hero kai lia ```HeroesComponent``` me ```hero``` ki aik  (Property) shamil (Add) karein.

> heroes.component.ts (hero property)

```javascript
 hero = 'Windstorm';
```

## Hero ko Dekhaein

```heroes.component.html``` (Template file) ko kholein. (Angular CLI) ki taraf se (Default Text) ko khatam (Delete) kar dein or isko (Data Binding) kia sath tabdeel (Replace) kardein aik nai (new Property) se.

> heroes.component.html
```javascript
{{hero}}
```

## (HeroesComponent View) ko dekhaein

```HeroesComponent``` ko dekhanay kai lia, Apko isko ```AppComponent``` ka (Shell) (Template) me dalana paray ga.

Ye yad rakhein kai ```app-heroes``` [Element Selector](https://angular.io/tutorial/toh-pt1#selector) hai ```HeroesComponent``` kai lia.
```AppComponent``` (Template file) me aik ```<app-heroes>``` (Element) shamil karein. bilkul (Title) kai nichay.

> src/app/app.component.html
```javascript
  <h1>{{title}}</h1>
  <app-heroes></app-heroes>
```

Is baat ko farz (Assumme) kartay howay kai ```ng serve``` (CLI Command) chal rahi hai. (Browser Refresh) hoga or application kai (Title and Name) ko dekhae ga.

## Hero (Class) ko banaein.

Asli hero nam (Name) se kuch barh kar hota hai.

```src/app``` (Folder) me Hero (Class) banaein iski apni (File) me or usko ```id``` or ```name``` (Property) de dein.

> src/app/hero.ts

```javascript
  export class Hero {
    id: number;
    name: string;
  }
```

Ab ```HeroesComponent``` (Class) kai pas dobara aein or  ```Hero Class``` ko (Import) karlein.

```Hero Componenet``` ki (Property) ko ```Hero``` ki type banany kai lia ```hero``` kai (Component) ko (Refactor) karein.

Nazar sani shuda (Revised) (Component) kuch is tarah dekhay ga.

> src/app/heroes/heroes.component.ts

```javascript
  import { Component, OnInit } from '@angular/core';
import { Hero } from '../hero';

@Component({
  selector: 'app-heroes',
  templateUrl: './heroes.component.html',
  styleUrls: ['./heroes.component.css']
})
export class HeroesComponent implements OnInit {
  hero: Hero = {
    id: 1,
    name: 'Windstorm'
  };

  constructor() { }

  ngOnInit() {
  }

}

```

Ab Page sahi tareeqai se nahi dekhay ga kio kai apne hero ko (String) se (Object) me  badal diya hai.

## Hero (Object) ko Dekhain

(Binding) ko (Template) me (Update) karein (Hero's) kai nam (Name) ko dekhanay kai lia or ```id``` or ```name``` dono ko (Detail Layout) me dikhanay kai lai. Is Tarah :

> heroes.component.html (HeroesComponent's template)

```javascript
  <h2>{{ hero.name }} Details</h2>
  <div><span>id: </span>{{hero.id}}</div>
  <div><span>name: </span>{{hero.name}}</div> 
```
(Browser) (Refresh) hoga or (Hero's Information) dekhany lagay ga.  

## (UppercasePipe) Kai sath tashkeel (Format) karein

```hero.name``` (Binding) me is tarah tarmeem (Modify) karein:

```javascript
  <h2>{{ hero.name | uppercase }} Details</h2>
``` 

Browser (Refresh) hoga or ab (Hero Name) baray huroof (Capital Letters) me dekhae dega.

(Interpolation Binding) me lafz (Word) ```uppercase``` 
( | ) Operator kai foran bad anay wala mutaharik (Activates) kardeta hai (Built-in ```UppercasePipe```) ko.

[Pipes](https://angular.io/guide/pipes) aik acha tareeka hai (Strings , Currency Amounts, Dates or degar (Other) display data) ko tashkeel (Format) karnay kai lia .
Angular kai bohat se (Built-in Pipes) hain or ap apna bhi bana saktay hain.

## Hero ki Tarmeem (Edit) karein

Sarif (User) Hero kai nam ko ```<input>``` (TextField) me tarmeem karnay kai ahal (Able) honay chahiye.

(Textbox) Hero ka nam bhi dekhay or jo sarif (User) indiraj (Type) karay wo bhi dekhae. Is ka matlab ye kai (Data) (Component Class) se (Screen) ki taraf jaiga or (Screen) se (Class) ki taraf wapis jaiga.
 
Is tarah kai (Data Flow) ko khudkar (Automate) karnay kai lia ```input``` form or ```hero.name``` property element kai darmiyan (Between) do-tarfa (Two-way Binding) ko (Setup) karein.

## Do-tarfa Binding (Two-way binding) 

(Detail Area) ko ```HeroesComponent``` template me (Refactor) karein. to ye ab kuch is tarah dekhae de ga:

> src/app/heroes/heroes.component.html (HeroesComponent's template)

```javascript
<div>
    <label>name:
      <input [(ngModel)]="hero.name" placeholder="name">
    </label>
</div>
```
[(ngModel)] ye Angular ka aik do-tarfa binding ka tareekae kar (Two-way Data Binding Syntax) hai.

Yahan ye (Syntax) ```hero.name``` property ko (HTML Textbox) se bind kar raha hai. to ab (Data) dono simit (Both Direction) (Flow) kar sakta hai: ```hero.name``` property se (Textbox) ki taraf or (Textbox) se ```hero.name``` ki taraf.

## Gumshuda FormsModule (The missing FormsModule)

is Baat ko zehan nasheen (Notice) karlen kai  [[(ngModel)]](https://angular.io/api/forms/NgControlStatus) ko shamil (Add) kartay hi application kam karna chor degi.

(error) ko dekhany kai lia, (Browser Development Tools) ko kholein (Open) or (Console) me is tarah kai aik pegam (Message) ko talash karein:
 ```
 Template parse errors:
Can't bind to 'ngModel' since it isn't a known property of 'input'.
 ```
 Agerchai (Although)  [ngModel](https://angular.io/api/forms/NgControlStatus) aik durust (Valid Directive) hai, ye (By default) dastiyab (Availiable) nahi hota.

 Ye ikhtiyari (Optional) [FormsModule](https://angular.io/api/forms/FormsModule) se mutaliq (Belong) hai or apko zarori hai kai ise istimal karnay kai lia ```opt-in``` karein.

 ## AppModule

Angular kai lia ye janna zarori hai kai apki Application kai tukray (Peices) apas me kis tarah jurein gain or application ko degar (Other) kon konsi files or (Libraries) darkar (Required) hain. Is tarah ki maloomat (Information) (MetaData) kehlati hain.

(Metadata) me se baz (Some) wo (Metadata) kai jo 
```@component``` decorators me hain jinhein apne shamil (Add) kia tha (Component Class) me, or degar pecheda (Critical Metadata) [@NgModule](https://angular.io/guide/ngmodule) decorators me hotay hain.

Intihaae zaroori (The Most Important) ```@NgModel``` decorator (Top-Level AppModule Class) ki tashreeh (Annotates) karta hai.

Angular (CLI) ```src/app/app.module.ts``` me aik ```AppModule``` class banati hai jab (Project) ko banaya jata hai.Ye wo jaga hai kai jahan ap ```opt-in``` kartay hain ```FormsModule``` me.

## Import FormsModule

```AppModule``` (```app.module.ts```) ko kholein (Open) or ```FormsModule``` (Symbol) ko ```@angular/forms``` library se import karein. 

> app.module.ts (FormsModule symbol import)

```javascript
  import { FormsModule } from '@angular/forms'; // <-- NgModel lives here
```

Phir ```FormsModule``` ko ```@NgModule``` metadata kai ```import``` array me shamil (Add) kardein, jis kai pas un (External Modules) ki List hogi kai jin kai (Application) ko zarorat hai.

> app.module.ts ( @NgModule imports)

```javascript
  imports: [
  BrowserModule,
  FormsModule
],  
```

Jab Browser (Refresh) hoga, Application do-bara (Again) qabil -e- istimal hojaigi . Ap hero ka nam tabdeel kar sakein gain or tabdeeli ko hama waqt (Immediately) ```<h2>``` me (Textbox) kai opper dekh sakein gain.

## Declare HeroesComponent 

Har component biz zaroor (Must Be) (Declared) hona chahiye aik [NgModule](https://angular.io/guide/ngmodule) me.

Apnay to ```HeroesComponent``` ko (Declare) nahi kia tha phir Application kesay chal rahi hai?

Ye is waja se chal rahi hai kio kai Angular CLI ne ```HeroComponent``` ko us waqt ```AppModule``` me (Declare) kardiya tha jab is ne component ko banaya (Generate) kia tha.

```src/app/app.module.ts``` ko kholein or ```HerosComponent``` ko talash (Find) karein jo balaee satah (Near The Top) par (Import) kiye gai hein.

```javascript
  import { HeroesComponent } from './heroes/heroes.component';
```

```HerosComponent``` (Declare) hai ```@NgModule.declarations``` array me.

```javascript
declarations: [
  AppComponent,
  HeroesComponent
],
```
Is baat ko malhooz-e-Khatir (Note) rakhein kai ```AppModule``` Application kai dono Components ```AppComponent``` or ```HeroesComponent``` ko (Declare) karta hai.

## Code ka akhari jaiza (Review)

Ap apki application is tarah dekhni chahiye [Barah-e-Rasst Misal](https://angular.io/generated/live-examples/toh-pt1/eplnkr.html) / [Example Download](https://angular.io/generated/zips/toh-pt1/toh-pt1.zip). Yahan un files ka code hai jis kai baray me is safhay (Page) par guftugu (Discussed) ki gai.

> src/app/heroes/heroes.component.ts

```javascript
import { Component, OnInit } from '@angular/core';
import { Hero } from '../hero';

@Component({
  selector: 'app-heroes',
  templateUrl: './heroes.component.html',
  styleUrls: ['./heroes.component.css']
})
export class HeroesComponent implements OnInit {
  hero: Hero = {
    id: 1,
    name: 'Windstorm'
  };

  constructor() { }

  ngOnInit() {
  }

}
```

> src/app/heroes/heroes.component.html

```javascript
<h2>{{ hero.name | uppercase }} Details</h2>
<div><span>id: </span>{{hero.id}}</div>
<div>
    <label>name:
      <input [(ngModel)]="hero.name" placeholder="name">
    </label>
</div>
```

> src/app/app.module.ts

```javascript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms'; // <-- NgModel lives here

import { AppComponent } from './app.component';
import { HeroesComponent } from './heroes/heroes.component';

@NgModule({
  declarations: [
    AppComponent,
    HeroesComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

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
<app-heroes></app-heroes>
```

> src/app/hero.ts

```javascript
export class Hero {
  id: number;
  name: string;
}
```

## Khulasa (Summary)

 * Apne CLI ko istimal kartay howay dosra ```HeroesComponent``` banaya.
 * Apne ```AppComponent``` shell me shamil (Add) kartay howay ```HeroesComponent``` ko dekhaya.
 * Apne ```UppercasePipe ``` format ko nam (Name) par lago (Apply) kia.
 * Apne ```ngModel``` directive kai sath do-tarfa (Two-way data binding) ko istimal kia.
 * Apne ```AppModule``` kai baray me sekha.
 * Apne ne ```FormsModule``` ko ```AppModule``` me (Import) karwaya to Angular is qabil hogaya kai isay tasleem (Recognize) karay or ```ngModel``` (Directive) is par lago (Apply) karay.
 * Apne Components ko ```AppModule``` me (Declare) karnay ki ahmiyat (Importance) ko sekha or qabil sataish (Appreciated) baat hai kai CLI ne isay khud apkai lia (Declare) kia hai.