# 📖 Slabikátor (SK/CZ)

> 🚀 **Živá ukážka aplikácie:** [https://urgothegreat.github.io/slabikator/](https://urgothegreat.github.io/slabikator/)

Slabikátor je jednoduchá, responzívna a rýchla webová aplikácia navrhnutá na automatické počítanie a analýzu počtu slabík v slovenskom a českom texte. Je optimalizovaná pre počítače aj mobilné zariadenia a dokáže rozpoznať špecifické jazykové nuansy, ktoré ovplyvňujú slabičnú štruktúru slov.

Aplikácia funguje ako čisté klientske riešenie (single HTML file) – všetka logika beží priamo vo vašom prehliadači prostredníctvom JavaScriptu bez potreby odosielania dát na server.

## ✨ Kľúčové funkcie

- **Podpora dvoch jazykov:** Prepínanie medzi slovenskou a českou verziou mení pravidlá analýzy.
- **Detekcia slabikotvorných spoluhlások:** Inteligentne rozpoznáva, kedy spoluhlásky `r, ŕ, l, l` (SK) alebo `r, l` (CZ) plnia funkciu jadra slabiky (napr. vo slovách ako *vlk*, *smrť*, *krk*).
- **Alternatívne počítanie (Dvojhlásky / Diftongy):**
  - V **slovenčine** analyzuje kombinácie `ia, ie, iu` (či sa čítajú ako jedna slabika s dvojhláskou alebo dve samostatné slabiky podľa kontextu).
  - V **češtine** zohľadňuje dvojhlásky `ou, au, eu` (napr. rozdiel pri slove *auto*).
- **Zvýraznenie nejednoznačnosti:** Ak riadok obsahuje slová, kde sa môže počet slabík líšiť (alternatívne interpretácie), riadok sa vizuálne zvýrazní žltou farbou a aplikácia zobrazí základný počet aj alternatívny počet slabík (napr. `3 (alt:4)`).
- **Responzívny tmavý režim (Dark Mode):** Moderné rozhranie šetrné k očiam, ktoré sa prispôsobí veľkosti obrazovky od smartfónov až po veľké monitory.
- **Synchronizované scrollovanie:** Bočný panel s počtom slabík sa posúva presne s textovým poľom, takže máte okamžitý prehľad o každom riadku.

## 🛠️ Ako funguje algoritmus pod kapotou?

Aplikácia rozdeľuje text na riadky a analyzuje každé slovo pomocou regulárnych výrazov (Regex):
1. **Samohlásky:** Každá bežná samohláska tvorí základ jadra slabiky.
2. **Slabikotvorné spoluhlásky:** Ak slovo neobsahuje žiadnu samohlásku, alebo ak sa `r/l` nachádza v špecifickom vzore medzi inými spoluhláskami (napr. `(?<=[spoluhláska])([rl])(?=[spoluhláska]|$)`), započíta sa ako slabika.
3. **Sporné dvojhlásky:** Aplikácia identifikuje sekvencie ako `ia/ie/iu` (SK) alebo `ou/au/eu` (CZ). Keďže ich interpretácia môže byť rôzna (jedna slabika ako diftong, alebo dve slabiky pri cudzích slovách či predponách), algoritmus vypočíta obe verzie a upozorní používateľa na alternatívu.

## 🚀 Ako aplikáciu spustiť?

Keďže je celý projekt zabalený do jediného hlavného HTML súboru, spustenie je mimoriadne jednoduché:

### Lokálne na počítači
1. Stiahnite si alebo skopírujte súbor `index.html` do svojho počítača.
2. Dvakrát naň kliknite – súbor sa okamžite otvorí v akomkoľvek modernom webovom prehliadači.

### Cez GitHub Pages (Zadarmo webová stránka)
Aplikácia je už plne nakonfigurovaná pre GitHub Pages. Priamo z hlavnej adresy repozitára sa spúšťa vďaka pomenovaniu hlavného súboru ako `index.html`.

## 📁 Štruktúra projektu

Projekt pozostáva z týchto súborov:
- `index.html` - *(Pôvodne slabiky.html)* Obsahuje kompletnú štruktúru (HTML5), štýlovanie (CSS3 v tmavom režime) a aplikačnú logiku (Vanilla JavaScript). Premenovaním na `index.html` sa zabezpečilo správne automatické načítanie aplikácie cez GitHub Pages.
- `README.md` - Dokumentácia k projektu.

## 📝 Licencia

Tento projekt je voľne dostupný. Môžete ho upravovať, šíriť a prispôsobovať pre vlastné vzdelávacie alebo osobné účely.
