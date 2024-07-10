---
title: Reverse engineer Android app-verkeer zonder root
authors:
  - marijn-kok
date: 2024-07-10T01:39:30+02:00
featuredImage: '/images/mitmproxy.png'
categories: []
tags: [tutorial, android]
summary: Altijd al eens willen weten hoe een app communiceert met zijn server? Met behulp van apk-mitm en mitmproxy kan je het verkeer van een app afvangen en analyseren zonder root.
---
Altijd al eens willen weten hoe een app communiceert met zijn server? Met behulp van apk-mitm en mitmproxy kan je het verkeer van een app afvangen en analyseren **zonder root**. In deze tutorial leg ik uit hoe je dit doet.

## Vereisten

- Android emulator (of een fysiek Android device verbonden met adb)
- [mitmproxy] (voor mitmweb)
- [apk-mitm]
- adb (van [platform-tools])

## 1. APK patchen

1. Download de app die je wil reverse engineeren van de Play Store _(al bij de hand? Ga naar stap 4)_
2. Vind het pad van de apk: `adb shell pm list packages -f -3`, optioneel met grep erachteraan. Dit geeft bijvoorbeeld `package:/data/app/~~9Jg8vCv5DYdaNbVeICtEqA==/nl.voedingscentrum.slimkoken-SzgrrdeyVzQfDNDQvi091g==/base.apk=nl.voedingscentrum.slimkoken`. Het pad is dan vanaf /data t/m .apk. Of met RegEx: `\/data.*apk`
3. Download de apk naar de huidige map: `adb pull /data/app/<apk-path> .`
4. Gebruik apk-mitm om de apk te patchen: `apk-mitm <apk-path>`
5. Installeer de apk op de emulator: `adb install <patched-apk-path>`

## 2. Afvangen van verkeer

1. Start de mitm: `mitmweb`
3. Configureer de proxy op de emulator of het apparaat _(Als dit niet werkt in de instellingen van de emulator, kan je ook de proxy instellen in de instellingen-app. Zie https://stackoverflow.com/a/78154250)_

## 3. CA certificaat installeren op Android

1. Open http://mitm.it/ in de browser van de emulator of het apparaat _(Als dit niet werkt, heb je waarschijnlijk de proxy niet goed ingesteld)_
2. Download het certificaat
3. Installeer het certificaat in de instellingen van het systeem

**Nu kan je het verkeer van de app zien in het mitm dashboard!** Succes met reverse engineeren.

[mitmproxy]: https://mitmproxy.org/
[apk-mitm]: https://www.npmjs.com/package/apk-mitm
[platform-tools]: https://developer.android.com/studio/releases/platform-tools
