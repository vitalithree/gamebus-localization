# gamebus-localization
This repository provides localization expansions for GameBus application.

Localizations consist of a base and expandable modules.

Base module contains strings for base app UI, for example: button captions etc.

Expandable modules provide localization strings for the growing collection of game descriptors and etc.

## Expandable modules
There are several modules that are expected to expand with time:
- GAMEDESCRIPTORS
- PROPERTIES
- MINIGAMES

Check corresponding folders for localization  files.

## Merge scheme
```mermaid
graph LR
    subgraph Compile-time at GameBus sources
        base(Base module) --> result-c((Compile-time translations))
        properties-c(PROPERTIES module) --> result-c
        descriptors-c(GAMEDESCRIPTORS module) --> result-c
        minigames-c(MINIGAMES module) --> result-c
    end

    subgraph Expandable modules at GitHub
        properties-e(PROPERTIES module)
        descriptors-e(GAMEDESCRIPTORS module)
        minigames-e(MINIGAMES module)
    end
    
    result-c --> result-f((Combined result at runtime))
    properties-e --> result-f
    descriptors-e --> result-f
    minigames-e --> result-f
    

     classDef orange fill:#f96
     classDef green fill:#9f6
     classDef purple fill:#96f
     classDef pink fill:#f69
     classDef bold stroke-width:4px
     class base orange
     class properties-c,properties-e green
     class descriptors-c,descriptors-e purple
     class minigames-c,minigames-e pink
     class result-f bold
```


## Published with GitHub Pages
The files are served by GitHub CDN at https://vitalithree.github.io/gamebus-localization

For example:
- https://vitalithree.github.io/gamebus-localization/GAMEDESCRIPTORS/en.json
- https://vitalithree.github.io/gamebus-localization/PROPERTIES/en.json
- https://vitalithree.github.io/gamebus-localization/MINIGAMES/en.json

> More info about GitHub Pages: https://pages.github.com/

## How do i add translations for my MiniGame at GameBus?
Open a pull request to the `main` branch of this repository.

GameBus team will review it asap.

> More info about pull requests https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork

