[English](README.md) | [Suomi](README.fi.md)

*Käännös on tehty GPT-5.6:n avustuksella.*

# image-peek

Omaan käyttöön tarkoitettu VS Code -laajennus. Vie hiiri Base64-kuvadataa sisältävän rivin päälle, niin näet kuvan esikatselun tallentamatta sitä ensin tiedostoksi.

Tukee muotoa `data:image/...;base64,...`. Toimii kaikissa tiedostotyypeissä.

## Keskeiset tiedostot

| Tiedosto | Tehtävä |
| --- | --- |
| `src/extension.ts` | Laajennuksen aloituspiste: lukee hiiren alla olevan rivin, etsii kuvadatan ja näyttää esikatselun. |
| `sample.txt` | Esimerkkikuvadata esikatselun tarkistamiseen käsin. |
| `package.json` | Laajennuksen tiedot, riippuvuudet ja koontikomennot. |
| `.vscode/launch.json`, `.vscode/tasks.json` | Paikallisen virheenkorjauksen ja kehityksen aikaisen automaattisen koonnin asetukset. |
| `src/test/` | Laajennuksen testien käynnistys ja yksinkertaiset esimerkkitestit. |

## Toimintaperiaate

Hiiri tekstin päälle → Nykyisen rivin lukeminen → Base64-kuvadatan etsiminen → Kuvan esikatselu.

Pidä kunkin kuvan data omalla rivillään. Jos samalla rivillä on useita kuvia, esikatselu ei välttämättä toimi oikein.

## Paikallinen käyttö

Asenna Node.js, pnpm 7 ja VS Code.

```sh
git clone https://github.com/runjief/image-peek.git
cd image-peek
pnpm install --frozen-lockfile
pnpm run build
```

Avaa projekti VS Codessa ja käynnistä laajennuksen kehitysikkuna painamalla `F5`. Avaa siinä `sample.txt` ja vie hiiri kuvadataa sisältävän rivin päälle nähdäksesi esikatselun.

## Tarkistukset ja testit

```sh
pnpm run compile
pnpm run lint
pnpm test
```

`pnpm test` suorittaa kaksi ensimmäistä automaattisesti. Testikomento lataa ja käynnistää VS Coden testiympäristön. Nykyiset testit ovat yksinkertaisia esimerkkejä; kuvien esikatselu on tarkistettava käsin.
