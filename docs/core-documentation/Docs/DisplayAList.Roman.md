# Heroes ki Lisk Dekhaein

* Fahrist (Content)
    * Farzi Heroes ko banaein
    * Heroes ko dekhaein
        * Heroes ko ```*ngFor``` kai zarein list banaein

Is safhay me, Ap (The Tour of Heroes) Application me mazeed Toosee (Expend) karein gai or Sarif ko Hero muntakhib karnay or uski tafseel (Detail) dekhanay ka ikhtiyar (Allow) den gai.

## Farzi Heroes Banaein

Apko Dekhanay kai lia chand heroes darkar (Need) hongai.

Bil akhir (Eventually) ap inko aik remote server se hasil kar rahay hongai.Filhal, Ap kuch farzi heroes banaein gain or or usko is tarah dekhaein gain kai wo server se a rahay hon.

```mock-heroes.ts``` nami aik file ```src/app/``` folder me banaein gain. Aik Heroes kai array ka  (Constant) ko banein or usay export karein. File is tarah dikhni chahiye.

>src/app/mock-heroes.ts
```javascript
import { Hero } from './hero';

export const HEROES: Hero[] = [
  { id: 11, name: 'Mr. Nice' },
  { id: 12, name: 'Narco' },
  { id: 13, name: 'Bombasto' },
  { id: 14, name: 'Celeritas' },
  { id: 15, name: 'Magneta' },
  { id: 16, name: 'RubberMan' },
  { id: 17, name: 'Dynama' },
  { id: 18, name: 'Dr IQ' },
  { id: 19, name: 'Magma' },
  { id: 20, name: 'Tornado' }
];
```

## Heroes ko Dekhaein

Ab ap Heroes ki list dikhanay kai lia tayyar hain ```HeroesComponent``` ki upperi janib (Top)

```HeroesComponent``` class file ko kholein or farzi ```Heroes``` ko import karein.

> src/app/heroes/heroes.component.ts (import HEROES)

```javascript
import { HEROES } from '../mock-heroes';
```

Us class ki property me ```heroes``` ko shamil (Add) karein kai jo in heroes ko binding kai lia khol dein.

```javascript
heroes = HEROES;
```

## Heroes Ki List *ngFor kai zarea banaein 

```HeroComponent``` Template file ko kholein or Darj zeel tabdeeliyan karein:
  * Aik ```<h2>``` tag to uper Add karein.
  * Uskai nechay (Un Ordered List) ka ```<ul>``` tag lagaein.
  * ```<ul>``` kai tag kai ander ```<li>``` ka tag lagaein takai isme ```hero``` ki (Properties) dekhaei ja sakein.
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

Ab ```<li>``` ko is tarah badlein

```<li *ngFor="let hero of heroes">```

![*ngFor](https://angular.io/guide/template-syntax#ngFor) Angular ka (Repeater Directive) hai. Ye (Host Element) ko Repeat karta hai har aik (Element) kai lia jo List me mojood hai.

is Misaal(Example) me.
 * ```<li>``` Host element hai.
 * ```heroes``` list hai ```HeroesComponent``` class me se.
 * ```hero``` halia (Current) hero kai (Object) ko rakhay howay hai (Iteration) kai lia list me se.

 > (Asterisk *) ko ```ngFor``` kai agai lagana na bholein. ye code syntax ka pecheda (Critical) hissa hai.

Browser kai refresh honay kai bad heroes ki List dekhay gi.

## Heroes kai Styles

Heroes ki list ko pur kashish (Attractive) hona chahiye or jab User us par mouse over karay to visually respond karna chahiye or hero ko list me se uthaei.

Pehlay ![Tutorial](https://angular.io/tutorial/toh-pt0#app-wide-styles) me apne basic styles ko pori application kai lia ```styles.css``` me set kia.Is styleSheet me heroes ki list kai lia koi style shamil nahi tha.