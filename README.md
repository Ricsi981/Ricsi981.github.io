# Kutatók Éjszakája: fehérjeszimulációk

Statikus, magyar nyelvű videógaléria. Az `index.html` böngészőben közvetlenül megnyitható; nincs telepítési vagy buildlépés.

A videók és a hozzájuk tartozó magyarázatok az `index.html` fájl `VIDEOS` listájában szerepelnek. A `file` mezőhöz az `assets/videos/<file>.mp4` videó és az `assets/posters/<file>.jpg` előnézeti kép tartozik. A videók hang nélküliek. Csak indításkor töltődnek be; az előnézetek helyi képek.

Az SSB kártya az új `ssb.mp4` videót használja. Az `ssb_llps.mp4` külön kártyán jelenik meg. A korábbi `fold_ecoli_ssb_4.mp4` fájl megmaradt, de a galéria már nem hivatkozik rá.

Videócsere után az előnézet is frissítendő. Példa FFmpeg használatával:

```sh
ffmpeg -ss 1 -i assets/videos/ssb.mp4 -frames:v 1 -vf scale=640:-1 -q:v 3 assets/posters/ssb.jpg -y
```

A lejátszók egérrel, érintéssel és billentyűzettel is kezelhetők. Tab billentyűvel választható vezérlő; Enter vagy szóköz aktiválja a gombokat, a nyílbillentyűk a kijelölt időcsúszkát mozgatják. F teljes képernyőre vált, Esc kilép belőle. A képernyőről kikerülő vagy háttérbe tett videók szünetelnek.

Az ELTE-logó forrását az `assets/images/README.md` tartalmazza. Az SSB-cseppek közérthető leírásának szakmai háttere: [Harami és munkatársai, 2020](https://pubmed.ncbi.nlm.nih.gov/33020264/).
