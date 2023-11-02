---
title: Wat te doen nadat je Visual Studio Code hebt geïnstalleerd
authors:
  - marijn-kok
date: 2023-11-02T23:15:07+01:00
featuredImage: ''
tags:
  - setup
  - tutorial
draft: true
---
Visual Studio Code, afgekort VS Code, is een code-editor van Microsoft. Het is een populaire keuze en heeft veel goede standaardinstellingen, maar een aantal dingen pas ik ook altijd graag aan. Dit doe ik door middel van aanpassingen aan het instellingenbestand en door het installeren van uitbreidingen.

## Uitbreidingen

De volgende uitbreidingen vind ik erg handig:

- [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame) van Wade Anderson. Deze uitbreiding voegt een klein stukje tekst onderaan de IDE toe die laat zien wanneer de regel waar je cursor is voor het laatst gewijzigd is met git. Handig als je afvraagt wie in godsnaam die regel code geschreven heeft! (In mijn geval: meestal mezelf)

- [Git History](https://marketplace.visualstudio.com/items?itemName=GuodongSun.vscode-git-cruise) van Guodong Sun. Met deze uitbreiding krijg je een mooi visueel overzicht van alle commits en branches in je git repository. Als je een commit selecteert kan je ook zien welke bestanden gewijzigd zijn. Handig om te zien wat de context was bij dat vreselijke stuk code wat je gevonden had met git blame.

Verder gebruik ik extensies voor ondersteuning van programmeertalen, maar die zal ik hier niet noemen.

## Instellingen

Ik gebruik de JSON die in het uitklapmenu hieronder staan als basis voor mijn instellingen. Let op dat ik deze instellingen in combinatie met Fedora gebruik (zie mijn artikel {{% reflink "wat-te-doen-nadat-je-fedora-hebt-geïnstalleerd" %}}); op Windows of macOS zou bijvoorbeeld `"update.mode": "none"` onlogisch zijn.

Je kan de instellingen als volgt toepassen: open het command palette (<kbd>ctrl+shift+P</kbd>), typ "user json" en kies "Preferences: Open User Settings (JSON)". Vervang vervolgens je configuratie met die van hieronder, of pas het aan naar wens.

<details>
<summary>Mijn instellingen (<code>settings.json</code>)</summary>

```json
{
    // Theme
    "window.autoDetectColorScheme": true,
    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,

    // VSCode
    "update.mode": "none",
    "workbench.startupEditor": "none",
    "breadcrumbs.enabled": false,
    "editor.inlineSuggest.enabled": true,
    "editor.minimap.enabled": false,
    "terminal.integrated.enablePersistentSessions": false,
    "window.zoomLevel": 1,
    "explorer.confirmDelete": false,

    // Git
    "git.confirmSync": false,
    "git.enableSmartCommit": true,

    // Files
    "files.eol": "\n",
    "files.insertFinalNewline": true,
    "files.trimTrailingWhitespace": true,
    "files.autoSave": "afterDelay",

    // == Languages ==
    // Go
    "go.survey.prompt": false,
    "go.toolsManagement.checkForUpdates": "local",

    // Dart
    "[dart]": {
        "editor.formatOnSave": true,
        "editor.formatOnType": true,
        "editor.rulers": [
            80
        ],
        "editor.selectionHighlight": false,
        "editor.suggestSelection": "first",
        "editor.tabCompletion": "onlySnippets",
        "editor.wordBasedSuggestions": false
    },
}
```
</details>


## Gebruikersinterface

Ik maak de volgende aanpassingen aan de gebruikersinterface:

- Schakel de badge uit van het kopje Run and Debug (<kbd>ctrl+shift+D</kbd>) door rechts te klikken en "Show badge" uit te schakelen.

- Verplaats het git tabje helemaal naar links in het onderste paneel, en verberg optioneel het ports tabje.

