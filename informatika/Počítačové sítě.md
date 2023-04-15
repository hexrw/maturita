---
layout: default
title: Počítačové sítě
permalink: /informatika/pocitacove-site/
---

## Počítačová síť

- skupina počítačů a síťových zařízení vzájemně spojených komunikačním
médiem
- umožňuje sdílení informací
- sdílení informací probíhá pomocí paketů
- bloků dat uzpůsobený pro přenos v počítačových sítích

### Dělení

#### Dle velikosti sítě

- **PAN** - personal area network
    - osobní síť, nejmenší - spojení PC-mobil přes bluetooth
- **LAN** - local area network
    - místní síť, většinou jedna budova, jedno místo
- **MAN** - metropolitan area network
    - propojení jednoho města
- **WAN** - wide area network
    - celá síť, propojení celého světa

#### Dle typu připojení

- **peer-to-peer**
    - každé zařízení je server i klient zároveň
    - v případě selhání jednoho nebo více uzlů (klientů) nedochází k selhání sítě
- **client-server**
    - jedno nebo více zařízení jsou servery a klienti se k ním připojují
    - v případě selhání všech serverů selže i celá síť

#### Dle způsobu připojení

- **bezdrátové**
    - Wi-Fi
    - Bluetooth
- **drátové**
    - kroucená dvojlinka
    - koaxiální kabel
    - optický kabel

#### Dle topologie zapojení

- **hvězda** (star)
- **kruh** (ring)
- **strom** (tree)
- **lineární** (line)
- **různohodnotná** (mesh)
- **sběrnice** (bus)
- **plná** (full)

![PS 2](/assets/ps-2.png)

### Síťové prvky

#### IP adresa

- číslo jednoznačně identifikující síťové rozhraní v počítačové sítí
používající TCP/IP protokol

##### IPv4

- **32 bitová adresa**
- poskytuje teoreticky zhruba 2<sup>32</sup> adres, prakticky je to méně díky rezervaci některých adres a díky sdružování do podsítí
- zapisována ve formátu x.x.x.x, kde x nabývá hodnot mezi 0 a 255
- pro soukromé sítě jsou rezervovány adresy (viz RFC1918)
    - 10.0.0.0/8 (255.0.0.0)
    - 172.16.0.0/12 (255.240.0.0)
    - 192.168.0.0/16 (255.255.0.0)
- počet adres byl vyčerpán v roce 2011 &rarr; IPv6

##### IPv6

- **128 bitová adresa**
- nahrazuje IPv4
- přináší masivní rozšíření adresního prostoru - 2<sup>128</sup> adres
- adresa je zapsána jako 8 skupin čtyř hexadecimálních číslic
- hlavním problémem IPv6 protokolu je velmi malé nasazení v reálném světě

##### Protokol TCP/IP

- *transmission control protocol*/*internet protocol*
- sada protokolů pro komunikaci v počítačových sítích
- IP - protokol pro propojení sítí
- TCP - protokol pro řízení přenosu
- zajišťuje spolehlivý obousměrný přenos dat na příslušných dvou uzlech

![PS 1](/assets/ps-1.png)

## Typické zapojení LAN sítě

<img alt="PS 3" src="/assets/ps-3.png" class="dark:invert" />
