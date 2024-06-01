---
title: Herstel AAC bestanden met PhotoRec
authors:
  - marijn-kok
date: 2024-05-30T22:59:55Z
featuredImage: /images/photorec.png
categories: []
tags: [tutorial, dataherstel, photorec]
---
Recentelijk had ik per ongeluk een aantal *AAC*-muziekbestanden verwijderd. Ik wilde een mapje genaamd test_deleteme verwijderen (ja, ik ben creatief met namen), maar realiseerde niet dat ik ook nog een mapje genaamd test had. Ik typte `rm -rf te` en drukte op <kbd>Tab</kbd>. Je kan raden wat er gebeurde... het verkeerde mapje *test* was verwijderd.

Ik downloadde direct het bestandherstelprogramma PhotoRec (op Fedora: `sudo dnf install testdisk`) en probeerde vervolgens in de bestandslijst aac te zoeken. Maar zelfs na al 22 jaar te bestaan ondersteunt PhotoRec kennelijk geen AAC. Het internet leek ook geen soelaas te bieden: ik vond slechts [één thread uit 2014 met deze vraag][1], zonder antwoorden. (Dit probleem komt ook weleens voor bij programmeren. Een bitterzoet gevoel)

Gelukkig biedt PhotoRec de mogelijkheid om zelf ondersteuning voor bestandstypen toe te voegen. Dit wordt uitgelegd in hun gids "[Creating custom signature for PhotoRec][2]". Het vereist echter wat gedoe en uitzoekwerk, dus maak ik het makkelijk voor je: **dit is wat je nodig hebt.**

1. Kies een veilige map waar je PhotoRec gaat uitvoeren. Let op: dat is dus NIET op de partitie waar de verloren gegevens staan!
2. Sla dit bestand in die map op: <a download="photorec.sig" href='data:,aac 11 "libfaac"'>photorec.sig</a>
3. Voer PhotoRec vanuit die map uit en selecteer "custom Own custom signatures" bij de file format selectiekeuze. Het zal dan ook aac-bestanden herkennen.

Dit is vanzelfsprekend een onvolledig stappenplan voor het gebruik van het hele programma. Raadpleeg daarvoor de [PhotoRec Step By Step][3] gids.

Succes en veel geluk toegewenst!

PS Zelfs het downloaden van PhotoRec was eigenlijk geen verstandige keuze; dit was ook op dezelfde partitie als waar de verwijderde gegevens stonden. Ik had echter geen apart apparaat klaarstaan. Gek genoeg kon het wel veel andere verwijderde bestanden vinden.

[1]: https://forum.cgsecurity.org/phpBB3/viewtopic.php?t=3429
[2]: https://www.cgsecurity.org/testdisk_doc/photorec_custom_signature.html
[3]: https://www.cgsecurity.org/wiki/PhotoRec_Step_By_Step

