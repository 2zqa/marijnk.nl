---
title: Wat te doen nadat je Fedora hebt geïnstalleerd (bijgewerkt maart 2024)
authors:
 - marijn-kok
toc: true
date: 2022-06-05T10:45:58+00:00
lastmod: 2024-03-16T18:00:00+00:00
featuredImage: /images/fedora.png
summary: Een lijst van aanpassingen, apps en tips die handig zijn na een nieuwe Fedora installatie. Ook nuttig als je een andere Linux distro gebruikt.
categories:
  - Linux
tags:
  - Fedora
  - setup
  - tutorial
---
De laatste paar jaren heb ik vele besturingssystemen gebruikt: Linux Mint, Ubuntu, Manjaro, Arch Linux, Pop!_OS en Fedora, maar ook Windows en MacOS. Voor Fedora, Windows en MacOS heb ik een lijst van aanpassingen bijgehouden voor het geval ik in de toekomst weer vanaf een schone installatie wil beginnen.

Dit is dus mijn gids voor Fedora, omgezet naar artikel-vorm. Het is misschien geschreven voor Fedora, maar de instructies zijn met wat vindingrijkheid ook op andere systemen uit te voeren. Tenslotte is dit artikel geschreven voor een Nederlandse installatie, omdat ik dit zelf zo gebruik.

## 1. Hostname instellen

In andere woorden: je apparaat een leuke naam geven.

Ga naar Instellingen > Info > Apparaatnaam en kies een nieuwe naam. Mijne heet lapdog. 🙂

## 2. Handige flatpak apps

_Flatpak_ is een prachtig systeem om (zonder root!) gemakkelijk apps te installeren, beheren en te verwijderen. Bijna al mijn apps zijn geïnstalleerd via flatpak. Ik maak veel gebruik van onderstaande apps en kan ze sterk aanraden. Flatpak apps zijn te installeren vanuit de Software-app of via de terminal: `flatpak install <pakketnaam>`.

| Naam | Pakketnaam | Omschrijving |
|:---:|:---:|:---:|
| Curtail | com.github.huluti.Curtail | Comprimeer foto’s. Heeft optie om zonder of met kwaliteitsverlies te comprimeren (met kwaliteitsverlies betekent nóg meer ruimtebesparing) |
| Metagegevensopruiming | fr.romainvigier.MetadataCleaner | Metadata van bestanden verwijderen, aan te raden voordat je foto’s op het wereldwijde web zet |
| Apostrophe | org.gnome.gitlab.somas.Apostrophe | Markdown tekstbewerker |
| Amberol | io.bassi.Amberol | Lokale muziekspeler |
| Uitbreidingsbeheer | com.mattjakeman.ExtensionManager | Beheer en installeer uitbreidingen voor GNOME |
| Pinta | com.github.PintaProject.Pinta | Handig fotobewerkingsprogramma, alternatief op het Windows exclusieve programma “Paint.NET” |
| Xournal\+\+ | com.github.xournalpp.xournalpp | Pdf’s annoteren, notities maken, werkt goed met touchscreen |
| MusicBrainz | org.musicbrainz.Picard | Muziektagger |
| Prism Launcher | org.prismlauncher.PrismLauncher | Alternatieve Minecraft launcher met moddingondersteuning |
| Thunderbird | org.mozilla.Thunderbird | E-mailprogramma |

## 3. Handige uitbreidingen

Als je Uitbreidingsbeheer hebt geïnstalleerd, kan je GNOME op allerlei fronten aanpassen. Persoonlijk ben ik zeer tevreden met de standaardervaring van GNOME op Fedora, maar gebruik toch een paar uitbreidingen:

  * Application Volume Mixer: Verander snel volume van apps
  * Grand Theft Focus: Schakelt de "programma is gereed" meldingen uit
  * Night Theme Switcher: Wisselt automatisch tussen een licht en donker thema, zie kopje 8

## 4. Ctrl op capslock

Als je veelvuldig gebruik maakt van sneltoetsen zoals ik, is ctrl op caps lock zetten iets wat ik zeer kan aanbevelen. Het is even wennen, maar daarna wil je niet meer terug. Ctrl + A, Ctrl + S en Ctrl + W worden opeens subtiele bewegingen in plaats van gymnastiek voor je pink!

  1. Installeer de Afstellingen-app: `sudo dnf install gnome-tweak-tool`
  2. Open de app
  3. Ga naar Toetsenbord & muis > Extra vormgevingsopties > Positie van Ctrl-toets. Vink "CapsLock is Ctrl-toets" aan.

## 5. Vensters vergroten en verplaatsen zonder de rand te hoeven vinden

Vensters manipuleren kan soms best moeizaam zijn. De rand van een venster is smal en een muis beweegt redelijk snel. Een alternatief is om met de meta-toets[^1] in combinatie met de rechtermuisknop de grootte van vensters te veranderen, en om met de linkermuisknop het venster te verplaatsen.

Ga naar Afstellingen > Windows en schakel "Afmetingen wijzigen met rechtermuisknop" in.


{{< figure caption="Video van een venster dat vergroot en verplaatst wordt, zonder dat de rand wordt aangeraakt." >}}
<video src="images/resize-move-window.webm" width=75% controls>Video van een venster dat vergroot en verplaatst wordt, zonder dat de rand wordt aangeraakt</video>
{{< /figure >}}

## 6. Trackpad ingeschakeld houden tijdens typen

Mocht je een trackpad gebruiken maar ook spelletjes willen spelen, dan is het aan te raden om dit te doen. Anders kan je niet tegelijk lopen en rondkijken bijvoorbeeld.

Ga weer naar de Afstellingen-app en vervolgens naar Toetsenbord & muis. Schakel vervolgens "Uitschakelen tijdens typen" uit onder Touchpad.

## 7. Firefox instellingen

Ik gebruik Firefox al jaren en kan het sterk aanraden. Er zijn echter een paar aanpassingen die ik maak om het nog beter te maken.

Sinds recente versies van Fedora wordt hardwareversnelling gebruikt voor videos (zoals bij YouTube), maar niet alle videoformaten worden hierdoor ondersteund. Installeer daarom de [enhanced-h264ify][1] extensie om gebruik te maken van deze versnelling.

Verder is scrollen in Firefox te snel op mijn laptop. Om dit op te lossen is gebruik gemaakt van de volgende configuratie:

```yaml
mousewheel.min_line_scroll_amount: 180
mousewheel.default.delta_multiplier_x: 30
mousewheel.default.delta_multiplier_y: 30
```

## 8. adw-gtk3 thema

[Libadwaita][2] is een bibliotheek van bouwblokken om moderne apps mee te maken. Sinds het officieel is vrijgegeven zijn er steeds meer apps die er gebruik van maken. Om ook oude apps als nieuw te laten lijken, is het thema adw-gtk3 ontwikkeld. Kijk op de GitHub pagina voor installatie-instructies: https://github.com/lassekongo83/adw-gtk3#other-installation-options

Installeer de flatpak én de reguliere versie om ervoor te zorgen dat al je apps het nieuwe thema krijgen. Het thema kan met de Afstellingen-app ingesteld worden onder het kopje "Uiterlijk", of automatisch met een extensie. Zie daarvoor het volgende kopje!

{{< figure caption="Standaard-thema (oud)" >}}{{< picture src="images/tilix-adwaita.png" >}}{{< /figure >}}
{{< figure caption="adw-gtk3 (nieuw)" >}}{{< picture src="images/tilix-adw-gtk3.png" >}}{{< /figure >}}

## 9. Automatische nachtmodus

Het gekibbel over donker versus licht thema is zo passé. De ware oplossing is een automatisch ingestelde lichte en donkere modus gebaseerd op de stand van de zon, zoals moeder natuur het bedoelde. 😉

Installeer eerst Uitbreidingsbeheer via de Software-app. Zoek in de app naar "Night Theme Switcher" en installeer deze. Open de instellingen van de extensie en ga naar "Thema's". Klik op "GTK-thema's afwisselen" en kies je lichte en donkere thema, bijvoorbeeld adw-gtk3 en adw-gtk3-dark.

Tip: installeer ook [Dark Reader][5] om websites in het donker weer te geven. Dit kan ook ingesteld worden om te reageren op je systeemthema.

Nog een tip: Als je liever handmatig tussen donkere en lichte modus wisselt, raad ik aan om "Legacy (GTK3) Theme Scheme Auto Switcher" te installeren. Zo worden oude apps ook naar donkere modus gewisseld, in plaats van alleen moderne apps.

## 10. Alt-tab zoals op Windows

Hoewel ik waardeer dat GNOME probeert de bureaubladstandaarden te verbeteren waar anderen dat niet durven, slaan ze met dit risico geheid de plank soms mis. Zo ook hier: standaard schakelt alt-tab alleen tussen vensters van dezelfde app, in plaats van schakelen tussen recent gebruikte vensters. Dit kan je als volgt herstellen:

Ga naar instellingen > Toetsenbord > Sneltoetsen bekijken en aanpassen > Navigatie, en stel "Tussen toepassingen schakelen" in op Alt+Tab.

## 11. Tikken om te klikken

Voor laptopgebruikers: als je ook gek wordt van het lawaai dat sommige trackpads maken als je ze indrukt, kan tikken om te klikken veel praktischer zijn.

Dit kan je inschakelen door te gaan naar de instellingen > Muis en touchpad te gaan en "Tikken om te klikken" in te schakelen.

## Extra's:

Deze dingen zijn wat specifieker aan mijn gebruik, maar kunnen nog steeds handig zijn om te weten.

### 10. Trackpad scrollsnelheid herstellen

Mocht je merken dat je trackpad veel te gevoelig is na je installatie (of bij meer apps dan alleen Firefox), dan deel ik hierbij graag de beste oplossing die ik gevonden heb. Hopelijk wordt dit in een toekomstige versie van GNOME goed opgelost zoals omschreven in [dit issue][6], maar in de tussentijd zullen we afhankelijk zijn van deze hack genaamd libinput-config.

De instructies om deze oplossing te installeren zijn te vinden op https://gitlab.com/warningnonpotablewater/libinput-config#how-to-build-and-install. Het vereist wel dat je een aantal packages hebt geïnstalleerd:

`sudo dnf install libinput-devel gcc-c++ meson ninja-build libudev-devel`

Verder ziet mijn `/etc/libinput.conf` er als volgt uit:

```ini
scroll-factor=0.2
gesture-speed=0.85
```

### 11. Nieuwste Java-versie

Om altijd de laatste versie van Java te hebben, voer je het volgende commando uit:

`sudo dnf install java-latest-openjdk`

Stel optioneel je standaard java-versie in met:

`sudo update-alternatives --config java`

### 12. OneDrive

Vanwege dataverlies op een oude Nextcloud instantie van mij vertrouw ik mezelf niet zo goed meer met het veilig stellen van data. Daarom gebruik ik een externe hostingoplossing, wat op dit moment Microsoft OneDrive is. Microsoft stelt OneDrive helaas niet officieel beschikbaar op Linux behalve via de website, maar rclone heeft functionaliteit om je OneDrive-bestanden te synchroniseren ([OneDrive komt ook binnenkort naar GNOME][7] gelukkig). Volg eerst rclone's instructies op hun website: <https://rclone.org/onedrive/>

Volg daarna de volgende stappen:

1. Maak een OneDrive map aan in je thuis-map: `mkdir ~/OneDrive`
2. Maak een map voor user systemd-services, mocht die nog niet bestaan: `mkdir -p ~/.config/systemd/user/`
3. Maak vervolgens het bestand `rclone-onedrive.service` aan met de volgende inhoud:

    ```ini
    [Unit]
    Description=OneDrive (rclone)
    AssertPathIsDirectory=%h/OneDrive
    # Make sure we have network enabled
    After=network.target

    [Service]
    Type=simple

    ExecStart=/usr/bin/rclone mount --vfs-cache-mode full onedrive: %h/OneDrive

    # Perform lazy unmount
    ExecStop=/usr/bin/fusermount -zu %h/OneDrive

    # Restart the service whenever rclone exists with non-zero exit code
    Restart=on-failure
    RestartSec=3

    [Install]
    # Autostart after reboot
    WantedBy=default.target
    ```

4. Schakel tenslotte de service in met het volgende commando (vereist géén root). De `--now` parameter start de service ook direct[^2]. `systemctl enable --now --user rclone-onedrive.service`

[1]: https://addons.mozilla.org/en-US/firefox/addon/enhanced-h264ify/
[2]: https://blogs.gnome.org/alexm/2021/12/31/libadwaita-1-0/
[3]: https://marijnk.nl/?attachment_id=129
[4]: https://marijnk.nl/?attachment_id=128
[5]: https://darkreader.org/
[6]: https://gitlab.gnome.org/GNOME/gtk/-/issues/4793
[7]: https://www.omgubuntu.co.uk/2024/02/onedrive-support-planned-gvfs-gnome-46

[^1]: Ook bekend als de Windows- of Commandtoets.
[^2]: https://www.freedesktop.org/software/systemd/man/latest/systemctl.html#enable%20UNIT%E2%80%A6
