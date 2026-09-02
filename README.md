# PIM Codering Tool — Plieger

Browser-based tool voor het verwerken van leverancier-PAB/ETIM-exports naar SAP CX
Backoffice Workflow deel 1 (productbeschrijvingen, salescodes, ETIM-classificaties,
navigatiecategorieën, intrastat) en Workflow deel 2 (logistiek: gewicht, afmetingen,
levertijd).

## Gebruik

Open `index.html` in de browser (of de gepubliceerde website-URL, zodra GitHub Pages
is ingesteld). Er is geen server nodig — alles draait lokaal in de browser.

## Hoe wijzigingen hier terechtkomen

Deze repository is de **enige bron van waarheid** voor de tool. Wijzigingen die in een
Claude-gesprek worden gemaakt, horen hier — via Claude Code — direct in gecommit te
worden, zodat:

- de website altijd de laatste versie toont (zodra GitHub Pages actief is)
- elke wijziging een leesbare commit-boodschap heeft (wat is er veranderd, en waarom)
- oude versies altijd terug te vinden zijn via de commit-geschiedenis

Geen losse HTML-downloads meer die per chatgesprek verloren kunnen gaan.

## Ondersteunde leveranciers (leverancier-specifieke logica)

- Grohe / AXOR (kleurcodes, ETIM-mapping, afkortingenwoordenboek, salescode D-groepen)
- Hansgrohe
- Bette (Antislip Sense / Minimum-douchebakdrager herkenning via artikelnummer)
- Detremmerie
- Wisa / Schwab (merk-alias naar leveranciersnummer)
- Duravit, Hansa, Direct Healthcare Group, Dornbracht, RAYBRO, ACO, Vent-Axia,
  Delabie, Conel/Trinnity

## Belangrijk: intern configuratiebestand

Sommige merk-specifieke logica (zoals Hansgrohe-salescode-koppelingen) gebruikt Plieger-interne
prijscategoriecodes. Om te voorkomen dat deze in de publieke broncode terechtkomen, staan deze
**niet** in dit bestand, maar in een apart bestand: `plieger-merk-config.json`.

**Dit bestand hoort nooit in deze (publieke) repository terecht te komen.** Upload het alleen
rechtstreeks in de tool zelf via de "Merk-config (optioneel)"-dropzone — het blijft dan in je eigen
browser en wordt nooit verzonden of opgeslagen op een server. Zonder dit bestand werkt de tool
gewoon door, alleen zonder de merk-specifieke salescode-fallback (het veld blijft dan leeg in
plaats van te gokken).

## Volgende stap: publiceren als website

Zie de instructies die apart zijn meegegeven voor het opzetten van GitHub Pages,
zodat deze repository ook als vast webadres bereikbaar wordt.
