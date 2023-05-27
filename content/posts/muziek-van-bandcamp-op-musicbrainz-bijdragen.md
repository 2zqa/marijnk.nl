---
title: Muziek van Bandcamp op MusicBrainz bijdragen
author: Marijn
type: post
date: 2022-05-29T22:35:20+00:00
url: /muziek-van-bandcamp-op-musicbrainz-bijdragen/
categories:
  - Muziek
tags:
  - Bandcamp
  - MusicBrainz
  - MusicBrainz Picard
  - tutorial

---
**AANPASSING:** Onnodige stappen weggehaald en uitleg over streepjescodes toegevoegd. Bedankt aerozol!

MusicBrainz Picard is een programma om je lokale muziekbibliotheek bij te houden. Het maakt gebruik van de open muziekencyclopedie MusicBrainz. Wanneer het werkt is het fijn, maar soms wordt muziek niet herkend. Wat doe je dan?

Als je muziek niet herkend wordt, betekent dit dat het nog niet op MusicBrainz staat. Je zou kunnen wachten tot iemand anders het doet, maar dan kan je soms lang wachten. Daarom leg ik je in dit artikel uit hoe je het heft in eigen handen kan nemen, in de vorm van korte, beknopte instructies.

## Voorbereiding {.wp-block-heading}

  1. Installeer violentmonkey ([Firefox][1], [Chrome][2]) en vervolgens [dit userscript][3] en [dit userscript][4].
  2. (Voor AcoustID) Open MusicBrainz picard en ga naar Opties > Opties > Vingerafdrukken en druk onder API-sleutel op de knop &#8220;API-sleutel verkrijgen&#8221;. Volg de stappen en vul je API-sleutel in.

## Importeren {.wp-block-heading}

  1. Ga naar Bandcamp pagina die je wil importeren, e.g. [myrone.bandcamp.com/track/track-day][5]
  2. Druk op &#8220;Import into MB&#8221;. (Als je deze knop niet ziet, zorg dat je het userscript correct geïnstalleerd hebt)<figure class="wp-block-image size-large is-style-default">

<img decoding="async" loading="lazy" width="1024" height="576" src="https://marijnk.nl/wp-content/uploads/2022/05/Importeerknop-min-1024x576.png" alt="Bandcamp pagina van Myrone's Track Day met twee knoppen: &quot;Import into MB&quot; en &quot;Search in MB&quot;" class="wp-image-100" srcset="https://marijnk.nl/wp-content/uploads/2022/05/Importeerknop-min-1024x576.png 1024w, https://marijnk.nl/wp-content/uploads/2022/05/Importeerknop-min-300x169.png 300w, https://marijnk.nl/wp-content/uploads/2022/05/Importeerknop-min-768x432.png 768w, https://marijnk.nl/wp-content/uploads/2022/05/Importeerknop-min.png 1280w" sizes="(max-width: 1024px) 100vw, 1024px" /> </figure> 

<ol start="3">
  <li>
    Verander de volgende velden:<ul>
      <li>
        Artiest: Als het vakje niet groen is, druk op het vergrootglas en kies de juiste artiest.
      </li>
      <li>
        Streepjescode: als het nummer ook op Spotify, iTunes of Deezer staat, kan je met de desbetreffende URL op <a href="https://atisket.pulsewidth.org.uk">atisket.pulsewidth.org.uk</a> de streepjescode (barcode/UPC) verkrijgen.
      </li>
    </ul>
    
    <ul>
      <li>
        Externe websites: Eigen invulling. Met bovengenoemde pagina kan je behalve de streepjescode ook de URL voor Spotify, Apple Music/iTunes en Deezer verkrijgen. Verdere voorbeelden van externe websites zijn TIDAL en SoundCloud.
      </li>
    </ul>
  </li>
</ol><figure class="wp-block-image size-large is-resized">

<img decoding="async" loading="lazy" src="https://marijnk.nl/wp-content/uploads/2022/05/Informatie-over-de-uitgave-min-925x1024.png" alt="" class="wp-image-99" width="694" height="768" srcset="https://marijnk.nl/wp-content/uploads/2022/05/Informatie-over-de-uitgave-min-925x1024.png 925w, https://marijnk.nl/wp-content/uploads/2022/05/Informatie-over-de-uitgave-min-271x300.png 271w, https://marijnk.nl/wp-content/uploads/2022/05/Informatie-over-de-uitgave-min-768x850.png 768w, https://marijnk.nl/wp-content/uploads/2022/05/Informatie-over-de-uitgave-min.png 1280w" sizes="(max-width: 694px) 100vw, 694px" /> </figure> 

<ol start="4">
  <li>
    Druk op &#8220;Volgende&#8221; tot je uitkomt bij Bewerkingsnotitie
  </li>
  <li>
    Controleer alle informatie en druk tenslotte op &#8220;bewerking invoeren&#8221;. Dat was het!
  </li>
</ol><figure class="wp-block-image size-large">

<img decoding="async" loading="lazy" width="884" height="1024" src="https://marijnk.nl/wp-content/uploads/2022/05/Overzichtspagina-min-884x1024.png" alt="" class="wp-image-96" srcset="https://marijnk.nl/wp-content/uploads/2022/05/Overzichtspagina-min-884x1024.png 884w, https://marijnk.nl/wp-content/uploads/2022/05/Overzichtspagina-min-259x300.png 259w, https://marijnk.nl/wp-content/uploads/2022/05/Overzichtspagina-min-768x890.png 768w, https://marijnk.nl/wp-content/uploads/2022/05/Overzichtspagina-min.png 1280w" sizes="(max-width: 884px) 100vw, 884px" /> </figure> 

## Albumhoes toevoegen {.wp-block-heading}

  1. Ga naar release pagina en dan naar de cover art pagina
  2. Druk op &#8220;Import from Bandcamp&#8221;<figure class="wp-block-image size-large">

<img decoding="async" loading="lazy" width="1024" height="576" src="https://marijnk.nl/wp-content/uploads/2022/05/Cover-art-page-min-1024x576.png" alt="" class="wp-image-101" srcset="https://marijnk.nl/wp-content/uploads/2022/05/Cover-art-page-min-1024x576.png 1024w, https://marijnk.nl/wp-content/uploads/2022/05/Cover-art-page-min-300x169.png 300w, https://marijnk.nl/wp-content/uploads/2022/05/Cover-art-page-min-768x432.png 768w, https://marijnk.nl/wp-content/uploads/2022/05/Cover-art-page-min.png 1280w" sizes="(max-width: 1024px) 100vw, 1024px" /> </figure> 

<ol start="3">
  <li>
    Wacht tot de albumhoes geladen is en druk op &#8220;Bewerking invoeren&#8221;
  </li>
</ol>

## (Optioneel) AcoustID toevoegen {.wp-block-heading}

Door een [AcoustID][6] toe te voegen kunnen nummers herkend worden gebaseerd op hun geluid.

Instructies herleid van: [picard-docs.musicbrainz.org/en/usage/submit_acoustid.html][7]

  1. Open de MusicBrainz Picard applicatie
  2. Sleep je muziek naar de linkerkolom en druk op &#8220;opzoeken&#8221;
  3. Selecteer alle muziek in de rechterkolom en druk op AcoustID&#8217;s versturen

 [1]: https://addons.mozilla.org/nl/firefox/addon/violentmonkey/
 [2]: https://chrome.google.com/webstore/detail/violentmonkey/jinjaccalgkegednnccohejagnlnfdag
 [3]: https://raw.github.com/murdos/musicbrainz-userscripts/master/bandcamp_importer.user.js
 [4]: https://github.com/ROpdebee/mb-userscripts/raw/dist/mb_enhanced_cover_art_uploads.user.js
 [5]: https://myrone.bandcamp.com/track/track-day
 [6]: https://en.wikipedia.org/wiki/AcoustID
 [7]: https://picard-docs.musicbrainz.org/en/usage/submit_acoustid.html