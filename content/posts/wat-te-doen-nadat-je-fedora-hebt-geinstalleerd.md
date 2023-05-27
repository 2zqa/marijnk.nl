---
title: Wat te doen nadat je Fedora hebt geïnstalleerd (bijgewerkt april 2023)
author: Marijn
type: post
date: 2022-06-05T10:45:58+00:00
url: /wat-te-doen-nadat-je-fedora-hebt-geinstalleerd/
featuredImage: /images/fedora.png
categories:
  - Linux
tags:
  - Fedora
  - setup
  - tutorial

---
De laatste paar jaren heb ik vele besturingssystemen gebruikt: Linux Mint, Ubuntu, Manjaro, Arch Linux, Pop!_OS en Fedora, maar ook Windows en MacOS. Voor Fedora, Windows en MacOS heb ik een lijst van aanpassingen bijgehouden voor het geval ik in de toekomst weer vanaf een schone installatie wil beginnen.

Dit is dus mijn gids voor Fedora, omgezet naar artikel-vorm. Het is misschien geschreven voor Fedora, maar de instructies zijn met wat vindingrijkheid ook op andere systemen uit te voeren. Tenslotte is dit artikel geschreven voor een Nederlandse installatie, omdat ik dit zelf zo gebruik.

## 1. Hostname instellen {.wp-block-heading}

In andere woorden: je apparaat een leuke naam geven.

Ga naar Instellingen > Info > Apparaatnaam en kies een nieuwe naam. Mijne heet lapdog. 🙂

## 2. Handige flatpak apps {.wp-block-heading}

_Flatpak_ is een prachtig systeem om (zonder root!) gemakkelijk apps te installeren, beheren en te verwijderen. Bijna al mijn apps zijn geïnstalleerd via flatpak. Ik maak veel gebruik van onderstaande apps en kan ze sterk aanraden. Flatpak apps zijn te installeren vanuit de Software-app of via de terminal: `flatpak install <pakketnaam>`.

| Naam | Pakketnaam | Omschrijving |
|:---:|:---:|:---:|
| Curtail | com.github.huluti.Curtail | Comprimeer foto’s. Heeft optie om zonder of met kwaliteitsverlies te comprimeren (met kwaliteitsverlies betekent nóg meer ruimtebesparing) |
| Metagegevensopruiming | `fr.romainvigier.MetadataCleaner` | Metadata van bestanden verwijderen, aan te raden voordat je foto’s op het wereldwijde web zet |
| Apostrophe | org.gnome.gitlab.somas.Apostrophe | Markdown tekstbewerker |
| Amberol | io.bassi.Amberol | Lokale muziekspeler |
| Uitbreidingsbeheer | com.mattjakeman.ExtensionManager | Beheer en installeer uitbreidingen voor GNOME |
| Pinta | com.github.PintaProject.Pinta | Handig fotobewerkingsprogramma, alternatief op het Windows exclusieve programma “Paint.NET” |
| Xournal++ | com.github.xournalpp.xournalpp | Pdf’s annoteren, notities maken, werkt goed met touchscreen |
| MusicBrainz | org.musicbrainz.Picard | Muziektagger |
| Prism Launcher | org.prismlauncher.PrismLauncher | Alternatieve Minecraft launcher met moddingondersteuning |
| Thunderbird | org.mozilla.Thunderbird | E-mailprogramma |


## 3. Handige uitbreidingen {.wp-block-heading}

Als je Uitbreidingsbeheer hebt geïnstalleerd, kan je GNOME op allerlei fronten aanpassen. Persoonlijk ben ik zeer tevreden met de standaardervaring van GNOME op Fedora, maar gebruik toch een paar uitbreidingen:

  * Application Volume Mixer: Verander snel volume van apps
  * Grand Theft Focus: Schakelt de &#8220;programma is gereed&#8221; meldingen uit
  * Night Theme Switcher: Wisselt automatisch tussen een licht en donker thema, zie kopje 8

## 4. Ctrl op capslock {.wp-block-heading}

Als je veelvuldig gebruik maakt van sneltoetsen zoals ik, is ctrl op caps lock zetten iets wat ik zeer kan aanbevelen. Het is even wennen, maar daarna wil je niet meer terug. Ctrl + A, Ctrl + S en Ctrl + W worden opeens subtiele bewegingen in plaats van gymnastiek voor je pink!

  1. Installeer de Afstellingen-app: `sudo dnf install gnome-tweak-tool`
  2. Open de app
  3. Ga naar Toetsenbord & muis > Extra vormgevingsopties > Positie van Ctrl-toets. Vink &#8220;CapsLock is Ctrl-toets&#8221; aan.

## 5. Trackpad ingeschakeld houden tijdens typen {.wp-block-heading}

Mocht je een trackpad gebruiken maar ook spelletjes willen spelen, dan is het aan te raden om dit te doen. Anders kan je niet tegelijk lopen en rondkijken bijvoorbeeld.

Ga weer naar de Afstellingen-app en vervolgens naar Toetsenbord & muis. Schakel vervolgens &#8220;Uitschakelen tijdens typen&#8221; uit onder Touchpad.

## 6. Firefox instellingen {.wp-block-heading}

Ik gebruik Firefox al jaren en kan het sterk aanraden. Er zijn echter een paar aanpassingen die ik maak om het nog beter te maken.

Sinds recente versies van Fedora wordt hardwareversnelling gebruikt voor videos (zoals bij YouTube), maar niet alle videoformaten worden hierdoor ondersteund. Installeer daarom de [enhanced-h264ify][1] extensie om gebruik te maken van deze versnelling.

Verder is scrollen in Firefox te snel op mijn laptop. Om dit op te lossen is gebruik gemaakt van de volgende configuratie:

<pre class="wp-block-code"><code>mousewheel.min_line_scroll_amount: 180
mousewheel.default.delta_multiplier_x: 30
mousewheel.default.delta_multiplier_y: 30</code></pre>

## 7. adw-gtk3 thema {.wp-block-heading}

[Libadwaita][2] is een nieuwe bibliotheek van bouwblokken om moderne apps mee te maken. Sinds het officieel is vrijgegeven zijn er steeds meer apps die er gebruik van maken. Om ook oude apps als nieuw te laten lijken, is het thema adw-gtk3 ontwikkeld. Kijk op de GitHub pagina voor installatie-instructies: <a href="https://github.com/lassekongo83/adw-gtk3#other-install-options" data-type="URL">github.com/lassekongo83/adw-gtk3</a>.

Installeer de flatpak én de reguliere versie om ervoor te zorgen dat al je apps het nieuwe thema krijgen. Het thema kan met de Afstellingen-app ingesteld worden onder het kopje &#8220;Uiterlijk&#8221;, of automatisch met een extensie. Zie daarvoor het volgende kopje!<figure class="wp-block-gallery has-nested-images columns-default is-cropped alignwide wp-block-gallery-1 is-layout-flex"> <figure class="wp-block-image size-full">

[<img decoding="async" loading="lazy" width="694" height="533" data-id="129"  src="https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-40-12.png" alt="Tilix met standaard Adwaita thema" class="wp-image-129" srcset="https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-40-12.png 694w, https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-40-12-300x230.png 300w" sizes="(max-width: 694px) 100vw, 694px" />][3]<figcaption class="wp-element-caption">Standaard-thema (oud)</figcaption></figure> <figure class="wp-block-image size-full is-style-default">[<img decoding="async" loading="lazy" width="712" height="551" data-id="128"  src="https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-39-46.png" alt="Tilix met adw-gtk3 thema" class="wp-image-128" srcset="https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-39-46.png 712w, https://marijnk.nl/wp-content/uploads/2022/06/Schermafdruk-van-2022-06-04-19-39-46-300x232.png 300w" sizes="(max-width: 712px) 100vw, 712px" />][4]<figcaption class="wp-element-caption">adw-gtk3 (nieuw)</figcaption></figure> <figcaption class="blocks-gallery-caption wp-element-caption">Tilix met en zonder thema</figcaption></figure>

## 8. Automatische nachtmodus {.wp-block-heading}

Het gekibbel over donker versus licht thema is zo passé. De ware oplossing is een automatisch ingestelde lichte en donkere modus gebaseerd op de stand van de zon, zoals moeder natuur het bedoelde. 😉

Installeer eerst Uitbreidingsbeheer via de Software-app. Zoek in de app naar Night Theme Switcher en installeer deze. Open de instellingen van de extensie en ga naar &#8220;Thema&#8217;s&#8221;. Klik op &#8220;GTK-thema&#8217;s afwisselen&#8221; en kies je lichte en donkere thema, bijvoorbeeld adw-gtk3 en adw-gtk3-dark.

Tip: installeer ook [Dark Reader][5] om websites in het donker weer te geven. Dit kan ook ingesteld worden om te reageren op je systeemthema.

## Extra&#8217;s: {.wp-block-heading}

Deze dingen zijn wat specifieker aan mijn gebruik, maar kunnen nog steeds handig zijn om te weten.

## 9. Trackpad scrollsnelheid herstellen {.wp-block-heading}

Mocht je merken dat je trackpad veel te gevoelig is na je installatie (of bij meer apps dan alleen Firefox), dan deel ik hierbij graag de beste oplossing die ik gevonden heb. Hopelijk wordt dit in een toekomstige versie van GNOME goed opgelost zoals omschreven in [dit issue][6], maar in de tussentijd zullen we afhankelijk zijn van deze hack genaamd libinput-config.

De instructies om deze oplossing te installeren zijn te vinden op [https://gitlab.com/warningnonpotablewater/libinput-config][7]. Het vereist wel dat je een aantal packages hebt geïnstalleerd:

`sudo dnf install libinput-devel gcc-c++ meson ninja-build libudev-devel`

Verder ziet mijn `/etc/libinput.conf` er als volgt uit:

<pre class="wp-block-code"><code>scroll-factor=0.2
gesture-speed=0.85</code></pre>

## 10. Nieuwste Java-versie {.wp-block-heading}

Om altijd de laatste versie van Java te hebben, voer je het volgende commando uit:

`sudo dnf install java-latest-openjdk`

Stel optioneel je standaard java-versie in met:

`sudo update-alternatives --config java`

## 11. OneDrive {.wp-block-heading}

Vanwege dataverlies op een oude Nextcloud instantie van mij vertrouw ik mezelf niet zo goed meer met het veilig stellen van data. Daarom gebruik ik een externe hostingoplossing, wat op dit moment Microsoft OneDrive is. Op Linux is OneDrive helaas niet officieel beschikbaar behalve via de website, maar rclone heeft functionaliteit om je OneDrive bestanden te synchroniseren. Bekijk hun website voor de instructies: <https://rclone.org/onedrive/>

 [1]: https://addons.mozilla.org/en-US/firefox/addon/enhanced-h264ify/
 [2]: https://blogs.gnome.org/alexm/2021/12/31/libadwaita-1-0/
 [3]: https://marijnk.nl/?attachment_id=129
 [4]: https://marijnk.nl/?attachment_id=128
 [5]: https://darkreader.org/
 [6]: https://gitlab.gnome.org/GNOME/gtk/-/issues/4793
 [7]: https://gitlab.com/warningnonpotablewater/libinput-config#how-to-build-and-install
