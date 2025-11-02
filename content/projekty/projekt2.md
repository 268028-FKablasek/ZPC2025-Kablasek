---
title: "Projekt 2"
weight: 2
subtitle: Tvorba technického puzzle z kartónu
---
<img src="/images/laser.jpg"
     alt="Img7"
     width="500" 
     style="position:absolute; right:2cm; top:8cm; border-radius:10px;">

# Volba tématu
Základem pro tento projekt byla volba vhodného tématu, které by splnilo zadání.

Zadání: Tvorba projektu pomocí laserové řezačky při použití maximálně dvou kartónů o rozměrech **1300x1000x6 mm**. Nutnost využítí principu kontaktních spojů **bez použití lepidla**.

Mým cílem bylo zvolit vhodné téma s oborovou tématikou, proto jsem se rozhodl udělat puzzle s tématikou hřídele z předmětu Základy konstruování (1K). 

# Technické údaje
- **Počet dílků: 600**
- **Rozměr puzzle: 1000x600x6 mm**
- **Rozměr podstavy:1200x800x6 mm**
- **Patern generace: 666**

# Realizace projektu
V prvním kroku bylo nutno najít způsob, jak efektivně vygenerovat patern pro puzzle. Ze zvědavosti jsem se chtěl vyhnout běžnému webovému generátoru a zkusit to přes ChatGpt. Tento úkol však nebyl tak snadný, jak by se mohlo zdát, avšak po delší době přesvědčování se podařilo docílit požadovaného výsledku. 
<img src="/images/puzzletemplate.png"
     alt="Img7"
     width="500" 
     style="position:absolute; right:2cm; top:20cm; border-radius:10px;">

Druhým krokem bylo vytvoření souboru pro gravír. Z tohoto důvodu bylo nutné překreslit fyzický výkres do formátu vhodný pro laser. Tady však nastaly problémy. 
Při exportování z inventoru do pdf a následného vložení do programu Afterburn se správně nezobrazovali kóty a popisové pole, proto následoval dlouhý trouble shooting. Při němž jsem zkoušel různé formáty souborů, následně použití jiného programu (AutoCAD Mechanical) a brouzdání po online fórech. Jediným funkčním řešením se nakonec úkazalo předělání výkresu do formátu svg. přes webovou stránku na export souborů.
<img src="/images/1112.jpg"
     alt="Img8"
     width="500" 
     style="position:absolute; right:2cm; top:30cm; border-radius:10px;">

Třetím krokem bylo otestování nastavení pro řezání a gravírování kartónu. Po testech jsem zvolil:   

     Palení- rychlost 55, výkon 65/60 Gravír-rychlost 80, výkon 20/15

Pro lepší viditelnost gravírování bylo posunuto ohnisko o **2mm** výše.

Po těchto přípravách jsem si uchytil celý kartón do laseru a prvně vygravíroval určený tvar a následně vyřezal zbývající obrys, abych zamezil propadnutí dílků. Pro snadnější přenosnost byla druhého kartónu navrhnuta podstava.
<video width="300" height="400" controls 
        style="position:absolute; right:8cm; top:40cm; border-radius:10px;">
  <source src="/videos/video1.mp4" type="video/mp4">
  Your browser does not support the video tag.
  
</video>

# Final results
<img src="/images/puzzledone.jpg"
     alt="Img6"
     width="600" 
     style="position:absolute; right:17,5cm; top:47.3cm; border-radius:10px;">