# Heroes ki Lisk Dekhaein

* Fahrist (Content)
  * Farzi Heroes ko banaein
  * Heroes ko dekhaein
    * Heroes ko `*ngFor` kai zarein list banaein

Is safhay me, Ap (The Tour of Heroes) Application me mazeed Toosee (Expend) karein gai or Sarif ko Hero muntakhib karnay or uski tafseel (Detail) dekhanay ka ikhtiyar (Allow) den gai.

## Farzi Heroes Banaein

Apko Dekhanay kai lia chand heroes darkar (Need) hongai.

Bil akhir (Eventually) ap inko aik remote server se hasil kar rahay hongai.Filhal, Ap kuch farzi heroes banaein gain or or usko is tarah dekhaein gain kai wo server se a rahay hon.

`mock-heroes.ts` nami aik file `src/app/` folder me banaein gain. Aik Heroes kai array ka (Constant) ko banein or usay export karein. File is tarah dikhni chahiye.

> src/app/mock-heroes.ts

```javascript
import { Hero } from "./hero";

export const HEROES: Hero[] = [
  { id: 11, name: "Mr. Nice" },
  { id: 12, name: "Narco" },
  { id: 13, name: "Bombasto" },
  { id: 14, name: "Celeritas" },
  { id: 15, name: "Magneta" },
  { id: 16, name: "RubberMan" },
  { id: 17, name: "Dynama" },
  { id: 18, name: "Dr IQ" },
  { id: 19, name: "Magma" },
  { id: 20, name: "Tornado" }
];
```

## Heroes ko Dekhaein

Ab ap Heroes ki list dikhanay kai lia tayyar hain `HeroesComponent` ki upperi janib (Top)

`HeroesComponent` class file ko kholein or farzi `Heroes` ko import karein.

> src/app/heroes/heroes.component.ts (import HEROES)

```javascript
import { HEROES } from "../mock-heroes";
```

Us class ki property me `heroes` ko shamil (Add) karein kai jo in heroes ko binding kai lia khol dein.

```javascript
heroes = HEROES;
```

## Heroes Ki List \*ngFor kai zarea banaein

`HeroComponent` Template file ko kholein or Darj zeel tabdeeliyan karein:

* Aik `<h2>` tag to uper Add karein.
* Uskai nechay (Un Ordered List) ka `<ul>` tag lagaein.
* `<ul>` kai tag kai ander `<li>` ka tag lagaein takai isme `hero` ki (Properties) dekhaei ja sakein.
* Kuch CSS Styles lagaein isko style denay kai lia (Ap anqreeb CSS Styles lagaein gai)

Isko kuch is tarah banein:

> heroes.component.html (heroes template)

```javascript
<h2>My Heroes</h2>
<ul class="heroes">
  <li>
    <span class="badge">{{hero.id}}</span> {{hero.name}}
  </li>
</ul>
```

Ab `<li>` ko is tarah badlein

`<li *ngFor="let hero of heroes">`

![*ngFor](https://angular.io/guide/template-syntax#ngFor) Angular ka (Repeater Directive) hai. Ye (Host Element) ko Repeat karta hai har aik (Element) kai lia jo List me mojood hai.

is Misaal(Example) me.

* `<li>` Host element hai.
* `heroes` list hai `HeroesComponent` class me se.
* `hero` halia (Current) hero kai (Object) ko rakhay howay hai (Iteration) kai lia list me se.

> (Asterisk \*) ko `ngFor` kai agai lagana na bholein. ye code syntax ka pecheda (Critical) hissa hai.

Browser kai refresh honay kai bad heroes ki List dekhay gi.

## Heroes kai Styles

Heroes ki list ko pur kashish (Attractive) hona chahiye or jab User us par mouse over karay to visually respond karna chahiye or hero ko list me se uthaei.

Pehlay ![Tutorial](https://angular.io/tutorial/toh-pt0#app-wide-styles) me apne basic styles ko pori application kai lia `styles.css` me set kia.Is styleSheet me heroes ki list kai lia koi style shamil nahi tha.

Ap mazeed styles ko shamil kar saktay hain `styles.css` or us styleSheet ko barhatay jain jis ko apne component me add kia tha.

Ap is baat ko tarjeeh de saktay hain kai ap aik specific component kai lia private styles de saktay hain or har cheez us component me dal saktay hain jis ki us component ko zarorat hai---Code ----HTML or ---CSS sab aik jaga.

Ye nukta-e-nazar (Approach) Component ko dubara kahein or istemal karnay me asani deta hai or (Component Intended) ko zahir karein agerchai (Even) global styles mukhtalif hon.

Ap inline private styles define karein gain `@Component.styles` array me ya phir stylesheet file ki tarah kai jo shanakht yafta (Identified) hai `@Component.styleUrls` array me.

jab CLI `HeroesComponent` ko banati hai. to wo aik `heroes,component.css` nami khali styleSheet banati hai `HeroesComponent` kai lia or `@Component.styleUrls` me is tarah point karein.

> src/app/heroes/heroes.component.ts (@Component)

```javascript
@Component({
  selector: 'app-heroes',
  templateUrl: './heroes.component.html',
  styleUrls: ['./heroes.component.css']
})
```

`herpes.component.css` file ko kholein or `HeroesComponent` kai lia private CSS styles ko paste karein.Is guide kai nichey ap in sab ko ![final Code Review](https://angular.io/tutorial/toh-pt2#final-code-review) me dekh sakein gain.

> Styles or StylesSheet `@Component` metadata me identified hain jin ka Scope us specific component tak hai. `heroes.component.css` styles sirf `HeroesComponent` par apply hongai or bahiri (Outer) HTML ko muta'asir (Effect) nahi karein gai ya kisi or HTML ko jo kai kisi or component me hai.

## Master/Detail

Jab user kisi hero ko click karta hai master lst me se,Component muntakhib (Selected) hero ki detail ko page kai nechay walay hisay me dikhae ga.

Is section me, Ap hero item click event ko listen kar rahay hongai or hero ki detail ko update kar rahay hongai.

## Click Event Binding Add karein

Aik click event binding add karein `<li>` me is tarah:

> heroes.component.html (template excerpt)
> `<li *ngFor="let hero of heroes" (click)="onSelect(hero)">`

ye aik angular ![Event Binding](https://angular.io/guide/template-syntax#event-binding) syntax ki misaal (Example) hai.

`click` kai ird gird (around) (Parentheses) angular ko ye batatai hain kai `<li>` element `click` event ko listen kar raha hai. Jab user `<li>` par click karay ga, to angular ```onSelect(Hero) expression ko (Execute) kar dega.

`onSelect()` aik `HeroComponent` ka method hai jis ko ab abhi likhnay walay hain.Angular isko `hero`object kai sath Call karta hai jo kai `<li>` kai click pe zahir hota hai, usse `hero` ko kai jo pehlay `*ngFor` expression me defined hai.

## Click Event Handler ko Add karein

Component ki `hero` property ko `selectedHero` kai nam ka sath badal dein mager usko assign na karein. Yahan application kai shoro hotay hi koi hero selected nahi hoga.

man darja (Following) method ko add karein,, jo kai click shuda (Clicked) hero ko template se component kai `selectedHero` kai sath assign kardega.

> src/app/heroes/heroes.component.ts (onSelect)

```javascript
selectedHero: Hero;

onSelect(hero: Hero): void {
  this.selectedHero = hero;
}
```

## Detail Template ko Update karein

Template ab bhi musalsal (Still) component kai puranay `hero` property ki (Taraf) refer kar raha hai jo kai ziyada dair tak muyasar (Exists) nahi rahay gi.
`hero` ko `selectedHero` kai sath rename kar dein.

> heroes.component.html (selected hero details)

```javascript
<h2>{{ selectedHero.name | uppercase }} Details</h2>
<div><span>id: </span>{{selectedHero.id}}</div>
<div>
  <label>name:
    <input [(ngModel)]="selectedHero.name" placeholder="name">
  </label>
</div>
```

## Khali (Empty) details ko \*nglf kai zareea chupa dein

Browser kai refresh honay kai bad , application kharab ho chuki hai.
Browser kai developer tools ko kholein or console ki janib is tarah kai aik error ko talash karein:

`HeroesComponent.html:3 ERROR TypeError: Cannot read property 'name' of undefined`

Ab kisi list item par click karein, App dobara kam karnay la'aik lagnay lagai gi. Heroes list me dikhna shoro ho jain gain or click shuda (Clicked) hero ki detail page kai nichlay hissay ki janib dikhein gi.

## Kia Howa (What Happened?)

Jab application start hogi, design kai tor par `selectedHero` `undefined` hoga.

Template me wo binding expressions kai jo `selectedHero` ki property ko refer kartay hain `{{selectedHero.name}}` wo zaror fail hojain gai kion kai abhi filhal koi selected hero nahi hai.

## Haal (The Fix)

Ager selected hero mujood hai to component sirf usse ki details dekhaei ga.

Hero detail ki HTML ko aik `<div>` me Wrap kar dein,`*ngLf` angular directive ko `<div>` me Add karein or usme `selectedHero` ko set kar dein.

> (Asterisk \*) ko `ngFor` kai agai lagana na bholein. ye code syntax ka pecheda (Critical) hissa hai.

> src/app/heroes/heroes.component.html (\*ngIf)

```javascript
  <div *ngIf="selectedHero">

  <h2>{{ selectedHero.name | uppercase }} Details</h2>
  <div><span>id: </span>{{selectedHero.id}}</div>
  <div>
    <label>name:
      <input [(ngModel)]="selectedHero.name" placeholder="name">
    </label>
  </div>

</div>
```

Browser kai refresh kai bad, namon (Names) li list dikhna shoro ho jaigi. Details ka area Blank hai.Hero ko click karein detail dikhna shoro ho jaigi.

## Ye kam kion karnay laga (Why it works) 

Jab ```selectedHero``` undefined tha ,```ngIf``` ne hero detail ko DOM se remove kardiya ab yahan koi ```selectedHero``` bindings nahi hai na hi iskai baray me fikar mand honay ki zarorat.

Jab user kisi hero ko pick karta hai ```selectedHero``` kai pas value ajati hai or ```ngIf``` hero ki detail ko DOM me rakh deta hai.

## Selected Hero ko style dein.

Ye kafi mushkil hota hai kai selected hero ko list me shanakht (Indentify) kia jai jab kai tamam ```<li>``` elements list me yaksan (Same) dikhtay hain.

ager user "Magneta" par click karta hai to us hero ko aik makhsoos (Distinctive) or bilkul isi background kai sath dekhana chahiye.

![](https://angular.io/generated/images/guide/toh/heroes-list-selected.png)