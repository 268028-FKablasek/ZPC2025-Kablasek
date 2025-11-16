
---
title: "Úvod"
---
# How to make (almost) anything 2025

V rámci této webové stránky bude postupně představen **individuální projekt** a zároveň **pět menších projektů** vytvořených do předmětu ZPC. Menší projekty představují jednotlívé technologie, které lze použít pro tvorbu. Individuální projekt propojuje získané zkušenosti a ukazuje jejich spojení do celku.

Na této stránce naleznete dokumentaci jednotlivých projektů, jejich výsledky a postupy, které vedly k jejich kompletaci. 


<style>
.tree {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 60px 0;
  font-family: sans-serif;
}

.tree .node {
  padding: 15px 30px;
  border: 2px solid #555;
  border-radius: 10px;
  background: #ffffff;
  position: relative;
  font-size: 1.2em;
  font-weight: bold;
  min-width: 160px;
  text-align: center;
  transition: all 0.3s ease;
}

.tree .node a {
  text-decoration: none;
  color: inherit;
  display: block;
}

.tree .node:hover {
  background: #f0f0f0;
  transform: scale(1.05);
  cursor: pointer;
}

.tree .children {
  display: flex;
  justify-content: center;
  gap: 50px;
  margin-top: 60px;
  position: relative;
}

.tree .children::before {
  content: "";
  position: absolute;
  top: -30px;
  left: 50%;
  width: 2px;
  height: 30px;
  background: #555;
}

.tree .children .node::before {
  content: "";
  position: absolute;
  top: -30px;
  left: 50%;
  width: 2px;
  height: 30px;
  background: #555;
}

.tree .children .node:first-child::after,
.tree .children .node:last-child::after {
  content: "";
  position: absolute;
  top: -30px;
  width: 50%;
  height: 2px;
  background: #555;
}

.tree .children .node:first-child::after {
  left: 50%;
}

.tree .children .node:last-child::after {
  right: 50%;
}
</style>

<div class="tree">
  <div class="node">
    <a href="/ZPC2025-Kablasek/projekty/individualni-projekt">Individuální projekt</a>
  </div>
  <div class="children">
    <div class="node"><a href="/ZPC2025-Kablasek/projekty/projekt1">Projekt 1</a></div>
    <div class="node"><a href="/ZPC2025-Kablasek/projekty/projekt2">Projekt 2</a></div>
    <div class="node"><a href="/ZPC2025-Kablasek/projekty/projekt3">Projekt 3</a></div>
    <div class="node"><a href="/ZPC2025-Kablasek/projekty/projekt4">Projekt 4</a></div>
    <div class="node"><a href="/ZPC2025-Kablasek/projekty/projekt5">Projekt 5</a></div>
  </div>
</div>
