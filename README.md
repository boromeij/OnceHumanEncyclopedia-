# Once Human Helper

Nederlandse itemencyclopedie met Engelse itemnamen, zoeken, categoriefilters, recepten en lokale favorieten. De eerste catalogus bevat acht items en is nog niet compleet.

## Publiceren op GitHub Pages

1. Open **Settings → Pages** in deze repository.
2. Kies **Deploy from a branch**, branch **main**, map **/(root)**.
3. GitHub bouwt de website met Jekyll zodra wijzigingen op `main` staan.
4. Bekijk de site op https://boromeij.github.io/OnceHumanHelper/.

`_config.yml` stelt `baseurl: "/OnceHumanHelper"` in. Bij een andere repositorynaam of een eigen domein moet je `url` en `baseurl` aanpassen. De layout gebruikt `relative_url` voor scripts, CSS en het databestand.

## Items beheren

De enige bron voor de gepubliceerde catalogus is **`_data/items.json`**. Bewerk deze lijst om items toe te voegen of informatie te corrigeren. Het bestand `items.json` in de hoofdmap is een Jekyll-template die deze lijst als JSON publiceert; vervang deze template niet door de catalogus.

Via **Beheer** kun je lokaal items toevoegen of JSON importeren. Download vervolgens de catalogus en vervang `_data/items.json` in GitHub. De wijzigingen komen online nadat ze op `main` zijn opgeslagen en de Pages-build slaagt.

Lokale wijzigingen en favorieten zijn alleen zichtbaar in de betreffende browser. Om nieuwe gepubliceerde gegevens te zien wanneer je een lokale catalogus gebruikt, kies **Beheer → Lokale catalogus herstellen**. Er is geen account, synchronisatie of serverdatabase.

Een item bevat `id`, `name`, `nl`, `category`, `description`, `obtain` en `source`. De id moet uniek en stabiel zijn. Optionele velden zijn `recipe`, `station`, `note`, `checked` en `status`. Een recept bevat ingrediënten met een item-id en een positief aantal, bijvoorbeeld:

```json
"recipe": [{ "id": "copper-ore", "amount": 3 }]
```

## Structuur

| Bestand | Functie |
| --- | --- |
| `_config.yml` | Jekyll-instellingen en websiteadres |
| `_layouts/default.html` | HTML-layout en paden naar bestanden |
| `index.html` | Catalogus en dialoogvensters |
| `_data/items.json` | Bewerkbare itemgegevens |
| `items.json` | Gegenereerde JSON-uitvoer voor de zoekfunctie |
| `app.js` | Zoeken, filters, favorieten en lokaal beheer |
| `style.css` | Vormgeving |

## Lokaal draaien

Installeer Ruby en Bundler. Voer in de projectmap uit:

```sh
bundle install
bundle exec jekyll serve
```

Open http://localhost:4000/OnceHumanHelper/. Voor een build: `bundle exec jekyll build`.

Een gewone bestandsserver is onvoldoende voor de Jekyll-bronbestanden: de Liquid-templates moeten eerst gebouwd worden.

## Inhoud

Controleer de gegevens in-game voor jouw scenario. Receptvarianten, volledige stats en gedetailleerde locaties zijn nog niet volledig opgenomen. Elk item verwijst naar een bron. Illustraties zijn generieke symbolen, geen game-assets. Onafhankelijk fanproject, niet verbonden aan Starry Studio of NetEase.
