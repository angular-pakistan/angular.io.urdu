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

>src/app/heroes/heroes.component.ts (import HEROES)

```javascript
import { HEROES } from '../mock-heroes';
```

Us class ki property me ```heroes``` ko shamil (Add) karein kai jo in heroes ko binding kai lia khol dein.

```javascript
heroes = HEROES;
```

## Heroes li List *ngFor kai zarea banaein 

