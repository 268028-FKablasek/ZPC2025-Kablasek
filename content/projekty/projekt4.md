---
title: "Projekt 4"
weight: 4
subtitle: 3D Tisk - převod do pomala
---

# Definice projektu/zadání
Čtvrtý miniprojekt je zaměřen na technologii 3D tisku.   
3D výtisk musí obsahovat:   
- **Uložení s vůli**  
- **Uložení s přesahem**  
- **Maximální váha 100g**  
- **Určitý druh mechanismu**

# Výběr tématu
Pro můj 3D tištění projekt, který by splňoval požadované parametry jsem zvolil realizaci 
převodu ozubenými koly do pomala.

# Technické parametry
- **Počet párů ozubených kol: 6** 
- **Převodový poměr: 15625**
- **Počet 3D tistěných dílů: 21**
- **Výška vrstvy: 0,3 mm**
- **Výplň: Kubická adaptivní 5%**
- **Tiskárna: Core one**
- **Materiál: PLA**

# Nárvh dílů
Všechny části tohoto projektu byly vymodelovány v aplikaci Inventor profesional 2026. V první řade bylo zapotřebí pomocí funkce návrh definovat hodnoty pro výpočet ozubení.     Navolil jsem si:  
- **Šířku ozubení B1=4mm**
- **Šírku ozubení B2=5mm**
- **Převodový poměr i=5**
- **Počet zubů pastorku=10**
- **Modul=2**

<img src="/images/Tabulkazuby.png"
     alt="15" 
     width="500" 
     style="position:absolute; right:2cm; top:27cm; border-radius:10px;">

Po vygenerovaní jsem na první pár kol přidal díru **8mm** pro hřídel a drážku pro pero. Na ostatních byla vytvořena pouze díra na hřídel.  
Hřídel je navržena s **vůli 0,2mm**, drážkami pro pojistné kroužky, perem a čtvercovým osazením pro nasunutí páky s **přesahem 0,1mm**. Pro uchycení hřídelí byl navrhnut rám obsahujicí dva otvory 8mm. Díly jsou proti vzájemnému axiálnímu posuvu pojišteny pojistnými kroužky.

<img src="/images/inventorkola.png"
     alt="16" 
     width="500" 
     style="position:absolute; right:2cm; top:35cm; border-radius:10px;">

# Realizace 3D tisku
Navržené díly jsem exportoval do souboru stl. ve vysoké kvalitě a vložil je do programu Prusa slicer 2.9.4. V programu byly navoleny tyto parametry:
- **Typ tiskárny**
- **Kvalita tisku/výška vrstvy**
- **Typ materiálu**
- **Rozložení na podložce**

<img src="/images/slicer.jpg"
     alt="17" 
     width="500" 
     style="position:absolute; right:2cm; top:46cm; border-radius:10px;">

# Složení vytištěných části
Po dokončení tisku jsem díly očístil pomocí brusného papíru. Při skládání bylo nutné prvně nasunout ozubene kola na hřídele a pojistit je pomocí pojistných kroužků. Následovalo usazení do rámu a nasazení kliky.

# Final results 
Ozubený převod obsahující 21 části. Složen pouze pomocí 3D tistěných dílů bez použití lepidla. Otočením kliky 15625x se poslední ozubene kolo otočí 1x. Na převodník je možné připojit další mechanismus pomocí volného posledního pastorku.

<img src="/images/mechanismus.jpg"
     alt="18" 
     width="500" 
     style="position:absolute; right:2cm; top:54cm; border-radius:10px;">

<video width="550" height="400" controls 
        style="position:absolute; right:17,5cm; top:64cm; border-radius:10px;">
  <source src="/videos/2.mp4" type="video/mp4">
  Your browser does not support the video tag.
  
</video>