# Kutatók Éjszakája: fehérjeszimulációk

Statikus, magyar nyelvű videógaléria. Az `index.html` böngészőben közvetlenül megnyitható; nincs telepítési vagy buildlépés.

A galéria fölötti négy információs fül egymástól függetlenül nyitható. Kezdetben mind zárt, és lejátszáskor sem nyílik ki automatikusan. Tartalmuk az oldal normál elrendezésében jelenik meg, a videókat nem takarja el. A fül újbóli megnyomása, az X gomb vagy a panelen belül az Esc bezárja az adott panelt. Témák: méret és idő, a szimuláció számítási lépései, az eredmények értelmezése, illetve az SSB-kondenzátumok biológiai jelentősége. A tudományos háttérhez vezető hivatkozások a panelekben találhatók.

A videók és a hozzájuk tartozó magyarázatok az `index.html` fájl `VIDEOS` listájában szerepelnek. A `file` mezőhöz az `assets/videos/<file>.mp4` videó és az `assets/posters/<file>.jpg` előnézeti kép tartozik. A videók hang nélküliek. Csak indításkor töltődnek be; az előnézetek helyi képek.

Az SSB kártya az új `ssb.mp4` videót használja. Az `ssb_llps.mp4` külön kártyán jelenik meg. A korábbi `fold_ecoli_ssb_4.mp4` fájl megmaradt, de a galéria már nem hivatkozik rá.

Videócsere után az előnézet is frissítendő. Példa FFmpeg használatával:

```sh
ffmpeg -ss 1 -i assets/videos/ssb.mp4 -frames:v 1 -vf scale=640:-1 -q:v 3 assets/posters/ssb.jpg -y
```

A lejátszók egérrel, érintéssel és billentyűzettel is kezelhetők. Tab billentyűvel választható vezérlő; Enter vagy szóköz aktiválja a gombokat, a nyílbillentyűk a kijelölt időcsúszkát mozgatják. F teljes képernyőre vált, Esc kilép belőle. A képernyőről kikerülő vagy háttérbe tett videók szünetelnek.

Az ELTE-logó forrását az `assets/images/README.md` tartalmazza. Az SSB-cseppek közérthető leírásának szakmai háttere: [Harami és munkatársai, 2020](https://pubmed.ncbi.nlm.nih.gov/33020264/).

Az LLPS-videó a galéria utolsó, teljes szélességű kártyája. A `featured` mező jelöli a kiemelést. A `description` a kártya magyarázata, a `note` pedig a videó indításakor és nagyított nézetbe lépéskor megjelenő, bezárható buborék szövege. Az információgombbal a buborék újra megnyitható. Kis lejátszóban a kép alatt, teljes képernyőn a kép mellett vagy fölött jelenik meg, a képernyő méretétől függően. Ha a böngésző nem támogatja az egész lejátszó teljes képernyős megjelenítését, az oldal saját nagyított nézete nyílik meg, így a magyarázat is elérhető marad. A nagyítás a teljes képernyő gombbal vagy Esc billentyűvel zárható be.

A p53 leírása a DNS-hez kötődést mutatja be, és a p53 saját mutációinak lehetséges hatását magyarázza. Nem állítja, hogy a fehérje a DNS alakjából közvetlenül felismer minden hibát. Szakmai háttér: [a 2AHI szerkezet](https://www.rcsb.org/structure/2AHI), [RCSB PDB-101: p53](https://pdb101.rcsb.org/motm/31). Az apoptoszóma hét részből álló szerkezete: [3JBT](https://www.rcsb.org/structure/3JBT).
