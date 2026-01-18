---
title: "Individuální projekt"
featured: true
subtitle: "Motorový blok podvodního dronu Argo"
---
<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/3.4.0/model-viewer.min.js"></script>

<style>
  model-viewer {
    width: 100%;
    height: 400px;
    background-color: #f0f0f0;
    border-radius: 10px;
  }
</style>

<model-viewer 
    src="/ZPC2025-Kablasek/models/motor.glb" 
    alt="3D model motorového bloku" 
    auto-rotate 
    camera-controls
    orientation="0deg 0deg 180deg"> 
</model-viewer>
<img src="/ZPC2025-Kablasek/images/rezmotoru.png"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:17cm; border-radius:10px;">

# Úvod
Individuální projekt se zabývá postupným vývojovým procesem motorového bloku do podvodního dronu Argo, který je realizován studentským týmem StrojLAB Lizard Engineers.   
Cílem projektu je zhotovit funkční kus, který bude následně sloužit do 3. iterace podvodního dronu pro průzkum Hranické propasti. 

## Představení projektu Argo
Argo je v posledních letech hlavní projekt studentského týmu StrojLAB Lizard Engineers, který se zabývá tvorbou týmových projektů, do kterých se můžou zapojit studenti napříč fakultami.        
Jedná se o podvodní modulární dron se zatopenou konstrukcí zhotovenou převážně pomocí aditivních technologií, jehož cílem je dosáhnout dna Hranické propasti. 
Hlavní vědecký přínos spočívá ve využití alternativních způsobů výroby a integrace propeleru s vnitřními lopatkami.   
Tato konstrukce by měla umožnit dosažení cíle, při zachování dostupnosti replikovat projekt ostatními "makery".

<img src="/ZPC2025-Kablasek/images/lizard.jpeg"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:26cm; border-radius:10px;">
---

# Vývojový postup jednotlivých částí
Před samotným zahájením práce na projektu bylo nutné nastudovat řešenou problematiku a zároveň se seznámit s předešlými řešeními. Podle získaných vědomostí byly vymezeny problémy, kvůli kterým předešlé verze selhaly, a byla zahájena práce na vlastní iteraci.

Základním stavebním kamenem vývoje byl již navržený a optimalizovaný propeler s vnitřními lopatkami, který značně omezil dráhu vývoje.

### Vymezení požadavků:
* **Použití pro náhon BLDC Motor AM480**   
* **Otáčky pro chod propeleru 5000 RPM** 
* **Zatěsnění převodového ústrojí v oleji**
* **Nízká váha konstrukce**
<img src="/ZPC2025-Kablasek/images/propeler.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:36cm; border-radius:10px;">

### 1. Vývoj uchycení propeler - Sleeve
Řídící parametr návrhu sleevu byl vnitřní průměr propeleru 70mm a rychlost otáčení. Pro dosažení 5000 Rpm bylo nutné zahrnout přímo na sleeve převod do pomala a to v poměru 2:1 vůči motoru. Dále se určil minimální vnější průměr na ložiska a to 80mm, aby bylo možné zachovat pevnost sleevu i při zátěži.  

V prvních iteracích byla řešena možnost použití HTD řemenice pro převod mezi sleevem a BLDC motorem z důvodu utěsnění pouze daného motoru v oleji. Po testech však bylo usouzeno, že provozovat ložiska pro daný průměr a otáčky ve vodě není vhodné z důvodu malé životnosti způsobené rozvířením částic písku.  
Ve druhé iteraci se proto přešlo k vytvoření jednotky motorového bloku, který bude těsnit v oleji BLDC motor, převodové ústrojí a sleeve s ložisky. Z řemenice se přešlo na převod ozubenými šípovými koly.
<img src="/ZPC2025-Kablasek/images/Blok starý.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:48cm; border-radius:10px;">
U principu druhé iterace se zůstalo a sleeve obsahuje vnitřní drážkování (pro vsunutí propeleru), šípové ozubené kolo o 56 zubech, dosedací plochy na ložiska a kovové dosedací plochy na gufera. Sleeve a propeler jsou děleny z důvodu snazší udržby, v případě potřeby nahrazení propeleru v terénu.  
Sleeve ustanovuje polohu propeleru pomocí dvou zátek s drážkováním.
<img src="/ZPC2025-Kablasek/images/Sleeve.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:59cm; border-radius:10px;">

### 2. Výběr ložisek
Ložiska bylo nutné navrhnout s minimálním vnitřním průměrem 80 mm, s možností zachycení radiální a axiální (60 N) síly při provozních otáčkách 5000 RPM. V první fázi byla zkoušena varianta ponechání ložisek ve vodě. Od tohoto se upustilo a začalo se hledat řešení s vyšší životností a nižší hmotností.  

V druhé fázi byla vytvořena rešerše na použitelné varianty. Zvažovalo se použití:

* **Kuličkových ložisek s kosoúhlým stykem**   
* **Magnetických ložisek** 
* **Dvojice kluzných radiálních a axiálních pouzder**
* **Nízkoprofilových ložisek** 

Hlavní omezení spočívalo v udržení hmotnosti jednoho ložiska okolo 100 g při splnění silových požadavků. Finální výběr byl učiněn po konzultaci s doktorem Davidem Košťálem a byly zvoleny nízkoprofilové kuličkové ložiska s kosoúhlým stykem SA035AR0 od firmy Kayden.
<img src="/ZPC2025-Kablasek/images/sheet.png"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:70cm; border-radius:10px;">

### 3. Výběr těsnění
Konzultace přinesla taktéž značný přínos při výběru těsnění. Výběr se zúžil na tři typy:

* **Ferofluidní těsnění** 
* **Gufera pro vysokorychlostní aplikace**
* **Trojice kroužků z různých materiálů** 

Pro aktuální iteraci bylo zvoleno těsnění pomocí gufera typu HMSA10V. Toto těsnění bylo zvoleno s ohledem na předpoklad vyrovnání tlaků při ponoru a vysokou dostupnost. Do další iterace by bylo spíše uvažováno o použití ferofluidního těsnění. Aktuální gufera jsou podrobována testům v tlakové komoře, aby se ověřila jejich funkčnost v dané aplikaci.
<img src="/ZPC2025-Kablasek/images/gufero.png"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:85cm; border-radius:10px;">

### 4. Návrh ozubení
Ozubení bylo navrženo podle parametrů BLDC motoru při provozní zátěži, zjištěné pokusem. Z těchto parametrů plynou provozní otáčky motoru těsně nad 10 000 RPM.   

Pro optimální provoz propeleru bylo nutné získat provozní otáčky 5 000 RPM při pravotočivých i levotočivých otáčkách. Z hlediska přesnosti, parametrů a konstručních podmínek bylo navrženo šípové ozubení.   
V Inventoru byl návrh proveden jako šikmé ozubení o poloviční šířce a toto kolo bylo ozrcadleno.
<img src="/ZPC2025-Kablasek/images/navrhozubeni.png"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:97cm; border-radius:10px;">

**Parametry:**

* **Převodový poměr:     2:1** 
* **Počet zubů pastorek: 28**
* **Počet zubů Sleeve:   56**
* **Modul:               2** 
* **Úhel sklonu:         20°**

### 5. Vývoj unašeče pastorku pro BLDC motor
Po návrhu ozubení se přesunula priorita na vymyšlení způsobu, jak efektivně uchytit pastorek na hřídel BLDC motoru.

V první iteraci byl testován prototyp unašeče na způsob originální součásti dodávané k motoru. Tato součást se uchycovala pomocí dvou červíků a závitu. Tento princip se ukázal neefektivní a zbytečně složitý, z důvodu nutnosti přesné kovové výroby na soustruhu.   
V druhé iteraci se začal optimalizovat 3D tištěný unašeč, který dosedá na doraz motoru společně s pastorkem, který stlačuje. Po mnoha neúspěšných pokusech se optimalizoval způsob uchycení s výrobními tolerancemi 3D tisku. 

Finální iterace obsahuje 4 samosvorné drážky, na které se nasune pastorek. Tento celek se dále našroubuje na hřídel motoru, přičemž dosedne na doraz motoru. Pro pojištění proti povolení je v horní části šroub M3 se zápustnou hlavou. Pojištění proti případnému vyosení obstarává horní osazení, nasunuté do ložiska v motorové skříni.
<img src="/ZPC2025-Kablasek/images/unasec.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:111cm; border-radius:10px;">
<img src="/ZPC2025-Kablasek/images/malekolo.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:120cm; border-radius:10px;">

### 6. Návrh motorové skříně
Motorová skříň je koncipována konstrukčně jako tlaková nádoba obsahující horní a spodní polovinu s tloušťkou stěny ve všech místech 10mm.  
Obě poloviny obsahují plochu na nalisování ložisek a tesnění. Ložiska jsou ve skřiní předepnuta pomocí obruče přidělané přes závitové vložky a šrouby se zápustnou hlavou.

Spodní polovina zároveň obstarává pojištění unašeče BLDC motoru přes kuličkové ložisko 61701-2RS, zalisované pod unašečem.  
Horní polovina obsahuje výřez pro uchycení chladiče a úchytu motoru. 
<img src="/ZPC2025-Kablasek/images/skrinspodek.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:128cm; border-radius:10px;">

### 7. Vývoj chladiče BLDC motoru
Chladič musí obstarávat částečný odvod tepla, a taktéž musí pevně ustanovovat polohu BLDC motoru při rotaci.

První iterace se koncipovala formou samotného dílce, ve kterém byl vložen motor s olejem a zatěsněn vůči zbytku. Po testech první iterace se však od tohoto nápadu upustilo z důvodu změny principu zatěsnění motorové skříně a zbytečně velké hmotnosti. 
Druhá iterace se začala řešit formou hliníkového úchytu, do kterého se přidělá BLDC motor a celek se našroubuje na motorovou skříň.   
Z druhé iterace vznikl po pár testech finální díl. Ten obsahuje pro úchyt BLDC motoru vsunutý negativ z vnitřní strany a z vnější strany drážky pro lepší odvod tepla.
<img src="/ZPC2025-Kablasek/images/chladic.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:138cm; border-radius:10px;">

### 8. Volba olejové náplně
Pro správnou funkci bylo nutné vybrat olejovou náplň, která obstará stabilní vyrovnání tlaků a mazání součástí.   
**Požadavky:**

* **Chemická nezávadnost** 
* **Mazací vlastnosti při vysokých otáčkách**
* **Nestlačitelnost při vysokých tlacích**
* **Hustota do 20vg** 
* **Elektrická nevodivost**

V závislosti na dostupnosti trhu byl vybrán hydraulický olej Shell PANOLIN S4 HLP Synth Vg 22, který splňuje výše zmíněné požadavky a je vhodný pro mazaní plastového ozubení při vysokých otáčkách. 
<img src="/ZPC2025-Kablasek/images/olej.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:150cm; border-radius:10px;">

# Výrobní proces
V této kapitole se zaměříme na výrobní procesy jednotlivých částí. Projekt kombinuje 4 výrobní technologie:

* **Selective laser sintering (SLS)** 
* **Fused filament fabrication (FFF)**
* **Kovoobrábění**
* **Laserové řezání** 

## 1. Výroba dílu na SLS 
V projektu se vyskytují díly vyrobené ze dvou odlišných materiálů pomocí této technologie pro dosažení funkčnosti dílů.
<img src="/ZPC2025-Kablasek/images/sls.jpg"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:162cm; border-radius:10px;">

###   A. Výroba dílů z PA11 CF15
Z daného materiálu jsou vyrobeny propelery. Volba tohoto materiálu byla učiněna z důvodu parametru pevnosti, tažnosti a povrchové struktury.  
Propelery musí udržovat rozměrovou stálost při rotaci, ale taktéž odolat vniku nečistot. 

Kvůli volbě tohoto materiálu bylo nutno tisknout díly v ochranné dusíkové atmosféře pod přívodním tlakem 5bar.   
Touto technologií se vyrobilo 8 kusů propelerů, které byly následně naskenovány pomocí skeneru SimScan.
<img src="/ZPC2025-Kablasek/images/propscan.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:172cm; border-radius:10px;">

#### Parametry zjistěné skenováním
Výsledné data ze skeneru jsou zpracovány pomocí programu GomInspect 2019. Data byla nejprve upravena a optimalizována pro další měření.  
Poté následovalo porovnání výsledného modelu výrobku a ideálního návrhu z programu Inventor. 

Z rozdílů těchto dat se sestavila mapa odchylek rozměrů, ze které vyplynula průměrná tolerance. 95 % rozměrů se pohybovalo v rozmezí tolerance -0,1 až -0,2 mm.
<img src="/ZPC2025-Kablasek/images/propscan1.png"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:181cm; border-radius:10px;">

###   B. Výroba dílů z PA12 Industrial
Tento materiál se zvolil na základě podobných vlastností k PA11 CF15, oproti němuž lze snadněji tisknout bez nutnosti ochranné atmosféry. 

Pomocí této technologie je zhotovena **Motorová skříň**, **Sleeve** a **Pastorek**. Materiál nabízí i bez úpravy povrchu dobré otěruvzdorné vlastnosti v kombinaci s vysokou soudržností vrstev.
<img src="/ZPC2025-Kablasek/images/pa12.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:190cm; border-radius:10px;">

#### Povrchová úprava dílů
Díly vyrobené technologií SLS se napouštěly impregnačním polymerem Dichtol WTF. Pro tento proces se u dílů po výrobě zdrsnil povrch brusným papírem, pro účinnější impregnaci. 
Proces namáčení a sušení byl u každého dílu proveden 5x. 

Tento proces umožnil zcela zacelit póry vzniklé technologií SLS, zlepšit drsnost povrchu a v hlavní řadě zaručit hydrofóbní vlastnosti součástí.
<img src="/ZPC2025-Kablasek/images/suseni.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:198cm; border-radius:10px;">

## 2. Výroba dílů na FFF
V počáteční části výroby a testů se touto technologií vyráběly díly pro ověření správnosti návrhu z materiálu PETG. Tyto díly sloužily pouze jako dočasné testovací kusy. 
<img src="/ZPC2025-Kablasek/images/test.jpg"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:207cm; border-radius:10px;">

Po otestování principu se touto technologií začaly tisknout díly z materiálu PA12 CF15 pro FFF, které mají pouze pevnostní funkci a není u nich nutné zaručit vodotěsnost. Díly fungují na principu propustnosti vody skrze jejich vnitřní infill. Samotný infill pak má funkci zaručení pevnosti a odfiltrování větších částic z vody.  
**Parametry tisku:**

* **Tiskárna: Prusa core one** 
* **Tryska: Obsidian, Hardened, 0.4mm, HF**
* **Infill: 30% gyroid**
* **Perimetry: 4** 
* **Vrchní a spodní vrstvy: 0**
* **Materiál: PA12 CF15 (Fiberlogic)**
* **Výška vrstvy: 0.15mm**

Technologie FFF se používá pro výrobu **Unašeče**, **Předepínacích obručí** a **Drážkované zátky**.   
Materiál PA12 CF15 pro tyto součásti byl zvolen na základě pevnosti v tlaku, soudržnosti vrstev a únavových vlastností. 
<img src="/ZPC2025-Kablasek/images/nastaveni.png"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:216cm; border-radius:10px;">

## 3. Kovovýroba
Ve vývojovém procesu byla snaha o omezení technologie kovovýroby na minimum, kvůli úspoře váhy. 
Jediný díl vyrobený touto technologií je proto **Chladič motoru**, sloužící zároveň pro jeho uchycení k motorové skříni. 
**Požadavky:**

* **Zachycení krouticího momentu od motoru** 
* **Zamezení pohybu základny motoru vůči ozubení** 
* **Přenos tepla z oleje do vody** 

Vyrobený kus je zhotoven z hliníku na CNC frézce. 

## 4. Laserové řezání
Touto technologií jsou zhotoveny těsnění na dělící rovině motorové skříně a mezi chladičem a skříní. 
Těsnicí materiál byl zvolen Klingerit, neboli těsnicí papír, který se ve strojírenské výrobě používá k zatěsnění tlakových přírub.

Požadovaného tvaru se dosáhlo vytvořením dxf souborů pro laserové řezání a následným vyřezáním na laseru.
<img src="/ZPC2025-Kablasek/images/tesneni.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:235cm; border-radius:10px;">

# Spojovací materiál a normalizované součásti

* **1x BLDC AM480 / 650KV** 
* **1x Ložisko 61701-2RS** 
* **2x Hřídelová vložka SKF_99317** 
* **2X Ložisko SA035AR0**
* **2x Gufero SKF_80X105X10 HMSA10 V**
* **16x Závitová vložka M2x4**
* **56x Závitová vložka M3x3**
* **6x Závitová vložka M4x4**
* **8x Závitová vložka M5x5**
* **28x CSN EN 24014 M5 x 30**
* **56x CSN 4309 5 A**
* **28x CSN EN 24 036 M5**
* **16x DIN 7991TX M2x10**
* **24x DIN 7991 M3x8**
* **1x DIN 7991 M3x10**
* **32x DIN 7991 M3x12**
* **4x DIN 7991 M3x16**
* **6x CSN EN 24017 M4x20**
 
# Proces sestavení
Tento proces je nutné striktně dodržet pro funkční sestavení modelu.

### 1. Vložení závitových vložek
Prvním krokem je vložení zavitových vložek M3x3, M4x4 a M5x5 do připravených míst v obou částech motorové skříně. 
Následuje vložení závitových vložek M2 a M3 do sleevu.
<img src="/ZPC2025-Kablasek/images/vlozky.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:261cm; border-radius:10px;">

### 2. Instalace ložisek
Ložiska SA035AR0 nalisujeme (Uložení do O) z vnitřní strany motorové skříně pod stálým tlakem. Na ložiska se vloží větší předepínací obruče s výřezy, které se postupně přitáhnou pomocí šroubů M3x8.  
Nalisuje se menší ložisko 61701-2RS.
<img src="/ZPC2025-Kablasek/images/vlozeniloziska.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:270cm; border-radius:10px;">

### 3. Instalace hřídelových vložek
Vezmeme si sleeve a 2x hřídelovou vložku. Vložky se opatrně pod stálým tlakem nalisují do poloviny plochy pro gufera na sleevu.   
Nářízneme si na hraně lisovací přírubu hřídelových vložek a krouživým pohybem kleštěmi oddělíme přírubu pro lisování. Vnitřní stranu, která vyčnívá jemně potřeme těsnícím lepidlem. Po tomto kroku je nutné stálým tlakem dotlačit vložky na zadní hranu a očistit přebytek lepidla.
<img src="/ZPC2025-Kablasek/images/sleevevlozky.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:278cm; border-radius:10px;">

### 4. Instalace propeleru do sleevu 
Do sleevu vložíme z jedné strany zátku, kterou přitáhneme pomocí 16 šroubů M3x12. (Orientační dotažení) 
Z otevřené strany nasuneme do sleevu propeler a vložíme druhou zátku. Pomocí 16 šroubů M3x12 ji postupně budeme utahovat do kříže(1Nm). Po dotažení se vrátíme k druhé straně, kterou dotáhneme na stejný moment.

### 5. Instalace sleevu do ložiska
Prvně si vezmeme spodní část motorové skříně (část s malým ložiskem). Sestavený sleeve si položíme kolmo na stůl a na něho dolní část skříně.   
Po vystředění ložiska vůči sleevu začneme vyvíjet stálý tlak na vnitřní kroužek ložiska pomocí lisovacího kroužku, dokud ložisko nedosedne na doraz sleevu.
<img src="/ZPC2025-Kablasek/images/spodekasleeve.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:290cm; border-radius:10px;">

### 6. Složení unašeče a motoru
Po vytištění unašeče projedeme vnitřní závit závitníkem M6. Horní část je nutné odjehlit od podpor a švu. 
Zkontrolujeme orientaci ozubeného kola na sleevu a podle něho nasuneme pastorek na unašeč. Unašeč poté našroubujeme na hřídel motoru a pojistíme ho z vrchní části proti povolení šroubem M3x10.

Tento celek nasuneme do menšího ložiska ve skříni a zkontrolujem orientaci kol.
<img src="/ZPC2025-Kablasek/images/unasecslozen.jpg"
     alt="5"
     width="400" 
     style="position:absolute; right:2cm; top:297cm; border-radius:10px;">

### 7. Uzavření motorové skříně
Na spodní část si vložíme těsnění. 
Horní část skříně si srovnáme vůči spodní. Nasuneme 4 šrouby M5 x 30 s podložkou (nasuneme jeden na každý směr) skrze vrchní část, těsnění a spodní část. Ze spodní strany vložíme podložky a našroubujeme matice (pouze na pár otáček).
Pomocí lisovacího kroužku nalisujeme horní část skříně na sleeve. Je nutno kontrolovat behěm procesu rovnoměrné rozložení sil, aby se předešlo vyosení ložisek. Po dosednutí ložiska na doraz dotáhneme jemně 4 vložené šrouby a vložíme zbylých 24.  
Všechny šrouby dotáhneme podle křížového pravidla na 2 Nm.

### 8. Kontrola volné rotace sleevu

### 9. Instalace gufera
Před instalací gufer je nutné instalovat menší předepínací koužky pomocí 16 M2x10 (1 Nm) - instalujeme zapuštěním ven.  
Gufero si zarovnáme vůči sleevu a pod stálým tlakem ho nalisujeme do skříně pomocí lisovacího kroužku. Toto zopakujeme i z druhé strany.

### 10. Instalace chladiče
Skrze hliníkový chladič provlečeme přívody od motoru. Na motorou skříň zarovnáme těsnění vůči dírám na šrouby.  
Motor si zarovnáme dráty k zadní straně a vložíme na něj chladič. Motor prvně upevníme pomocí 4 M3x16 a poté celý chladič zašroubujeme do skříně pomocí šesti M4x20. 
Šrouby M3 dotáhneme na moment 2Nm a šrouby m4 na 4Nm.

### 11. Plnění olejem
Do spodní části motorové skříně našroubujeme zátku s tesněním. Vývod od kabelů zatěsníme použitím polyuretanového tmelu a kovové vložky.  

Vyrobený celek se vloží do nádoby o velikosti minimálně 200x200x150mm. Nádobu vylijeme olejem do výšky 150mm a necháme v ní celek alespoň 12 hodin. 
Po uplynutí této doby instalujeme v nadobě zátku s těsněním do chladiče motoru.  

Motorový blok vyjmeme a důkladně odmastíme. 

(Na obrázku lze vidět složenou referenci bez horního gufera)
<img src="/ZPC2025-Kablasek/images/bezgufera.jpg"
     alt="5"
     width="500" 
     style="position:absolute; right:2cm; top:340cm; border-radius:10px;">

## Stav projektu v době odevzdání stránek
Návrhová i vývojová část je kompletně hotová a čeká se pouze na vyrobení hlínikového chladiče. 

Projekt je sestaven bez hliníkového chladiče, který je dočasně nahrazen výtiskem z technologie FFF, pro účely testování.  
Motorový blok byl cvičně naplněn a roztočen na nízké otáčky pomocí tištěného dílu, na čemž bylo ověřeno:

* **Těsnost motorového bloku** 
* **Funkčnost převodu** 
* **Správnost výrobních vs návrhových tolerancí** 
* **Výška upevnění motoru a osová vzdálenost**
 
## Závěrečné shrnutí
Individuální projekt se podařilo realizovat ve fázi kompletního konstrukčního návrhu. V době odevzdání webových stránek je motorový blok sestaven s využitím dočasného chladiče vyrobeného technologií FFF, který pro účely testování zastupuje finální hliníkový díl.

Prvotní funkční zkoušky prototypu při nízkých otáčkách prokázaly správnost zvolené koncepce. Experimentálně byla ověřena těsnost motorové skříně, plynulost chodu převodového ústrojí a korektnost výrobních tolerancí v návaznosti na osové vzdálenosti.

Projekt je tak připraven na finální kompletaci po dodání CNC obráběného chladiče. Po následných zátěžových testech bude proces výroby 5x zopakován. Výsledné jednotky pak budou sloužit jako pohonná jednotka pro 3. iteraci podvodního dronu Argo.

