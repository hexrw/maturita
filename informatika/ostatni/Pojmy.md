---
layout: default
title: Pojmy
permalink: /informatika/ostatni/pojmy/
---

<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>

<div x-data="{
    topic: '1',
    data: [],
    getData() {
        let promises = []
        for (i = 1; i <= 25; i++) {
            promises.push(
                fetch('/informatika/ostatni/pojmy/' + i)
                    .then(res => res.text())
                    .then(html => /<body.*?>([\s\S]*)<\/body>/.exec(html)[1])
            )
        }
        Promise.all(promises).then(res => {
            this.data = res
        })
    }
}" x-init="getData()">

<label for="topics">Vyber téma:</label>
<select id="topics" x-model="topic">
<option value="1">Algoritmus, vývojové diagramy, deklarace proměnných</option>
<option value="2">Binární vyhledávací strom</option>
<option value="3">Bitmapová počítačová grafika</option>
<option value="4">Cyklus s podmínkou</option>
<option value="5">Cyklus s pevným počtem kroků</option>
<option value="6">Databázové systémy</option>
<option value="7">Historie výpočetní techniky, hardware</option>
<option value="8">Homogenní datové struktury</option>
<option value="9">Informace a informační zdroje, číselné soustavy</option>
<option value="10">Internet – historie, struktura a využití, služby internetu</option>
<option value="11">Lineární spojový seznam</option>
<option value="12">Multimedia</option>
<option value="13">Nehomogenní datové struktury</option>
<option value="14">Počítačové sítě</option>
<option value="15">Počítačové viry a další malware</option>
<option value="16">Prezentační technologie</option>
<option value="17">Procedury a funkce, druhy parametrů</option>
<option value="18">Software – vývoj, rozdělení, operační systémy</option>
<option value="19">Tabulkové kalkulátory, textové editory</option>
<option value="20">Teorie grafů, backtracking</option>
<option value="21">Tvorba webových stránek</option>
<option value="22">Úplný a neúplný podmíněný příkaz</option>
<option value="23">Vektorová počítačová grafika</option>
<option value="24">Základní metody vyhledávání a třídění</option>
<option value="25">Záznamová média a zálohování dat, komprimace</option>
</select>

<div x-html="data[topic - 1]"></div>

</div>
