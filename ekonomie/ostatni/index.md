---
layout: default
title: Ústní a praktická část maturitní zkoušky
permalink: /ekonomie/ustni-a-prakticka-cast-maturitni-zkousky/
---

<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>

<div x-data="{
    topic: '1',
    data: [],
    getData() {
        let promises = []
        for (i = 1; i <= 20; i++) {
            promises.push(
                fetch('/ekonomie/ostatni/' + i)
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
    <option value="1">Základní ekonomické pojmy a subjekty národního hospodářství</option>
    <option value="2">Marketing</option>
    <option value="3">Daňová soustava ČR zaměřená na přímé daně</option>
    <option value="4">Hospodářská politika státu</option>
    <option value="5">Personální činnost podniku</option>
    <option value="6">Dlouhodobý majetek podniku</option>
    <option value="7">Podnik a podnikání</option>
    <option value="8">Oběžný majetek podniku</option>
    <option value="9">Daňová soustava ČR zaměřená na nepřímé daně</option>
    <option value="10">Odměňování</option>
    <option value="11">Národní hospodářství</option>
    <option value="12">Cenné papíry</option>
    <option value="13">Centrální banka</option>
    <option value="14">Obchodování s cennými papíry</option>
    <option value="15">Obchodní banky</option>
    <option value="16">Finanční řízení podniku</option>
    <option value="17">Daňová evidence</option>
    <option value="18">Náklady a výnosy podniku</option>
    <option value="19">Trh a tržní mechanismus</option>
    <option value="20">Management</option>
</select>

<div x-html="data[topic - 1]"></div>
