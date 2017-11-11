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