---
title: "Projekt 5"
weight: 5
subtitle: Elektro - Morse code transmitter
---

<img src="/images/elektro.jpg"
     alt="19"
     width="500" 
     style="position:absolute; right:2cm; top:8cm; border-radius:10px;">

# Definice projektu
Cílem tohoto projektu bylo se naučit využivát elektronické řízení zejména pomocí mikrokontroleru Arduino Uno. Nutností bylo použít zmíněný mikrokontroler a součásti nacházející se v programu Tinker CAD.

# Volba tématu
Pro realizaci jsem si zvolil tzv. "Morse code transmitter", neboli zařízení umožňující převod psáného textu do morzeovky a zpětně.

# Realizace zapojení
Projekt jsem se rozhodl realizovat pouze v digitální podobě v softwaru TinkerCad. Prvotní verze byla pouze na otestování principu a poté postupně vylepšována do koncové podoby. Jednotlivé verze se lišily v použitých součástek, tak i v programu. Po iteračním procesu vznikla finální verze, která obsahuje tyto části:  
- **Arduino Uno R3**
- **PCF8574-based, 39 (0x27) LCD 16 x 2 (I2C)**
- **Piezo bzučák**
- **NeoPixel Ring 12**
- **470 Ω Resistor**
- **100 uF, 16 V Polarized Capacitor**
- **Button**
- **12 x vodič**
- **Breadboard**  

Jednotlivé součástky jsou mezi sebou propojeny vodiči přes breadbordu a napájeny napřímo z arduina.
 <img src="/images/pocetelektro.png"
     alt="20"
     width="500" 
     style="position:absolute; right:2cm; top:19cm; border-radius:10px;">

 <img src="/images/schema.png"
     alt="21"
     width="500" 
     style="position:absolute; right:2cm; top:26cm; border-radius:10px;">

# Tvorba programu
**V první části** programu si bylo nutné nadefinovat jednotlivé vstupy a používané obsahové knihovny. Vstupy se difinují podle funkce const int a knihovny pomocí include.

<img src="/images/kod1.png"
     alt="22"
     width="500" 
     style="position:absolute; right:2cm; top:34cm; border-radius:10px;">

**Druhá část** programu obsahuje mapování jednotlivých znaků a písmen na jejich znění v morzeově kódu. Zároveň však definuje, aby nebyl rozdíl mezi málými/velkými písmeny a diakritikou. Bez tohoto kroku by displej při zadání diakritiky ukázal pouze **?**.

<img src="/images/kod2.png"
     alt="23"
     width="500" 
     style="position:absolute; right:2cm; top:40cm; border-radius:10px;">

**Třetí část** programu se zabývá ovládním **Neopixel ringu** (červená=tečka, modrá=čárka), **Bzučáku** a délkou jednotlivých intervalů. Délka jednotlivých intervalů slouží pro vyzuální a zvukové rozeznání teček a čárek.  

<img src="/images/kod3.png"
     alt="24"
     width="500" 
     style="position:absolute; right:20cm; top:46cm; border-radius:10px;">   
  
 .   
 .   
 .   
 .   
 .   
 .   
 .   
 .   
Zároveň si bylo nutno nadefinovat funkci pro ruční zadávání morzeova kódu ve formě ručního sepnutí tlačítka, které bude v další části programu vracet z čárek a teček písmena a znaky na displej. 

<img src="/images/kod4.png"
     alt="25"
     width="500" 
     style="position:absolute; right:2cm; top:51cm; border-radius:10px;">

V poslední (v páte) části programu je nadefinované ovldání displeje, prvky, které má zobrazovat, a drobné úpravy pro plynulejší chod. Pro stav nečinosti je definovaná hláška **ZPC2025-Kablasek**.

<img src="/images/kod5.png"
     alt="26"
     width="500" 
     style="position:absolute; right:2cm; top:55.5cm; border-radius:10px;">

# Final results
Zařízení umožňuje převod psaného textu na morzeovku a opačně pomocí možnosti ručního zadávaní morzeovky tlačítkem. Tečky signalizuje krátkým probliknutím červené barvy a zvukovou signalizací po dobu 200ms. Čárky signalizuje dlouhým problikutím modré barvy a zvukovou signalizací po dobu 600ms. Displej při převodu zobrazuje dané pisméno a jeho tvar v morzeově abecedě. 

Pro další verze by bylo možno přidat funkci zvukové detekce morzeova kódu a následného přepisu do písmen a znaků.

<video width="600" height="400" controls 
        style="position:absolute; right:17.5cm; top:67.4cm; border-radius:10px;">
  <source src="/videos/videoprojekt.mp4" type="video/mp4">
  Your browser does not support the video tag.
  
</video>