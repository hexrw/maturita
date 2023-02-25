---
layout: default
title: Bitmapová počítačová grafika
permalink: /informatika/bitmapova-pocitacova-grafika/
---

{{ page.title }}
================

Rastrová grafika (či bitmapová grafika) je jeden ze dvou základních způsobů, jakým počítače ukládají a zpracovávají obrazové informace (druhý způsob je vektorová grafika).

V rastrové grafice je celý obrázek popsán pomocí jednotlivých barevných bodů (pixelů). Body jsou uspořádány do mřížky. Každý bod má určen svou přesnou polohu a barvu v nějakém barevném modelu (např. RGB). Tento způsob popisu obrázků používá např. televize nebo digitální fotoaparát.

Kvalitu záznamu obrázku ovlivňuje především rozlišení a barevná hloubka. Rozmístění a počet barevných bodů obvykle odpovídají zařízení, na kterém se obrázek vykresluje (monitor, tiskárna). Pokud se obrázek zobrazuje na monitoru, pak většinou stačí rozlišení 72 DPI, pro tisk na tiskárně 300 DPI.

Pro převod obrazových předloh (klasické fotografie, kreseb a dalších) do rastrové grafiky slouží skener nebo digitální fotoaparát.

Další možností pro ukládání a zpracování obrazů je vektorová grafika, kde se obrázek popisuje pomocí geometrických objektů - křivek a mnohoúhelníků.

## Výhody rastrové grafiky

- Přirozená volba pro digitální fotografii (a některé další typy grafiky).
- Pořízení obrázku je velmi snadné například pomocí fotoaparátu nebo pomocí skeneru.

## Nevýhody rastrové grafiky

- Změna velikosti (zvětšování nebo zmenšování) vede ke zhoršení obrazové kvality obrázku.
- Zejména zvětšování obrázku je možné jen v omezené míře, neboť při větším zvětšení je na výsledném obrázku patrný rastr.
- Poměrně velké nároky na paměťové zdroje (při vysokém rozlišení a barevné hloubce velikost obrázku dosahuje i jednotek megabytů, v profesionální grafice se běžně operuje i s podklady o desítkách megabytů).

## Formáty rastrové grafiky

Používané formáty grafických souborů dělíme na nekomprimované a komprimované, komprimované pak na formáty s bezeztrátovou či ztrátovou kompresí:

- BMP
- GIF
- JPEG
- JPEG 2000
- JPEG XL
- PCX
- PNG
- TIFF
- WebP

Znázornění kruhu v rastrové grafice:
![Rastrová grafika](https://i.ibb.co/3TgC37n/image.png)

## Kvalita obrazu

Kvalita obrazu je ovlivněna řadou parametrů.
- **Počet obrazových bodů** – (čím více, tím lépe, ale obrázek zabere více místa).
Můžeme se setkat s označením např. 1600 × 1200 - počet pixelů v horizontálním
a vertikálním směru. Digitální fotoaparáty uvádí vynásobenou hodnotu, např.
1920000 pixelů neboli 1,92 MPix (výrobci většinou zaokrouhlují nahoru a
označují 2 MPix).
- **Rozlišení** – je počet obrazových bodů na jednotku vzdálenosti. Udává se
v jednotkách DPI (Dots Per Inch). Rozlišení 100 DPI je tedy 100 obrazových
bodů na 1 palec (2,54 cm)
- **Velikost plátna** (v cm nebo palcích)
Všechny tři uvedené parametry spolu souvisí. Pokud budeme vytvářet nový obrázek zadáme
buďto počet obrazových bodů nebo velikost a rozlišení.
- **Barevná hloubka** – každý z jednotlivých bodů barevného obrázku může
nabývat jednu z barev zvolené barevné palety.

## Barevný model

Barevný model je matematický model popisující barvy na základě podílu jednotlivých složek, kterými mohou být vybrané základní barvy nebo jiné parametry. Množina barev definovaná daným barevným modelem se nazývá barevný prostor. Nejznámější barevný model je RGB používaný například v digitální fotografii a CMYK používaný pro barevný tisk.

Fyzikálně je barva vlastnost světla a je dána podílem jednotlivých vlnových délek daného světla v rámci barevného spektra. Barevné modely popis barvy zjednodušují a přizpůsobují lidskému vnímání barev a technickým a dalším potřebám. Definice barev je relativní a záleží na určení neutrální barvy (neutrální šedá, viz vyvážení bílé).

Kromě modelů RGB a CMYK založených na míchání barev existují i jiné modely pracující jasem a dalšími parametry, např. HSV nebo Lab.

### Přehled barevných modelů

- **RGB** (Red, Green, Blue) je aditivní barevný model založený na faktu, že lidské oko je citlivé na tři barvy - červenou, zelenou a modrou. Ostatní barvy jsou dány sytostí těchto barev.
    - Model lze vyjádřit pomocí krychle, ve které jednotlivé osy (x,y,z) odpovídají modrému, červenému a zelenému světlu. Kombinací těchto barev lze získat téměř všechny barvy barevného spektra.
    - Variantou RGB je RGBA (Red, Green, Blue, Alpha), kde je navíc přidán alfa kanál, který nese informaci o průhlednosti. 
- **CMY a CMYK** je barevný model založený na subtraktivním míchání barev. Používá se hlavně u reprodukčních zařízení, která barvy tvoří mícháním pigmentů. Model CMY obsahuje tři základní barvy - azurovou (Cyan), purpurovou (Magenta) a žlutou (Yellow). Jejich složením by měla vzniknout černá, ale při použití běžných tiskových barev není takto vzniklá černá příliš kvalitní. Proto se používá model CMYK, kde je navíc čtvrtá barva - černá (Key black).
- **HSV a HSB** (Hue, Saturation, Value), někdy také HSB (Hue, Saturation, Balance) je barevný model odpovídající lidskému intuitivnímu popisu barev. Má tři základní parametry: tón (odstín), sytost (saturace) a jas. 
- **HSL** (Hue, Saturation, Lightness) je velmi podobný HSV. Zavedla jej firma Tektronix a podařilo se jí odstranit některé nedostatky HSV. Sytost leží na vodorovné ose, světlost na svislé ose a barevný tón představuje úhlová hodnota. Tvar modelu odpovídá skutečnosti - schopnost rozlišování barevných odstínů skutečně klesá se ztmavováním a zesvětlováním základní čisté barvy, zvyšování a snižování světlosti barvy skutečně spočívá v přidávání světlého nebo tmavého pigmentu.
- **YUV** se používá v televizním vysílání.

## Nejčastější formáty rastrové grafiky

### JPEG

JPEG (anglická výslovnost [ˌdžeiˈpeg], užívají se též počeštěné výslovnosti jépeg nebo jpeg) je standardní metoda ztrátové komprese používané pro ukládání počítačových obrázků ve fotorealistické kvalitě. Formát souboru, který tuto kompresi používá, se také běžně nazývá JPEG. Nejrozšířenější příponou tohoto formátu je .jpg, .jpeg, .jfif, .jpe, event. tato jména psána velkými písmeny.

Skutečným názvem typu souboru je JFIF [ˌdžeiˈfif], což znamená JPEG File Interchange Format. Zkratka JPEG znamená Joint Photographic Experts Group, což je vlastně konsorcium, které tuto kompresi navrhlo.

Když se běžně hovoří o souboru JPEG, míní se tím většinou soubor JFIF, nebo soubor Exif JPEG. Existuje však více formátů souborů založených na kompresi JPEG, například JNG.

JPEG/JFIF je nejčastější formát používaný pro přenášení a ukládání fotografií na World Wide Webu. Není však vhodný pro perokresbu, zobrazení textu nebo ikonky, protože kompresní metoda JPEG vytváří v takovém obrazu viditelné a rušivé artefakty. Pro takové účely se většinou používají soubory PNG a GIF. Protože má GIF pouze 8 bitů na pixel, není vhodný pro barevné fotografie, PNG je možné použít pro ukládání fotografií, ale výsledná velikost souboru je nevhodná pro publikování na webu.

MIME typ pro JFIF je image/jpeg (definované v RFC 1341). 

JPEG je vhodný pro fotografické snímky nebo malby realistických scenérií s hladkými přechody v tónu a barvě. V tomto případě poskytuje mnohem menší velikosti souboru než čistě bezztrátové metody jako PNG, přičemž zachovává stále dobrou kvalitu obrazu. Formát JPEG je často srovnáván s GIF – tato srovnaní jsou velmi problematická, protože GIF nikdy nebyl určen pro fotografické obrazy, je limitován na 256 barev, a konečně byl překonán formátem PNG, který je také vhodný pro fotografické obrazy, je bezeztrátový, za cenu větších souborů. Použití na webu – Formát JPEG byl spolu s formátem GIF běžně nejpoužívanějším formátem pro kompresi obrázků na webu, jako jsou designové prvky a loga. V dnešní době je vytlačován formátem PNG, zejména v oblasti designových prvků stránek, jelikož jak již bylo řečeno, tento formát je bezeztrátový a aktuálně, kdy obecně průměrná rychlost připojení internetu u běžných uživatelů narůstá, nehraje větší velikost souborů ve formátu PNG tak významnou roli jako dříve, navíc při použití osmibitových barev ve formátu PNG není rozdíl ve velikosti u srovnatelně kvalitních obrázků v JPEG a PNG zas tak velký. V neposlední řadě také formát PNG podporuje oproti JPEG označení určitých barev v obrázku jako průhledných (toto umí i formát GIF). 

### PNG

PNG (oficiální výslovnost „ping“, Portable Network Graphics, česky přenosná síťová grafika) je grafický formát určený pro bezeztrátovou kompresi rastrové grafiky. Byl vyvinut jako zdokonalení a náhrada formátu GIF. PNG nabízí podporu 24 bitové barevné hloubky, nemá tedy jako GIF omezení na maximální počet 256 barev současně. PNG tedy do jisté míry nahrazuje GIF, nabízí více barev a lepší kompresi (algoritmus Deflate + filtry). Navíc obsahuje osmibitovou průhlednost (tzv. alfa kanál), to znamená, že obrázek může být v různých částech různě průhledný (tzv. RGBA barevný model). Nevýhodou PNG oproti GIF je praktická nedostupnost jednoduché animace, pro kterou sice existují 2 návrhy APNG a MNG, které se ale zatím neprosadily.

PNG se stejně jako formáty GIF a JPEG používá na Internetu.

Podle MIME má PNG přidělen typ image/png.

Oficiální referenční implementací formátu je libpng.

Soubor PNG se skládá z hlavičky souboru a série chunků (datových bloků, doslova kusů, soust nebo špalků).

Každý chunk zprostředkovává jistou informaci o obrazu nebo metadatech. Chunky jsou sémanticky samostatné (přímo se nepojí s jinými částmi souboru). Chunky se rozdělují na „rozhodující“ (critical) a „pomocné“ (ancillary). Rozdělení na chunky dovoluje slučitelnost obrazů PNG se staršími verzemi, stejně jako rozšiřitelnost o případné nové.

Každý chunk se skládá ze čtyř částí: délky obsahu (4 bajty), typu/názvu (4 bajty), samotných dat a kontrolního součtu (4 bajty). Díky tomuto návrhu mohou dekodéry formátu přeskakovat pomocné chunky, aniž by je musely číst; kontrolní součet přispívá k detekci chyb při zpracování.

PNG používá bezeztrátovou kompresi se 2 základními kroky:

1. **Filtrování** – snaha objevit běžné vzory (např. barevné pruhy, gradienty) pro zvýšení účinnosti dalšího kroku
2. **Komprese** – využívá metodu DEFLATE (stejně jako komprimační knihovna zlib), tj. kombinaci slovníkového algoritmu LZ77 a Huffmanova kódování

### WebP (Google)

WebP je ztrátový i bezztrátový kompresní souborový formát pro rastrové obrázky. Vyvinula jej firma Google ze svého formátu videa VP8 používaného v kontejneru WebM a první vydání je z 30. září 2010.

Formát podporuje průhlednost a animaci.

Referenční implementace obsahuje konverzní program pro příkazovou řádku Linuxu pojmenovaný webpconv a knihovnu pro dekódování

*Následuje převzatý text z Wikipedie (en)*

WebP is an image file format developed by Google intended as a replacement for JPEG, PNG, and GIF file formats. It supports both lossy and lossless compression, as well as animation and alpha transparency.

Google announced the WebP format in September 2010, and released the first stable version of its supporting library in April 2018.

### Lossless compression

WebP's lossless compression, a newer algorithm unrelated to VP8, was designed by Google software engineer Jyrki Alakuijala. It uses advanced techniques such as dedicated entropy codes for different color channels, exploiting 2D locality of backward reference distances and a color cache of recently used colors. This complements basic techniques such as dictionary coding, Huffman coding and color indexing transform. This format uses a recursive definition: all of the control images, such as the local entropy code selection, are encoded the same way as the whole image itself.

### Animation

Google has proposed using WebP for animated images as an alternative to the popular GIF format, citing the advantages of 24-bit color with transparency, combining frames with lossy and lossless compression in the same animation, and support for seeking to specific frames. Google reports a 64% reduction in file size for images converted from animated GIFs to lossy WebP, however, with a very noticeable visual impact, both at default settings, and optimised settings. When converting using lossless WebP, a 19% reduction is achieved as reported by Google, although real world performance is nearer to 10%.

### GIF

GIF (Graphics Interchange Format, výslovnost džif i gif[1]) je grafický formát určený pro rastrovou grafiku. GIF používá bezeztrátovou kompresi LZW, na rozdíl například od formátu JPEG, který používá ztrátovou kompresi. GIF je tedy vhodný pro reprezentaci vektorových obrázků (nápisy, plánky, loga), protože zakreslené čáry nejsou rozmazány kompresí. GIF umožňuje také jednoduché animace.

GIF má jedno velké omezení — maximální počet současně použitých barev barevné palety je 256 (8 bitů), v případě animace pak umožňuje využít odlišné palety 256 barev pro každý snímek. Toto omezení nemá formát PNG, který se hodí ke stejným účelům jako GIF a nabízí pro většinu obrazů výrazně lepší kompresi. Formát PNG však neumožňuje animace (ty umožňuje až APNG a MNG).

Formát GIF se stejně jako formáty PNG a JPEG používá pro WWW grafiku na Internetu.

GIF je využitelný pro obrázky, které obsahují nízký počet barev (loga, grafy atd.) a u kterých je potřeba zachovat vstupní kvalitu (tzn. použít bezeztrátovou komprimaci).

GIF je také vhodný na malé animace a filmové klipy s minimálním rozlišením a nízkým počtem barev.

![GIF example](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/Rotating_earth_%28large%29.gif/200px-Rotating_earth_%28large%29.gif)
