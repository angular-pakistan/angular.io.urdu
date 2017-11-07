# Tutorial: (Bahadur'on ki Saair) Tour of Heroes

Tour of Heroes Tutorial Angular ki bunyadi usool (fundamentals) par mushtamil hai.

Is Tutorial me ap aik aisi Application banaein gain jo aik (Staffing Agency) ko apnay (Stable Heroes) ko munazzam 
(Manage) karnay me madad degi.

Is bunyadi (Basic) Application aisay bohat saray features hain kai jo ap aik (Data-Driven Application) me dekhein gain. Ye Application Heroes ki list legi or usse dekhay gi, Kisi bhi muntakhib Hero ki malomaat (Detail) me Tarmeem (Edit) karti hai, or heroes kai (Data) kai mukhtalif zawiyon ki taraf (Navigate) karti hai.

Is Tutorial kai ikhtitam (End) par ap Darj Zail (Following) kam karnay kai qabil (Able) ho jain gain.

* (Elements) or Heroes ki (Data List) ko Dekhanay (Show) or Chupanay (Hide) kai lia Angular kai (Built-in Directives) ka Istimal.
* Heroes ki detail ko dekhanay or Heroes kai (Array) ko Dekhanay kai lia Angular Components ko banana.
* (One-way Data Binding) ko (Read-Only Data) kai istimal karna.
* Qabil-e-Tarmeem (Editable) Fields ko (Model) ko (Update) karnay kai lia Shamil (Add) karna (Two-Way Binding) kai sath.
* (Component Methods) ko (User Events) kai sath (Bind) karna, jeesakai (KeyStrokes) or (Clicks).
* Sarifeen (Users) ko (Master List) me se (Hero) ko muntakhib (Select) karnay kai Qabil banana or us (Hero) ki (Detail) me Tarmeem (Edit) karna.
* (Data) ki Tashkeel (Format) karna (Pipes) kai sath.
* Heroes ko jama (Assemble) karnay kai lia Mushtarqa Service (Shared Service) banana.
* (Routing) ko mukhtalif (Different) (Views) or (Components) ki taraf (Navigate) karnay kai lia istimal karna.

Ap Angular ko shoro karnay kai lia bohat kuch sekhein gain or Aetimad (Confidence) barhaein gai kai Angular har wo kam kar sakta hai or ap is se chahtay hain.

## Ap kia banaein gain

Yahan aik Tasweeri Khaka (Visual idea) hai kai ye (Tutorial) kaha tak rehnumai (Lead) karay ga, Shoro'aat (Dashboard) se or Behtareen Heroes ki List se:

![](https://angular.io/generated/images/guide/toh/heroes-dashboard-1.png)

Ap in Dono (Links) par (Click) kar saktay hain Jo kai ()(Dashboard) kai opper hain ("Dashboard") or  ("Heroes") jo kai (Navigate) karein gain (Dashboard View) or (Heroes View) kai darmiyan.

Ager ap (Dasboard Hero) "Magenta" ka click kartay hain to ye route (Hero Detail) ko Khol dega jahan ap Hero ka nam badal (Change) kar saktay hain.

![](https://angular.io/generated/images/guide/toh/hero-details-1.png)

("Back" Button) ko Click kartay hi ap (Dashboard) par ajain gai. Uper Links apko (Main Views) ki taraf lay jain gain. Ager Ap ("Heroes") par click karein kartay hain to app (Heroes) ki (Master List View) dekhay gi.

![](https://angular.io/generated/images/guide/toh/heroes-list-2.png)

Jab ap mukhtalif (Hero) ka nam par (Click) karein gai,to aik mukhtasar si malomaat (mini Detail) (Read-only) nichay ajain gi. or list nai (Choice)  zahir (Reflect) karay gi.

Ap ("View Detail" Button) par click kar saktay hain takay ap muntakhib (Selected Hero) ki malomaat
(Detail) ko tarmeem kai qabil (Editable) kar sakein.

Man darja zail Diagram (Following Diagram) ne tamam (Navigation Options) ki tasweer kashi (Captures) ki howi hai.

![](https://angular.io/generated/images/guide/toh/nav-diagram.png)

Yahan Chalti howi Application:

![](https://angular.io/generated/images/guide/toh/toh-anim.gif)