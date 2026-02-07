<p align="center">
  <img src="./assets/img/logo.png" alt="Delavnice semantičnega opisovanja podatkov" width="200px" />
</p>

# Delavnice semantičnega opisovanja podatkov

## Osnovni podatki

<details>
<summary>Prikaži podrobnosti</summary>

### Termini

**9. februar 2026** in **12. februar 2026** od 9:00 do 13:00 po MS Teams.

### Ciljna skupina

Zaposleni v javnem sektorju, ki želijo napredovati na področju semantičnega opisovanja podatkov in izboljšati interoperabilnost svojih podatkovnih zbirk.

### Cilji delavnice

- Omogočiti osnovno razumevanje semantične interoperabilnosti in pomena odprtih podatkov.
- Usposobiti udeležence za pretvorbo podatkov v odprte in semantično opisane formate (CSV, RDF/TTL).
- Okrepiti razumevanje uporabe URI-jev, trojčkov RDF in ontologij ter uporabo osnovnih orodij (npr. [Protégé](https://protege.stanford.edu/)).
- Spodbuditi uporabo povezanih podatkov in integracijo podatkov iz različnih virov (npr. SURS, CRP, OSM, Wikidata ipd.).
- Omogočiti izvajanje osnovnih poizvedb SPARQL ter razumevanje, kako sklepanje prinaša dodatno znanje.

### Zahteve

#### Predznanje

- Osnovno znanje o podatkovnih bazah.
- Poznavanje formatov CSV, JSON in načinov zapisovanja podatkov z omenjenima formatoma.

#### Programska oprema

- Lokalno nameščeno orodje [Protégé](https://protege.stanford.edu/) ali dostop do [WebProtégé](https://webprotege.stanford.edu/).
- Lokalno nameščeno orodje za delo z besedilnimi datotekami (npr. [VS Code](https://code.visualstudio.com/), [Notepad++](https://notepad-plus-plus.org/), [Sublime Text](https://www.sublimetext.com/) ipd.).
- Lokalno nameščena podpora za [Docker](https://docs.docker.com/desktop/) za izvajanje SPARQL poizvedb in sklepanje.

### Izvajalca

**dr. Slavko Žitnik** in **dr. Dejan Lavbič**

### Financiranje

Naročilo sofinancirata Republika Slovenija in Evropska unija iz Načrta za okrevanje in odpornost (NOO), komponenta Digitalne preobrazbe javnega sektorja in javne uprave (C2K7), ukrep Razvoj novih dinamičnih e-storitev.

</details>

## Vsebina

### 1. Uvod: Zakaj semantično opisovanje podatkov?

<p align="left">
  <img src="./assets/img/logo_1.png" alt="1. poglavje" width="200px" />
</p>

<details>
<summary>Prikaži podrobnosti</summary>

#### 1.1 Namen delavnice

V okviru delavnice želimo **praktično pojasniti**:

- zakaj klasično objavljanje podatkov ni dovolj,
- kako doseči višje ravni odprtosti podatkov,
- kakšen problem semantično opisovanje dejansko rešuje,
- zakaj je to še posebej pomembno za javni sektor.

Poudarek ni na tehnologiji, temveč na **problemu in dodani vrednosti**, ki jo semantično opisovanje prinaša.

#### 1.2 Motivacijski problem

Realni problem, s katerim se srečamo, je situacija, kjer podatki obstajajo, vendar iz njih težko pridobimo željene odgovore.

Primer takšnega realnega vprašanja je:

> _"Katere občine imajo največ prebivalcev, katere šole imajo tam sedež in kakšna je nadmorska višina teh območij?"_

Podatki sicer že obstajajo, vendar:

- so **razpršeni** po različnih institucijah (CRP, SURS, MIZŠ, OSM, Wikidata),
- uporabljajo **različne identifikatorje**, **poimenovanja** in **strukture**,
- **niso** neposredno medsebojno **povezljivi**.

Z eno datoteko Excel ali CSV **tega vprašanja ne moremo rešiti**. Zato potrebujemo nek način, kjer podatki "govorijo isti jezik", se lahko povezujejo in so računalniku razumljivi. V tem kontekstu je **semantično opisovanje podatkov ključnega pomena**.

#### Od podatkov do znanja

Pogosto strukturirane podatke napačno interpretiramo kot semantično bogate podatke. To ne drži, saj moramo jasno razlikovati, da **struktura ne predstavlja pomena**.

| Pojem           | Primer                                                                                                                                                    |
| :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **podatek**     | `298000`                                                                                                                                                  |
| **informacija** | Število prebivalcev Ljubljane.                                                                                                                            |
| **metapodatek** | Kaj ta številka pomeni, za katero leto, vir, metodologija.                                                                                                |
| **znanje**      | Sklepanje, povezovanje, odgovori na kompleksna vprašanja, npr. Ljubljana je največje mesto v Sloveniji z 298.000 prebivalci (podatki iz leta 2023, SURS). |

Zgornji primer jasno pokaže da lepo strukturirana datoteka CSV ne pove, kaj stolpci dejansko pomenijo. Struktura ≠ semantika. Brez opredeljenega pomena računalnik podatkov ne razume in jih ne more povezovati.

#### 1.3 Zakaj je to pomembno za javni sektor?

Javni sektor upravlja z **veliko količino podatkov**, ki se pogosto zbirajo večkrat, niso ponovno uporabni, niso pripravljeni za povezovanje.

Semantična interoperabilnost pri tem prinaša številne koristi, in sicer zmanjšuje podvajanje, omogoča ponovno uporabo podatkov in podpira podatkovno podprto odločanje.

Omenjen pristop je tesno povezan s strategijami in načeli, predstavljenimi v dokumentu **Podatkovnih semantičnih smernic** - cilji digitalne preobrazbe, pomenom interoperabilnosti, načeli FAIR (**F**indable, **A**ccessible, **I**nteroperable, **R**eusable) in odprtih podatkov.

#### 1.4 Kaj semantično opisovanje ni?

O semantičnem opisovanju podatkov pogosto obstajajo napačne predstave. Tukaj je nekaj **pogostih zmot**:

- ❌ _"To je samo za raziskovalce."_
- ❌ _"To pomeni, da moramo najprej narediti ontologijo."_
- ❌ _"To je preveč kompleksno za praktično uporabo."_

Ključno vodilo delavnice je:

> _Ne gradimo ontologije - rešujemo problem povezovanja podatkov za namen odgovarjanja na kompleksna vprašanja._

#### 1.5 Intuitivne razlage ključnih pojmov

Pri delavnici bomo uporabljali preproste in intuitivne razlage ključnih pojmov, kot so:

| Pojem                                    | Razlaga                                                                                                                                                                                                                                    |
| :--------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URI (Uniform Resource Identifier)**    | Enoličen in nespremenljiv naslov (ne le ID v tabeli), ki identificira vir (npr. občino, šolo) na spletu.                                                                                                                                   |
| **RDF (Resource Description Framework)** | Način, kako računalniku predstavimo "kdo je kdo, kako so stvari povezane" z uporabo trojčkov (subjekt, predikat, objekt).                                                                                                                  |
| **Ontologija**                           | Formalen opis pojmov in njihovih medsebojnih odnosov v določenem področju (npr. občine, šole).                                                                                                                                             |
| **SPARQL**                               | Jezik za poizvedovanje po semantično opisanih podatkih. Npr. Google (v kontekstu spletnih strani) oz. SQL (v kontekstu relacijskih baz) za grafovsko urejene podatke.                                                                      |
| **Povezani podatki (Linked Data)**       | Podatki, ki so medsebojno povezani z uporabo URI-jev, kar omogoča integracijo in kontekstualizacijo iz različnih virov. Način, s katerim lahko samodejno pridobimo podatke iz zunanjih virov (npr. [Wikidata](https://www.wikidata.org/)). |

#### 1.6 Praktični primer

Če pogledamo poljuben članek na spletni strani [RTV Slovenije](https://www.rtvslo.si/), npr. [Zadnji dan za odpiranje transakcijskih računov za predvolilne kampanje](https://www.rtvslo.si/slovenija/zadnji-dan-za-odpiranje-transakcijskih-racunov-za-predvolilne-kampanje/772271), lahko opazimo, da je delno semantično opisan z namenom olajšanja iskanja in povezovanja vsebin, kot to prikazuje naslednja slika.

<p align="center">
  <img src="./assets/img/RTVSLO_clanek.jpg" alt="RTV SLO članek: Zadnji dan za odpiranje transkacijskih računov za predvolilne kampanje" width="500px" /><br>
  Vizualizacija novice iz <a href="https://www.rtvslo.si/slovenija/zadnji-dan-za-odpiranje-transakcijskih-racunov-za-predvolilne-kampanje/772271" target="_blank">RTV SLO</a>
</p>

Izvorna koda novice iz [RTV SLO](https://www.rtvslo.si/slovenija/zadnji-dan-za-odpiranje-transakcijskih-racunov-za-predvolilne-kampanje/772271) vsebuje naslednji del z uporabo [JSON-LD](https://json-ld.org/) za semantično opisovanje vsebine novice:

```html
<!DOCTYPE html>
<html lang="sl">
  <head>
    ...
    <script type="application/ld+json">
      {
        "@context": "https://schema.org",
        "@type": "NewsArticle",
        "mainEntityOfPage": {
          "@type": "WebPage",
          "@id": "https://www.rtvslo.si/slovenija/zadnji-dan-za-odpiranje-transakcijskih-racunov-za-predvolilne-kampanje/772271"
        },
        "headline": "Zadnji dan za odpiranje transakcijskih računov za predvolilne kampanje",
        "image": [
          "https://img.rtvcdn.si/_up/upload/2025/11/23/66997310_fp-fb.jpg"
        ],
        "datePublished": "2026-02-04 07:25:17",
        "dateModified": "2026-02-04 07:33:56",
        "author": {
          "@type": "Person",
          "name": "G. K.",
          "url": "https://www.rtvslo.si"
        },
        "publisher": {
          "@type": "Organization",
          "name": "RTV Slovenija",
          "logo": {
            "@type": "ImageObject",
            "url": "https://img.rtvslo.si/_static/novi/logo/md_RTVSLO-logo-color.png"
          }
        }
      }
    </script>
  </head>
  <body>
    ...
  </body>
</html>
```

Opazimo lahko, da je novica semantično opisana z uporabo standarda [schema.org](https://schema.org/), ki omogoča enostavno razumevanje vsebine tako ljudem kot računalnikom, kar se pogosto uporablja pri objavi splošnih podatkov na svetovnem spletu.

V tem konkretnem primeru so uporabljeni pojmi, kot so [`NewsArticle`](https://schema.org/NewsArticle) (novica), [`headline`](https://schema.org/headline) (naslov), [`image`](https://schema.org/image) (slika), [`datePublished`](https://schema.org/datePublished) (datum objave), [`author`](https://schema.org/author) (avtor) in [`publisher`](https://schema.org/publisher) (izdajatelj). Ti pojmi omogočajo strukturirano predstavitev ključnih informacij o novici, kar olajša iskanje, indeksiranje in povezovanje z drugimi vsebinami na spletu.

Poznamo pa še številne druge formalne opredelitve v obliki besednjakov in ontologij, kot so npr. [**F**riend **O**f **A** **F**riend (**FOAF**)](http://xmlns.com/foaf/spec/), [**D**ublin **C**ore (**DC**)](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/), [**S**imple **K**nowledge **O**rganization **S**ystem (**SKOS**)](https://www.w3.org/TR/skos-reference/), in seveda [**D**ata **CAT**alog Vocabulary (**DCAT**)](http://www.w3.org/ns/dcat#), ki se uporablja predvsem na področju podatkovnih naborov podatkov.

</details>

### 2. Od izvornih podatkov (1 ★) do odprtih podatkov (3 ★)

<p align="left">
  <img src="./assets/img/logo_2.png" alt="2. poglavje" width="200px" />
</p>

<details>
<summary>Prikaži podrobnosti</summary>

#### 2.1 Ravni odprtosti podatkov

Cilj delavnice je pojasniti, kako iz razdrobljenih javnih podatkov dobimo odgovore, ki jih iz posamezne zbirke ne moremo pridobiti. Pri tem pogosto govorimo o [ravneh odprtosti podatkov](https://5stardata.info/), predstavljene v naslednji tabeli.

| Raven | Opis                                                                                   | Primer                                                                                    |
| :---- | :------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------- |
| ★     | Podatki so objavljeni na spletu (v poljubnem formatu) pod odprto licenco.              | Poročilo v obliki PDF o občinskih proračunih na spletni strani občine.                    |
| ★★    | Podatki so strukturirani (npr. Excel namesto skeniranega dokumenta).                   | Excel tabela z javnimi naročili.                                                          |
| ★★★   | Podatki so v odprtem formatu (npr. CSV namesto Excel).                                 | Datoteka CSV s statistiko prebivalstva iz SURS-a.                                         |
| ★★★★  | Podatki uporabljajo URI-je za enolično identifikacijo pojmov, kar omogoča povezovanje. | Nabor podatkov o občinah, kjer ima vsaka občina svoj URI.                                 |
| ★★★★★ | Podatki so povezani z drugimi viri, kar omogoča kontekstualizacijo.                    | Podatki o šolah, povezani z prostorskimi podatki, standardi izobraževanja in demografijo. |

Model 5 ★ odprtosti podatkov nam pomaga razumeti, **zakaj zgolj objava podatkov še ne pomeni, da so ti uporabni**. Vsaka zvezdica predstavlja **konkreten kvalitativni preskok**, kjer vsaka naslednja zvezdica predpostavlja izpolnitev pogojev prejšnje. Največja dodana vrednost pa se pojavi pri 4 ★ in 5 ★, kjer podatki postanejo medsebojno povezljivi in kontekstualizirani. Na žalost večina podatkov dandanes obstaja na ravni 2 ★ ali 3 ★, kar močno omejuje njihovo uporabnost.

#### 2.2 Izvorni podatki (1 ★ in 2 ★): ko podatki obstajajo, a niso uporabni

Za začetek si poglejmo podatke o Centralnem registru prebivalstva (**CRP**) iz [NIO](https://nio.gov.si/sl/products/nio%2Bcentralni%2Bregister%2Bprebivalstva%2Bcrp%2Bvpogled%2Bpreko%2Bemso?release=0.1), ki so na voljo v naslednjih Excel datotekah:

> [📊 `Nabor podatkov NIO CRP.xls`](./assets/data/raw/CRP/Nabor%20podatkov%20NIO%20CRP.xls)  
> [📊 `Sifranti IO CRP.xls`](./assets/data/raw/CRP/Sifranti%20IO%20CRP.xls)

📊 `Sifrant IO CRP.xls` v zavihku `Občine` vsebuje šifrant občin z naslednjimi podatki:

| OBC_ID | OBC_IME_SLO_MLC |
| ------ | --------------- |
| 1      | Ajdovščina      |
| 2      | Beltinci        |
| 3      | Bled            |
| 4      | Bohinj          |
| 5      | Borovnica       |
| 6      | Bovec           |
| 7      | Brda            |
| 8      | Brezovica       |
| 9      | Brežice         |
| 10     | Tišina          |
| ...    | ...             |

Po pregledu podatkov opazimo:

- podatki so **razpršeni po več datotekah in zavihkih**,
- pomen stolpcev **ni jasno razložen** (npr. kaj pomeni `4` v stolpcu `OBC_ID` in v katerem registru je enolična oznaka; ali je ta oznaka nespremenljiva in uporabna tudi izven Excel datoteke?),
- podatki so predstavljeni **brez konteksta**,
- iste vrednosti se lahko nanašajo na **različne koncepte** (npr. `Ljubljana` kot občina, naselje, upravna enota), ker ni eksplicitne definicije pojma.

Gre za tipičen primer, kjer so podatki objavljeni (1 ★) in strukturirani (2 ★), vendar brez jasnega pomena in konteksta, kar onemogoča njihovo učinkovito uporabo in zato **niso interoperabilni**.

> Excel datoteka je primerna za uporabniško branje, ne pa za povezovanje podatkov.

#### 2.3 Prehod v odprti format (3 ★): CSV kot prvi korak k tehnični interoperabilnosti

Naslednji korak je pretvorba podatkov v **odprt** in **strojno berljiv format**, kot je CSV. To omogoča lažjo obdelavo in izmenjavo podatkov med različnimi sistemi.

Format CSV je preprost besedilni format, kjer so podatki organizirani v vrstice in stolpce, ločene z vejicami ali drugimi ločili (npr. `;`). Vsaka vrstica predstavlja en zapis, prvi vrstici pa običajno vsebujejo imena stolpcev. Je odprt standard, neodvisen od orodij, primeren za avtomatsko obdelavo in podprt praktično v vseh okoljih.

V nadaljevanju bomo podatke iz Excela izvozili v podatke CSV, odstranili nepotrebne zavihke, poenotili kodiranje (UTF-8) in zagotovili konsistentna imena stolpcev.

```csv
OBC_ID;OBC_IME_SLO_MLC;OBC_DTM_UKN
1;Ajdovščina;
2;Beltinci;
3;Bled;
4;Bohinj;
5;Borovnica;
6;Bovec;
7;Brda;
8;Brezovica;
9;Brežice;
10;Tišina;
...
```

S tem postopkom zapisa v obliki CSV smo **izboljšali dostopnost**, **ne** pa še **pomena**.

> **Struktura ≠ semantika.** Brez opredeljenega pomena računalnik podatkov ne razume in jih ne more povezovati.

#### 2.4 Primer zunanjega vira: podatki SURS (3 ★)

Nadaljujemo s podatki Statističnega urada Republike Slovenije (**SURS**), ki so na voljo na [portalu odprtih podatkov SURS](https://www.stat.si/obcine/sl/Theme/Index/PrebivalstvoStevilo), med tematskimi članki o prebivalstvu. Če želimo pridobiti podatke o številu prebivalcev po občinah za leto 2025 lahko s klikom na [zemljevid](https://gis.stat.si/#) zahtevamo podrobnjši pregled, kjer vnesemo omejitve za leto 2025 in zahtevamo prenos. Ker potrebujemo zgolj podatke o številu prebivalcev, zahtevamo **Prenesi CSV tabelo**, kjer dobimo naslednjo vsebino:

- Datoteka ZIP 📦 `STAGE_data.zip` z naslednjimi datotekami:
  - [📊 `data.tsv`](./assets/data/raw/SURS/2025/data.tsv),
  - [📄 `info.html`](./assets/data/raw/SURS/2025/info.html),
  - [📝 `info.txt`](./assets/data/raw/SURS/2025/info.txt).

`data.tsv`

```tsv
ob_id ob_ime              tot_p
001   Ajdovščina          19895
213   Ankaran             3446
195   Apače               3563
002   Beltinci            8129
148   Benedikt            2738
149   "Bistrica ob Sotli" 1335
003   Bled                8154
150   Bloke               1554
004   Bohinj              5238
```

Datoteka `info.txt` sama po sebi vsebuje zgolj **vrednosti** in **kratice stolpcev**, katerih pomen iz same strukture ni razviden. Brez dodatnega konteksta računalnik (in pogosto tudi človek) ne ve, kaj posamezen stolpec predstavlja.

Vlogo tega konteksta v primeru podatkov SURS predstavlja datoteka `info.txt` z **zunanjim opisom podatkovnega modela**. V njej so za vsak stolpec navedeni polni nazivi pojmov v slovenskem in angleškem jeziku ter hierarhična umestitev kazalnika.

`info.txt`

```txt
ACRONYM        English                                           Slovenian
-------------------------------------------------------------------------------------------------------------------
tot_p          Population > number of population > total         Prebivalstvo > število prebivalcev > skupaj
```

Ta primer lepo ponazarja ključno lastnosti ravni 3 ★, kjer so podatki odprti in strojno berljivi, medtem ko **pomen** podatkov **ni del podatkov samih**, ampak je **zapisan ločeno** v spremljajoči dokumentaciji.

Za računalniško obdelavo pomeni, da je treba `info.txt` interpretirati ročno ali z dodatno logiko, saj ni enolične, formalne povezave med stolpci in pomenom. Podatki še vedno niso neposredno primerni za avtomatsko povezovanje z drugimi viri.

#### 2.5 Omejitve ravni 3 ★

Na tej točki smo zdaj posamezne podatke (CRP in SURS) pretvorili v odprt format (CSV). Kako zdaj ta nabora podatkov medsebojno povežemo?

Pojavijo se namreč naslednje težave:

- ni skupnega identifikatorja (npr. `OBC_ID` v CRP ni popolnoma enak `ob_id` v SURS),
- imena se razlikujejo (npr. `OBC_IME_SLO_MLC` v CRP in `ob_ime` v SURS),
- ni jasne definicije pojma (občina, pošta, upravna enota, naselje),
- računalnik pri samodejni obdelavi ne razume, da `Ajdovščina` v CRP in `Ajdovščina` v SURS predstavljata isto občino.

Npr. `Ajdovščina` ima v CRP `OBC_ID=1`, v SURS pa `ob_id=001`. Človeški uporabnik to zlahka ugane, računalnik pa brez dodatnih informacij (npr. pravil oz. semantike) ne more vedeti, da gre za isti entiteti.

> Pri 3 ★ smo s formatom CSV dosegli strojno berljivost in odprt format, vendar podatki še vedno **nimajo enoličnih identifikatorjev** in **formalno opredeljenega pomena**. Zato v naslednjem poglavju uvedemo **URI-je** in **RDF**, da omogočimo povezovanje in semantično interoperabilnost.

</details>

### 3. Raven 4 ★: semantični opis podatkov z RDF

<p align="left">
  <img src="./assets/img/logo_3.png" alt="3. poglavje" width="200px" />
</p>

<details>
<summary>Prikaži podrobnosti</summary>

#### 3.1 Zakaj CSV ni več dovolj?

V tem koraku naredimo **ključni preskok** od zgolj odprtih in strojno berljivih podatkov (3 ★) k **semantično opisanim podatkom** (4 ★). RDF, ki ga bomo uporabili, podatkom ne doda nove vsebine, temveč jasen in strojno razumljiv pomen.

Kot primer lahko izpostavimo `Ajdovščina` v CRP in `Ajdovščina` v SURS, ki za človeškega uporabnika pomenita isto občino, za računalnik pa gre zgolj za **enak niz znakov**, brez pomena.

Če želimo rešiti ta problem, moramo vpeljati:

- **enolične identifikatorje** (URI-je), ki bodo jasno določili, da gre za isto entiteto,
- **formalni opis pomena** (to kasneje zajamemo z ontologijo), ki bo opredelila, kaj je občina, kakšne so njene lastnosti in kako se povezuje z drugimi pojmi,
- **model, ki presega tabelarično strukturo** in omogoča predstavitev kompleksnih odnosov med pojmi (RDF).

#### 3.2 RDF: opis podatkov v obliki trojčkov

[**RDF** (Resource Description Framework)](https://www.w3.org/RDF/) je standard za predstavitev podatkov v obliki **trojčkov**:

- **osebek** _(angl. subject)_ - kaj opisujemo (npr. `Občina Ajdovščina`),
- **povedek** _(angl. predicate)_ - katero lastnost opisujemo (npr. `ima število prebivalcev`),
- **predmet** _(angl. object)_ - vrednost ali povezava (npr. `19895`).

Takšna struktura omogoča eksplicitno izražati pomen, povezovanje podatkov v graf in razširljivost brez spremembe obstoječih zapisov.

#### 3.3 URI: enolična identifikacija pojmov

Osnova jezika RDF je uporaba URI-jev, ki predstavljajo stabilne, globalno enolične in spletno naslovljive identifikatorje.

Namesto npr. `OBC_ID=1` uporabimo npr. `https://onto.mdp.gov.si/obcina/ajdovscina`, ki jasno identificira občino Ajdovščina. S tem odpravimo dvoumnost, omogočimo povezovanje z drugimi viri in jasno ločimo pojem od njegovega zapisa v tabeli.

> **URI ni le identifikator** - je nosilec pomena, ki omogoča povezovanje in integracijo podatkov iz različnih virov.

#### 3.4 Zapis RDF v obliki Turtle (TTL)

RDF podatke lahko zapišemo v različnih formatih, eden izmed najbolj berljivih je **Turtle (TTL)**, ker je človeško berljiv in pogosto uporabljen v praksi.

Osredotočimo se na podatke v obliki TSV, ki smo jih izvozili iz SURS-a:

`data.tsv`

```tsv
ob_id ob_ime              tot_p
001   Ajdovščina          19895
213   Ankaran             3446
195   Apače               3563
002   Beltinci            8129
148   Benedikt            2738
149   "Bistrica ob Sotli" 1335
003   Bled                8154
150   Bloke               1554
004   Bohinj              5238
```

V TSV datoteki so stolpci ločeni s tabulatorji (ne s presledki). Vsaka vrstica predstavlja eno občino, stolpci pa njene lastnosti. Pri pretvorbi v RDF bomo vsako vrstico pretvorili v več trojčkov: en trojček za tip entitete (npr. `shema:Obcina`) in po en trojček za vsako lastnost (npr. naziv, število prebivalcev).

Za razumevanje trojčkov je koristen “polni” zapis s celotnimi URI-ji. V praksi pa skoraj vedno uporabimo predpone (`@prefix`), da je zapis bistveno bolj berljiv.

Sedaj v RDF obliko s serializacijo v TTL zapišimo podatke o prvi občini, `Ajdovščina`:

```turtle
https://onto.mdp.gov.si/obcina/ajdovscina http://www.w3.org/1999/02/22-rdf-syntax-ns#type https://onto.mdp.gov.si/shema/Obcina .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/idObcinaSurs "001" .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/naziv "Ajdovščina" .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/steviloPrebivalcev 19895 .
```

Pri zapisu v obliko trojčkov smo si izbrali URI `https://onto.mdp.gov.si/obcina/ajdovscina` za identifikacijo občine Ajdovščina, lastnosti `https://onto.mdp.gov.si/shema/idObcinaSurs` za SURS-ov enolični identifikator, `https://onto.mdp.gov.si/shema/naziv` za poimenovanje in `https://onto.mdp.gov.si/shema/steviloPrebivalcev` za število prebivalcev. Uporabili smo tudi standardni RDF predikat `http://www.w3.org/1999/02/22-rdf-syntax-ns#type`, da opredelimo, da gre za entiteto tipa `Obcina`.

Opazimo, da je `https://onto.mdp.gov.si/shema/steviloPrebivalcev` številska vrednost, zato je zapisana brez narekovajev, medtem ko sta `https://onto.mdp.gov.si/shema/idObcinaSurs` in `https://onto.mdp.gov.si/shema/naziv` besedilni vrednosti in sta zapisani z narekovaji. V RDF zapisu so to [literali](https://www.w3.org/TR/rdf11-concepts/#section-Graph-Literal); tipe (npr. `xsd:integer` ali `xsd:string`) lahko kasneje tudi eksplicitno določimo.

V praksi bomo za vsako občino hranili oba identifikatorja (npr. šifro CRP in SURS) kot lastnosti iste entitete. S tem naredimo prvi korak k usklajevanju virov, ne da bi podatke podvajali.

> Če na podatke v CSV obliki gledamo kot 2D tabelo, potem posamezno vrstico tabele pretvorimo v več RDF trojčkov, kjer vsak stolpec predstavlja lastnost, vrstica pa subjekt (entiteto). S tem smo podatke iz tabelarične oblike pretvorili v grafovno obliko, ki omogoča bolj fleksibilno predstavitev in povezovanje podatkov.

Dodamo lahko še nekaj dodatnih občin:

```turtle
https://onto.mdp.gov.si/obcina/ajdovscina http://www.w3.org/1999/02/22-rdf-syntax-ns#type https://onto.mdp.gov.si/shema/Obcina .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/idObcinaSurs "001" .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/naziv "Ajdovščina" .
https://onto.mdp.gov.si/obcina/ajdovscina https://onto.mdp.gov.si/shema/steviloPrebivalcev 19895 .

https://onto.mdp.gov.si/obcina/ankaran http://www.w3.org/1999/02/22-rdf-syntax-ns#type https://onto.mdp.gov.si/shema/Obcina .
https://onto.mdp.gov.si/obcina/ankaran https://onto.mdp.gov.si/shema/idObcinaSurs "213" .
https://onto.mdp.gov.si/obcina/ankaran https://onto.mdp.gov.si/shema/naziv "Ankaran" .
https://onto.mdp.gov.si/obcina/ankaran https://onto.mdp.gov.si/shema/steviloPrebivalcev 3446 .

https://onto.mdp.gov.si/obcina/apace http://www.w3.org/1999/02/22-rdf-syntax-ns#type https://onto.mdp.gov.si/shema/Obcina .
https://onto.mdp.gov.si/obcina/apace https://onto.mdp.gov.si/shema/idObcinaSurs "195" .
https://onto.mdp.gov.si/obcina/apace https://onto.mdp.gov.si/shema/naziv "Apače" .
https://onto.mdp.gov.si/obcina/apace https://onto.mdp.gov.si/shema/steviloPrebivalcev 3563 .
```

Ko se količina podatkov povečuje, postane tak zapis manj pregleden. Zato lahko uporabimo **predpone** za skrajšanje URI-jev in izboljšanje berljivosti.

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix obcina: <https://onto.mdp.gov.si/obcina/> .
@prefix shema:  <https://onto.mdp.gov.si/shema/> .

obcina:ajdovscina a shema:Obcina .
obcina:ajdovscina shema:idObcinaSurs "001" .
obcina:ajdovscina shema:naziv "Ajdovščina" .
obcina:ajdovscina shema:steviloPrebivalcev 19895 .

obcina:ankaran a shema:Obcina .
obcina:ankaran shema:idObcinaSurs "213" .
obcina:ankaran shema:naziv "Ankaran" .
obcina:ankaran shema:steviloPrebivalcev 3446 .

obcina:apace a shema:Obcina .
obcina:apace shema:idObcinaSurs "195" .
obcina:apace shema:naziv "Apače" .
obcina:apace shema:steviloPrebivalcev 3563 .
```

Dodatno lahko uporabimo tudi **zapis kratkih oblik** za še bolj jedrnat zapis, saj opazimo, da se določeni osebki ponavljajo. Namesto `rdf:type` lahko uporabimo tudi `a`.

```turtle
@prefix rdf:    <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix obcina: <https://onto.mdp.gov.si/obcina/> .
@prefix shema:  <https://onto.mdp.gov.si/shema/> .

obcina:ajdovscina a shema:Obcina ;
    shema:idObcinaSurs "001" ;
    shema:naziv "Ajdovščina" ;
    shema:steviloPrebivalcev 19895 .

obcina:ankaran a shema:Obcina ;
    shema:idObcinaSurs "213" ;
    shema:naziv "Ankaran" ;
    shema:steviloPrebivalcev 3446 .

obcina:apace a shema:Obcina ;
    shema:idObcinaSurs "195" ;
    shema:naziv "Apače" ;
    shema:steviloPrebivalcev 3563 .
```

Če gre pri trojčkih RDF za ponavljanje osebkov, na koncu vrstice uporabimo podpičje `;` in v novi vrstici izpustimo osebek. Če pa gre za ponavljanje osebkov in povedkov, pa uporabimo vejico `,` in v novi vrstici izpustimo osebek in povedek.

#### 3.5 Kako določimo URI-je?

Pri prehodu na raven 4 ★ je ena od ključnih odločitev, kako bomo entitetam dodelili **stabilne** in **smiselne URI-je**. Pri tem upoštevamo nekaj osnovnih načel:

- URI naj se s časom ne spreminja (tudi če se spremeni naziv entitete) in naj bo **stabilen**.
- URI naj bo **berljiv** in človeku razumljiv.
- URI mora biti znotraj problemske domene **enoličen** (v idealnem primeru tudi globalno).
- **Ne** uporabljajte **posebnih znakov**, zgolj majhne črke, vezaje, brez presledkov, šumnike pravilom pretvorimo (`č` → `c`, `š` → `s`, `ž` → `z`).
- **Izogibanje internim enoličnim identifikatorjem kot edinem ključu** - če so ID-ji vezani na konkreten sistem (npr. Excel šifrant), jih pogosto hranimo kot lastnost (npr. `shema:idObcinaSurs`), ne pa nujno kot edini del URI-ja.

V okviru delavnice bomo uporabljali preprost vzorec:

- za entitete: `https://onto.mdp.gov.si/obcina/{naziv-obcine}`
- za pojme v shemi/modelu: `https://onto.mdp.gov.si/shema/{naziv-pojma}`

S tem ločimo:

- **entitete** (npr. `obcina:ajdovscina`), ki predstavljajo konkretne stvari v realnem svetu,
- **pojme** (npr. `shema:Obcina`, `shema:naziv`, `shema:steviloPrebivalcev`), ki predstavljajo lastnosti, relacije ali kategorije, ki jih uporabljamo za opis entitet.

#### 3.6 Kaj dobimo z ravnjo 4 ★?

Ko podatke zapišemo v RDF in uporabimo URI-je, dosežemo več kot zgolj zapis v drugem formatu:

- pri imenih ni več dvoumnosti, saj imamo **enolično identifikacijo** vsake entitete,
- **povezljivost** med različnimi viri (npr. isti URI se lahko uporablja v CRP in SURS kontekstu),
- **grafovska struktura** podatkov, ki ni omejena zgolja na 2D tabelo, ampak omogoča predstavitev kompleksnih odnosov med pojmi,
- boljšo osnovo za **poizvedovanje** (SPARQL) in kasneje tudi **sklepanje**,
- predpogoj za naslednji korak **formalizacije pomena z ontologijo**, kar predstavimo v nadaljevanju.

Ko naši podatki dosežejo raven 4 ★, dosežemo stanje, kjer podatki postanejo dejansko interoperabilni na semantični ravni - ne le prenosljivi, ampak tudi razumljivi in povezljivi. To je ključni korak k temu, da lahko podatke dejansko uporabimo za odgovarjanje na kompleksna vprašanja, ki zahtevajo integracijo več virov.

</details>

### 4. Formalizacija podatkovnega modela z ontologijami

<p align="left">
  <img src="./assets/img/logo_4.png" alt="4. poglavje" width="200px" />
</p>

<details>
<summary>Prikaži podrobnosti</summary>

#### 4.1 Zakaj RDF sam po sebi ni dovolj?

V prejšnjem koraku smo podatke zapisali v obliki RDF in jim dodelili URI-je, s čimer smo dosegli enolično identifikacijo entitet, osnovno povezljivost in strojno berljiv ter razširljiv zapis.

Vendar nam RDF sam po sebi še ne pove:

- kaj natančno pomeni pojem `Obcina`,
- katere lastnosti smiselne,
- ali ima lahko občina več nazivov,
- ali je `steviloPrebivalcev` obvezen podatek.

Brez uporabe ontologije so ta pravila implicitna, zapisana zgolj v dokumentaciji ali v obliki tacitnega znanja razvijalcev in so nedostopna računalniški interpretaciji. Ontologija ta pravila **formalizira**, **eksplicitno opredeli** pomen pojmov, njihove lastnosti in medsebojne odnose ter jih naredi **strojno razumljive**.

#### 4.2 Kaj je ontologija (v kontekstu delavnice)?

V kontekstu delavnice je **ontologija** formalni opis pojmov, njihovih lastnosti in medsebojnih odnosov v določenem področju (npr. občine, šole).

Ontologija opredeljuje:

- kaj obstaja (tj. razredi, npr. `Obcina`, `Naselje`, `UpravnaEnota`),
- kako je opisano (tj. lastnosti, npr. `naziv`, `steviloPrebivalcev`),
- kako so pojmi povezani (tj. relacije, npr. `jeDelObcine`, `imaNaselje`),
- pravila in omejitve (npr. `Obcina` mora imeti vsaj en `naziv`).

> Ontologija ni slovar pojmov, niti podatkovna baza - je **model pomena**.

#### 4.3 Ločevanje modela in podatkov: TBox in ABox

Pri delu z ontologijami jasno ločimo dve ravni:

- **TBox (Terminological Box)**: opisuje **strukturo in pravila** pojmov v ontologiji (npr. `Obcina` je vrsta `AdministrativnaEnota`, `steviloPrebivalcev` je lastnost, ki se nanaša na `Obcina`),
- **ABox (Assertional Box)**: vsebuje **konkretne podatke** oz. **primerke** in njihove lastnosti (npr. `obcina:ajdovscina` je primerek `Obcina`, `obcina:ajdovscina` ima `steviloPrebivalcev` `19895`).

Takšno ločevanje je pomembno, ker omogoča ponovno uporabo istega modela, loči domensko znanje od podatkov in olajša vzdrževanje in nadgradnje.

#### 4.4 Uvoz podatkov TTL v orodje za upravljanje ontologij

V tem koraku se še ne bomo ukvarjali z ontologijo, ampak bo začeli z **realnimi podatki SURS**, ki smo jih v predhodnjem koraku pretvorili iz CSV v RDF/TTL.

Trenutna datoteka vsebuje:

- posamezne občine kot entitete RDF,
- osnovne lastnosti (npr. naziv, število prebivalce, SURS ID),
- vendar **še nima formalnega modela** (TBox).

Uporabili bomo orodje [Protégé](https://protege.stanford.edu/), ki je odprtokodno orodje za urejanje ontologij in RDF podatkov.

Zahtevali (`File` &rarr; `Open`) bomo datoteko [`SURS_obcine.ttl`](./assets/data/processed/SURS_obcine.ttl), ki predstavlja razširitev našega predhodnjega primera z vsemi občinami, ki so na voljo v izvorni SURS-ovi datoteki [`data.tsv`](./assets/data/raw/SURS/data.tsv).

<p align="center">
  <img src="./assets/img/Protege_start_SURS.png" alt="Začetni pogled orodja Protégé" width="800px" />
</p>

Na začetnem zaslonu na zgornji sliki opazimo povzetek vsebine naših podatkov, kjer mogoče izpostavimo nekaj ključnih informacij:

- **število trditev** _(angl. Axiom)_ je **848**, kar predstavlja število aksiomov, ki jih Protégé interpretira iz datoteke, pri čistem zapisu RDF to pogosto sovpada s trojčki (`212` občin × `4` trditve na občino = `848`),
- **število primerkov** _(angl. Individual count)_ je **212**, kar ustreza številu občin v Sloveniji (glede na podatke SURS za leto 2025),
- **število lastnosti** _(angl. Annotation Property count)_ je **3**, kar ustreza lastnostim (`idObcinaSurs`, `naziv`, `steviloPrebivalcev`), ki jih je Protégé tako interpretiral, ker še niso formalno opredeljene kot podatkovne lastnosti.

Po uvozu v Protégé lahko v zavihku `Individuals` (`Entities` &rarr; `Individuals`) pregledamo podatke, kjer vidimo seznam vseh občin in njihove lastnosti. Če izberemo posamezen primerek (npr. `ajdovscina`) lahko vidimo njegove lastnosti in vrednosti.

<p align="center">
  <img src="./assets/img/Protege_individuals_SURS.png" alt="Primerki podatkov SURS v Protégé" width="800px" />
</p>

V zavihku `Classes` (`Entities` &rarr; `Classes`) pa vidimo, da imamo opredeljen zgolj RDF razred `Obcina`, ki je uporabljen v našem primeru, ni pa dodatno opisan. Prisoten je zgolj seznam primerkov tega razreda.

<p align="center">
  <img src="./assets/img/Protege_classes_SURS.png" alt="Razred podatkov SURS v Protégé" width="800px" />
</p>

> To je tipično začetno stanje, kjer imamo **podatke (ABox)**, vendar še **nismo definirali modela (TBox)** oz. je le-ta zelo osnoven. V naslednjem koraku bomo začeli z gradnjo ontologije, ki bo formalizirala pomen naših podatkov.

#### 4.5 Prvi korak formalizacije: opis razreda

Naslednji korak je, da iz obstoječih podatkov SURS **izluščimo pojme**, ki jih implicitno že uporabljamo.

Pri tem ugotovimo, da opisujemo **občine**, ki so opisane s SURS-ovim ID-jem, imenom in številom prebivalcev za določeno leto.

To vodi do prvega osnovnega razreda `Obcina`, ki pa je implicitno že opredeljen, saj vsi naši primerki pripadajo temu razredu, kot to prikazuje naslednji primer.

```turtle
obcina:ajdovscina a shema:Obcina .
```

> V Protégé je privzeto prikazano lokalno ime `Obcina`, v ozadju pa gre za URI `shema:Obcina`.

Sedaj bomo ta nov razred `Obcina` formalno definirali v našem modelu, in sicer lahko dodamo naslednje trditve in ponovno naložimo datoteko v Protégé:

```turtle
@prefix owl:   <http://www.w3.org/2002/07/owl#> .

shema:Obcina a owl:Class ;
  rdfs:label "Občina"@sl ;
  rdfs:label "Municipality"@en .
```

<p align="center">
  <img src="./assets/img/Protege_classes_label_SURS.png" alt="Oznaka razreda podatkov SURS v Protégé" width="800px" />
</p>

Lahko pa s klikom na `+` pri `Annotations` novo oznako dodamo tudi ročno, kjer najprej izberemo `rdfs:label`, v polje `Value` pa vnesemo oznako razreda v španskem jeziku (npr. `Municipio`) in jo označimo z jezikovno oznako `@es`, kot prikazuje spodnja slika.

<p align="center">
  <img src="./assets/img/Protege_label_add_SURS.png" alt="Dodajanje oznake razreda podatkov SURS v Protégé" width="800px" />
</p>

Posledično se v izvorni kodi TTL doda naslednja trditev za `shema:Obcina`:

```turtle
shema:Obcina rdf:type owl:Class ;
             rdfs:label "Municipality"@en ,
                        "Občina"@sl ,
                        "Municipio"@es .
```

> Za lastnost smo uporabili [`rdfs:label`](https://www.w3.org/TR/rdf-schema/#ch_label) kot standardno lastnost za opisovanje oznak pojmov, ki je del [RDF Schema (RDFS)](https://www.w3.org/TR/rdf-schema/).

Ko ontologijo shranimo z orodjem Protégé, pa opazimo, da je prisotnih nekaj dodatnih trditev, ki jih Protégé samodejno doda za boljšo interoperabilnost in skladnost z OWL standardom.

To je npr. opredelitev lastnosti (ki jih še nismo formalno definirali, ampak so implicitno prisotne v naših podatkih):

```turtle
shema:idObcinaSurs rdf:type owl:AnnotationProperty .
shema:naziv rdf:type owl:AnnotationProperty .
shema:steviloPrebivalcev rdf:type owl:AnnotationProperty .
```

> Ker lastnosti v začetnem SURS TTL niso formalno opredeljene, jih Protégé interpretira kot **oznake** (annotations) in jih zato označi kot `owl:AnnotationProperty`. V naslednjem koraku bomo te lastnosti formalno definirali kot **podatkovne lastnosti** (data properties) z uporabo `owl:DatatypeProperty`, kar bo omogočilo boljšo interpretacijo in uporabo teh lastnosti v našem modelu.

Prav tako vsakemu primerku (občini) doda trditev, da je [`owl:NamedIndividual`](https://www.w3.org/TR/owl2-syntax/#Named_Individuals), kar pomeni, da gre za konkretno entiteto, ki je del naše ontologije:

```turtle
obcina:ajdovscina rdf:type owl:NamedIndividual ,
                           shema:Obcina ;
                  shema:idObcinaSurs "001" ;
                  shema:naziv "Ajdovščina" ;
                  shema:steviloPrebivalcev 19895 .
```

Prav tako se opredeli osnovni prostor imen z uporabo `@base` in aktivno ontologijo, kar omogoča krajši zapis URI-jev v datoteki.

```turtle
@base <https://onto.mdp.gov.si/shema/> .
<https://onto.mdp.gov.si/shema/> a owl:Ontology .
```

#### 4.6 Podatkovne lastnosti

Naslednji korak je formalizacija lastnosti, ki jih podatki SURS že vsebujejo.

Iz vsebine lahko razberemo naslednje lastnosti:

- enolični identifikator občine po SURS-u,
- ime občine in
- število prebivalcev občine.

V grafičnem vmesniku Protégé (`Entities` &rarr; `Data properties` &rarr; `Create a new Data property`) lahko te lastnosti dodamo kot **podatkovne lastnosti** _(angl. Data Properties)_, ker se nanašajo na vrednosti, ki so literali (npr. besedilo, število).

Podatkovni lastnosti `idObcinaSurs` določimo naslednje atribute:

- ime _(angl. Name)_: `idObcinaSurs`,
- domena _(angl. Domain)_: `Obcina`,
- obseg _(angl. Range)_: `xsd:string`,
- oznake _(angl. Annotation)_: `SURS ID občine`@sl.

Posledično se v izvorni kodi TTL dodajo naslednje trditve:

```turtle
shema:idObcinaSurs a owl:DatatypeProperty ;
                   rdfs:domain shema:Obcina ;
                   rdfs:range xsd:string ;
                   rdfs:label "SURS ID občine"@sl .
```

Podobno dodajmo še lastnosti `naziv` in `steviloPrebivalcev` z ustreznimi atributi, pri čemer `steviloPrebivalcev` določimo kot `xsd:integer`, saj gre za številsko vrednost.

```turtle
shema:naziv a owl:DatatypeProperty ;
            rdfs:domain shema:Obcina ;
            rdfs:range xsd:string ;
            rdfs:label "naziv"@sl .

shema:steviloPrebivalcev a owl:DatatypeProperty ;
                         rdfs:domain shema:Obcina ;
                         rdfs:range xsd:integer ;
                         rdfs:label "število prebivalcev"@sl .
```

Ob ponovnem nalaganju datoteke v Protégé lahko sedaj v zavihku `Data properties` vidimo naše formalno definirane lastnosti z njihovimi atributi.

<p align="center">
  <img src="./assets/img/Protege_data_properties_SURS.png" alt="Podatkovne lastnosti podatkov SURS v Protégé" width="800px" />
</p>

Izvorna koda primera do tega trenutka je na voljo v [`SURS_obcine_dp.ttl`](./assets/data/processed/SURS_obcine_dp.ttl), kjer so dodane formalne definicije razreda `Obcina` in podatkovnih lastnosti `idObcinaSurs`, `naziv` in `steviloPrebivalcev`.

#### 4.7 Nadgradnja z objektnimi lastnostmi

Pri podatkih, ki jih trenutno imamo na voljo, je zagotovo na mestu vprašanje - kako bi vključili še zgodovinske podatke ali podatke za naslednja leta.

Namesto da ima občina `steviloPrebivalcev` kot enostavno številsko vrednost, bi lahko imeli **povezavo na drug primerek**, ki predstavlja **meritev števila prebivalcev za določeno leto**.

> To je tipičen primer, kjer se izkaže grafovska struktura v primerjavi s tabelarično. Atribut `steviloPrebivalcev` v resnici ni lastnost občine, ampak lastnost opazovanja občine skozi leta. Zato vrednost modeliramo ločeno, da lahko imamo več meritev za različna leta, ne da bi morali spreminjati strukturo razreda `Obcina`.

Vpeljali bi lahko razred `MeritevPrebivalcev`, ki bi imel lastnosti `leto` in `vrednost`, ter nato v razred `Obcina` dodali **objektno lastnost** _(angl. Object Property)_ `imaMeritevPrebivalcev`, ki bi kazala na primerek `MeritevPrebivalcev`.

Najprej dodajmo razred `MeritevPrebivalcev` in nove lastnosti, povezane z njim. Atribut `leto` določimo kot `xsd:gYear`, saj gre za letnico, medtem ko `vrednost` ostane `xsd:integer`.

```turtle
shema:MeritevPrebivalcev a owl:Class ;
                          rdfs:label "Meritev števila prebivalcev"@sl .

shema:leto a owl:DatatypeProperty ;
            rdfs:domain shema:MeritevPrebivalcev ;
            rdfs:range xsd:gYear ;
            rdfs:label "leto"@sl .

shema:vrednost a owl:DatatypeProperty ;
                rdfs:domain shema:MeritevPrebivalcev ;
                rdfs:range xsd:integer ;
                rdfs:label "vrednost"@sl .
```

Posledično lahko obstoječo podatkovno lastnost `steviloPrebivalcev` nadomestimo z novo objektno lastnostjo `imaMeritevPrebivalcev`, ki bo kazala na primerek `MeritevPrebivalcev`.

> V nadaljevanju `shema:steviloPrebivalcev` ne uporabljamo več neposredno kot lastnost razreda `Obcina`, ampak vrednost hranimo prek meritev; lastnost lahko zato odstranimo.

```turtle
shema:imaMeritevPrebivalcev a owl:ObjectProperty ;
                             rdfs:domain shema:Obcina ;
                             rdfs:range shema:MeritevPrebivalcev ;
                             rdfs:label "ima meritev števila prebivalcev"@sl .
```

<p align="center">
  <img src="./assets/img/Protege_object_properties_SURS.png" alt="Objektna lastnost podatkov SURS v Protégé" width="800px" />
</p>

#### 4.8 Preoblikovanje podatkov z novo strukturo

Podatke (tj. primerki) o številu prebivalcev iz SURSA bomo sedaj preoblikovali tako, da namesto neposredne vrednosti `steviloPrebivalcev` vsebujejo povezavo na primerek `MeritevPrebivalcev`, ki ima lastnosti `leto` in `vrednost`. To nam omogoča, da imamo več meritev za različna leta, ne da bi morali spreminjati strukturo razreda `Obcina`.

Za občino `Ajdovščina` to izgleda takole:

```turtle
obcina:ajdovscina a shema:Obcina ;
    shema:idObcinaSurs "001" ;
    shema:naziv "Ajdovščina" ;
    shema:imaMeritevPrebivalcev obcina:ajdovscina-stevilo-prebivalcev-2024, obcina:ajdovscina-stevilo-prebivalcev-2025 .

obcina:ajdovscina-stevilo-prebivalcev-2024 a shema:MeritevPrebivalcev ;
    shema:leto "2024"^^xsd:gYear ;
    shema:vrednost 19891 .

obcina:ajdovscina-stevilo-prebivalcev-2025 a shema:MeritevPrebivalcev ;
    shema:leto "2025"^^xsd:gYear ;
    shema:vrednost 19895 .
```

Celotna datoteka z nadgrajenim modelom in preoblikovanimi podatki je na voljo v [`SURS_obcine_dp_op.ttl`](./assets/data/processed/SURS_obcine_dp_op.ttl).

</details>

### 5. Raven 5 ★: povezani podatki in zunanji viri

<p align="left">
  <img src="./assets/img/logo_5.png" alt="5. poglavje" width="200px" />
</p>

<details>
<summary>Prikaži podrobnosti</summary>

#### 5.1 Kaj pomeni raven 5 ★ v praksi?

Na ravni 4 ★ smo podatke zapisali v RDF, dodali enolične URI-je, formalizirali model z ontologijo (formalni model TBox in strukturirane primerke ABox) in dosegli strojno razumljivost. Vendar so naši podatki še vedno **izolirani** - niso povezani z drugimi viri, ne uporabljajo skupnih pojmov ali standardov, in niso del širšega ekosistema podatkov.

Raven 5 ★ dosežemo šele, ko naše podatke **povežemo z drugimi viri** in **uporabimo skupne pojme** iz obstoječih ontologij, s čimer postanejo del globalnega spletnega ekosistema podatkov.

Ključna razlika je:

> 4 ★ = podatki so **semantično opisani**  
> 5 ★ = podatki so semantično opisani in **povezani z drugimi podatki**

#### 5.2 Zunanji viri za povezovanje

- **Repozitorij podatkovnih modelov** (npr. Centralni besednjak) na Platformi za semantično interoperabilnost.
- **Splošne terminološke (TBox) ontologije** (npr. [Schema.org](https://schema.org/), [FOAF](http://xmlns.com/foaf/spec/), [Dublin Core](http://purl.org/dc/elements/1.1/)), [SKOS](http://www.w3.org/2004/02/skos/core#), [DCAT](http://www.w3.org/ns/dcat#) idr.
- **Splošne podatkovne (ABox) ontologije** (npr. [DBpedia](https://wiki.dbpedia.org/), [Wikidata](https://www.wikidata.org/), [LinkedGeoData](http://linkedgeodata.org/)) idr.
- **Domenski besednjaki** (npr. [EUROVOC](https://eurovoc.europa.eu/), [GEMET](https://www.eionet.europa.eu/gemet/)), [INSPIRE](https://inspire.ec.europa.eu/glossary), [GeoNames](https://www.geonames.org/) idr.

> Povezovanje z zunanjimi viri ne pomeni, da bomo vse podatke fizično uvozili v lastno podatkovno zbirko. Ključna ideja povezanih podatkov je, da **ohranimo podatke pri izvoru**, mi pa zagotovimo **enolične povezave**, prek katerih lahko po potrebi dostopamo po dodatnih informacijah.

V nadaljevanju se ne bomo osredotočili na množično povezovanje z zunanjimi viri, ampak bomo najprej pogledali **povezovanje znotraj javnega sektorja**, in sicer na primeru [`CRP.ttl`](./assets/data/processed/CRP.ttl), ki predstavlja referenčne, produkcijsko usmerjen model. Na njem bomo pokazali osnovne semantične mehanizme povezovanja, ki so uporabni pri povezovanju z zunanjimi viri.

#### 5.3 Povezovanje s hierarhijo pojmov (`rdfs:subClassOf`)

V ontologiji CRP so pojmi organizirani v **hierarhijo razredov**, kar omogoča ponovno uporabo lastnosti in bolj splošne poizvedbe. V zvihku `Entities` &rarr; `Classes` lahko opazimo hierarhijo (glej spodnjo sliko), kjer so razredi organizirani z uporabo lastnosti `rdfs:subClassOf`, kar pomeni, da je en razred podrazred drugega.

- `cnbs:Sifrant`
  - `:SifrantIO`
    - `:Obcina`

<p align="center">
  <img src="./assets/img/Protege_subclasses_CRP.png" alt="Razredna hierarhija podatkov CRP v Protégé" width="800px" />
</p>

Zapis hierarhije v RDF/TTL je naslednji:

```turtle
@prefix : <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix cnbs: <http://onto.mju.gov.si/centralni-besednjak-sifranti#> .

cnbs:Sifrant rdf:type owl:Class .

:SifrantIO rdf:type owl:Class ;
           rdfs:subClassOf cnbs:Sifrant .

:Obcina rdf:type owl:Class ;
        rdfs:subClassOf :SifrantIO .
```

S tem formalno opredelimo, da je vsaka `Obcina` tudi `SifrantIO` in vsak `SifrantIO` tudi `cnbs:Sifrant`.

Pri tem smo načrtno uporabili pojme iz **Centralnega besednjaka** (npr. `cnbs:Sifrant`), ki je del Platforme za semantično interoperabilnost, da pokažemo, kako lahko uporabimo skupne pojme za povezovanje z zunanjimi viri. S tem smo dosegli, da so naši podatki o občinah del širšega ekosistema podatkov, ki uporablja skupne standarde in pojme.

> To predstavlja temelj za sklepanje: če poizvedujemo po vseh `cnbs:Sifrant`, bomo samodejno dobili tudi `:Obcina`, če seveda uporabljamo mehanizme sklepanja, ki upoštevajo hierarhijo razredov.

#### 5.4 Povezovanje s hierarhijo lastnosti (`rdfs:subPropertyOf`)

Podoben koncept kot pri razredih velja tudi za lastnosti. V CRP-ju se pogosto pojavi situacija, kjer imamo splošno lastnost (npr. identifikator) in nato bolj specifične lastnosti, ki so podlastnosti te splošne lastnosti (npr. identifikator v določenem registru).

V zavihku `Entities` &rarr; `Data properties` lahko opazimo hierarhijo lastnosti (glej spodnjo sliko), kjer so določene lastnosti označene kot `rdfs:subPropertyOf` drugih lastnosti.

- [`foaf:givenName`](https://xmlns.com/foaf/spec/#term_givenName)
  - `:ime`
    - `:mat_ime_1`

<p align="center">
  <img src="./assets/img/Protege_subproperties_CRP.png" alt="Hierarhija lastnosti podatkov CRP v Protégé" width="800px" />
</p>

Zapis hierarhije v RDF/TTL je naslednji:

```turtle
@prefix : <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix cnb: <http://onto.mju.gov.si/centralni-besednjak-core#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .

:ime rdf:type owl:DatatypeProperty ;
     rdfs:subPropertyOf foaf:givenName ;
     rdfs:domain cnb:FizicnaOseba ;
     rdfs:range [ rdf:type rdfs:Datatype ;
                  owl:onDatatype xsd:string ;
                  owl:withRestrictions ( [ xsd:maxLength "35"^^xsd:nonNegativeInteger
                                         ]
                                       )
                ] ;
     rdfs:label "ime"@sl .

:mat_ime_1 rdf:type owl:DatatypeProperty ;
           rdfs:subPropertyOf :ime ;
           rdfs:label "prvo ime matere"@sl .
```

S tem formalno opredelimo, da je `:mat_ime_1` podlastnost `:ime`, ki je podlastnost `foaf:givenName`. To pomeni, da če imamo trditev, da ima neka oseba `:mat_ime_1` vrednost "Marija", lahko sklepamo, da ima ta oseba tudi `:ime` "Marija" in `foaf:givenName` "Marija", če uporabljamo mehanizme sklepanja, ki upoštevajo hierarhijo lastnosti. Prav tako se deduje tudi vse omejitve, npr. dolžina 35 znakov, ki je opredeljena na `:ime`, velja tudi za `:mat_ime_1`.

#### 5.5 Povezovanje istih primerkov (`owl:sameAs`)

V nekaterih primerih vemo, da dva URI-ja predstavljata **popolnoma isto entiteto**, le v različnih podatkovnih virih.

V našem primeru občina Ajdovščina v viru CRP (`:Obcina_1`) predstavlja isto občino, ki je opredeljena tudi na Wikidata (`wd:Q331701`).

<p align="center">
  <img src="./assets/img/Protege_sameAs_CRP.png" alt="Isti primerki podatkov CRP v Protégé" width="800px" />
</p>

Zapis hierarhije v RDF/TTL je naslednji:

```turtle
@prefix : <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix wd: <https://www.wikidata.org/entity/> .

:Obcina_1 rdf:type owl:NamedIndividual ,
                   :Obcina ;
          :identifikator 1 ;
          :vrednost "Ajdovščina"@sl ;
          owl:sameAs wd:Q331701 .
```

Semantični pomen tega zapisa je močan, in sicer: vse, kar velja za `:wd:Q331701` (npr. da je to občina, da ima določene lastnosti, da je del Slovenije), velja tudi za `:Obcina_1`, in obratno. To nam omogoča, da združimo informacije iz različnih virov, ne da bi morali fizično združiti podatke, ampak preprosto zagotovimo povezavo med njimi.

#### 5.6 Povezovanje pojmov (`owl:equivalentClass`)

V predhodnjih korakih smo povezovali **primerke** (`owl:sameAs`) in gradili **hierarhije** razredov (`rdfs:subClassOf`) oz. lastnosti (`rdfs:subPropertyOf`). Pogosto pa želimo povezati tudi **pojme** oz. razrede, npr. v našem primeru pojem **občine** pomeni isto kot pojem **municipality** v nekem drugem slovarju ali ontologiji. Za to lahko uporabimo gradnik `owl:equivalentClass`.

V CRP-ju je razred `:Obcina` zapisan kot definiran razred, in sicer z natančnim opisom, kaj vse ga opredeljuje. To je razvidno v naslednjem zapisu in pogledu v orodju Protégé, in sicer v dveh delih:

- Zaprt nabor primerkov z `owl:equivalentClass` in `owl:oneOf`, kjer so navedeni vsi primerki, ki spadajo v razred `:Obcina` (npr. `:Obcina_1`, `:Obcina_10`, `:Obcina_100` itd.).
- Omejitev pri dedovanju z `rdfs:subClassOf`, kjer ima `:identifikator` omejitev vrednosti med 1 in 999, `:vrednost` pa omejitev dolžine do 35 znakov.

```turtle
:Obcina rdf:type owl:Class ;
        owl:equivalentClass [ rdf:type owl:Class ;
                              owl:oneOf ( :Obcina_1
                                          :Obcina_10
                                          :Obcina_100
                                          ...
                                        )
                            ] ;
        rdfs:subClassOf :SifrantIO ,
                        [ rdf:type owl:Restriction ;
                          owl:onProperty :identifikator ;
                          owl:allValuesFrom [ rdf:type rdfs:Datatype ;
                                              owl:onDatatype xsd:int ;
                                              owl:withRestrictions ( [ xsd:minInclusive 1
                                                                     ]
                                                                     [ xsd:maxInclusive 999
                                                                     ]
                                                                   )
                                            ]
                        ] ,
                        [ rdf:type owl:Restriction ;
                          owl:onProperty :vrednost ;
                          owl:allValuesFrom [ rdf:type rdfs:Datatype ;
                                              owl:onDatatype xsd:string ;
                                              owl:withRestrictions ( [ xsd:maxLength "35"^^xsd:nonNegativeInteger
                                                                     ]
                                                                   )
                                            ]
                        ] ;
        rdfs:label "Občina"@sl .
```

<p align="center">
  <img src="./assets/img/Protege_omejitev_razreda_CRP.png" alt="Omejitev razreda podatkov CRP v Protégé" width="800px" />
</p>

Takšen pristop je uporaben za **šifrante**, kjer želimo izrecno opredeliti, da gre za končen seznam.

#### 5.7 Povezovanje CRP in SURS podatkov

Sedaj si poglejmo konkreten primer povezovanja podatkov dveh virov:

- Centralnega registra prebivalcev (**CRP**) in
- Statističnega urada RS (**SURS**).

Cilj ni združevanje podatkov v eno datoteko, temveč omogočiti, da podatki iz različnih virov **opisujejo iste entitete** in jih lahko **skupaj uporabljamo v poizvedbah in sklepanju**. S tem namenom bomo integracijo opredelili v novi datoteki [`Integracija_CRP_SURS.ttl`](./assets/data/processed/Integracija_CRP_SURS.ttl), kjer bomo vzpostavili povezave med pojmi in primerki iz obeh virov.

CRP in SURS obravnavata **iste občine**, vendar z različnim namenom: v CRP-ju so uradni šifranti in stabilni identifikatorji, ne vsebuje pa statističnih kazalnikov (npr. števila prebivalcev), ki pa so prisotni v SURS-u.

Najbolj neposreden način povezovanja je na ravni **primerkov občin**, kjer lahko uporabimo `owl:sameAs`.

V CRP imamo npr.

```turtle
@prefix : <https://pzsi.sigov.si/datamodel/ns/crp#> .

:Obcina_1 rdf:type owl:NamedIndividual ,
                   :Obcina ;
          :identifikator 1 ;
          :vrednost "Ajdovščina"@sl .
```

V SURS-u pa imamo npr.

```turtle
@prefix shema: <https://onto.mdp.gov.si/shema/> .
@prefix obcina: <https://onto.mdp.gov.si/obcina/> .

obcina:ajdovscina a shema:Obcina ;
    shema:idObcinaSurs "001" ;
    shema:naziv "Ajdovščina" .
```

Ker vemo, da oba primerka predstavljata **isto realno občino**, ju lahko povežemo:

```turtle
@prefix crp: <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix sursABox: <https://onto.mdp.gov.si/obcina/> .

crp:Obcina_1 owl:sameAs sursABox:ajdovscina .
```

> Zaradi lažjega razumevanje in interpretacijo uporabimo predponi `crp` in `surs` za URI-je iz obeh virov.

S tem povemo, da gre za isto entiteto, lastnosti iz obeh virov veljajo za isto občino, poizvedbe lahko "prehajajo" med viroma. Ključno je, da **podatkov ne podvajamo**, ampak jih **logično združimo**.

Poleg primerkov lahko povežemo tudi **pojme**. Npr. v CRP-ju imamo razred:

```turtle
@prefix : <https://pzsi.sigov.si/datamodel/ns/crp#> .

:Obcina rdf:type owl:Class .
```

V SURS modelu pa:

```turtle
@prefix shema: <https://onto.mdp.gov.si/shema/> .
@prefix obcina: <https://onto.mdp.gov.si/obcina/> .

obcina:ajdovscina a shema:Obcina .
```

Če se odločimo, da oba pojma pomenita isto stvar (tj. občino), lahko uporabimo `owl:equivalentClass`. Posledica tega bi bila, da bi vsi primerki `:Obcina` v CRP-ju postali tudi `shema:Obcina` in obratno, kar omogoča skupno interpretacijo in uporabo lastnosti, ki so opredeljene na obeh straneh. Če pa želimo biti bolj previdni (npr. ker SURS model vključuje tudi zgodovinske oz. agregirane enote), lahko uporabimo šibkejšo povezavo `rdfs:subClassOf`.

```turtle
@prefix crp: <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix sursTBox: <https://onto.mdp.gov.si/shema/> .

sursTBox:Obcina rdfs:subClassOf crp:Obcina .
```

V okviru integracije za občino Ajdovščina že imamo povezavo na Wikidata (`owl:sameAs wd:Q331701`), kar pomeni, da je ta občina del širšega ekosistema podatkov, ki vključuje tudi SURS in CRP, saj so ti povezani z Wikidata. Dodajmo še omenjene povezave za nekaj drugih občin.

```turtle
@prefix crp: <https://pzsi.sigov.si/datamodel/ns/crp#> .
@prefix sursTBox: <https://onto.mdp.gov.si/shema/> .
@prefix sursABox: <https://onto.mdp.gov.si/obcina/> .
@prefix wd: <https://www.wikidata.org/entity/> .

sursTBox:Obcina rdfs:subClassOf crp:Obcina .

crp:Obcina_1 owl:sameAs sursABox:ajdovscina .
crp:Obcina_11 owl:sameAs sursABox:celje .
crp:Obcina_61 owl:sameAs sursABox:ljubljana .
crp:Obcina_70 owl:sameAs sursABox:maribor .

crp:Obcina_1 owl:sameAs wd:Q331701 .
crp:Obcina_11 owl:sameAs wd:Q3441823 .
crp:Obcina_61 owl:sameAs wd:Q3434113 .
crp:Obcina_70 owl:sameAs wd:Q3435104 .
```

</details>

### 6. Uporaba semantično opisanih podatkov s SPARQL

### 7. Sklepanje: prehod od podatkov k znanju

### 8. Vizualizacija in integracija v aplikacije
