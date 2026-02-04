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

> _"Katere upravne enote imajo največ prebivalcev, katere šole imajo tam sedež in kakšna je nadmorska višina teh območij?"_

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
  - [📊 `data.tsv`](./assets/data/raw/SURS/data.tsv),
  - [📄 `info.html`](./assets/data/raw/SURS/info.html),
  - [📝 `info.txt`](./assets/data/raw/SURS/info.txt).

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

<details>
<summary>Prikaži podrobnosti</summary>

#### 3.1 Zakaj CSV ni več dovolj?

V tem koraku naredimo **ključni preskok** od zgolj odprtih in strojno berljivih podatkov (3 ★) k **semantično opisanim podatkom** (4 ★). RDF, ki ga bomo uporabili, podatkom ne doda nove vsebine, temveč jasen in strojno razumljiv pomen.

Kot primer lahko izpostavimo `Ajdovščina` v CRP in `Ajdovščina` v SURS, ki za človeškega uporabnika pomenita isto občino, za računalnik pa gre zgolj za **enak niz znakov**, brez pomena.

Če želimo rešiti ta problem, moramo vpeljati:

- **enolične identifikatorje** (URI-je), ki bodo jasno določili, da gre za isto entiteto,
- **formalni opis pomena** (ontologijo), ki bo opredelila, kaj je občina, kakšne so njene lastnosti in kako se povezuje z drugimi pojmi,
- **model, ki presega tabelarično strukturo** in omogoča predstavitev kompleksnih odnosov med pojmi (RDF).

#### 3.2 RDF: opis podatkov v obliki trojčkov

[**RDF** (Resource Description Framework)](https://www.w3.org/RDF/) je standard za predstavitev podatkov v obliki **trojčkov**:

- **osebek** _(angl. subject)_ - kaj opisujemo (npr. `Upravna enota Ljubljana`),
- **povedek** _(angl. predicate)_ - katero lastnost opisujemo (npr. `ima sedež v`),
- **predmet** _(angl. object)_ - vrednost ali povezava (npr. `Ljubljana`).

Takšna struktura omogoča eksplicitno izražati pomen, povezovanje podatkov v graf in razširljivost brez spremembe obstoječih zapisov.

#### 3.3 URI: enolična identifikacija pojmov

Osnovna jezika RDF je uporaba URI-jev, ki predstavljajo stabilne, globalno enolične in spletno naslovljive identifikatorje.

Namesto npr. `OBC_ID=1` uporabimo npr. `https://onto.mdp.gov.si/obcina/ajdovscina`, ki jasno identificira občino Ajdovščina. S tem odpravimo dvoumnost, omogočimo povezovanje z drugimi viri in jasno ločimo pojem od njegovega zapisa v tabeli.

> **URI ni le identifikator** - je nosilec pomena, ki omogoča povezovanje in integracijo podatkov iz različnih virov.

#### 3.4 Zapis RDF v obliki Turtle (TTL)

RDF podatke lahko zapišemo v različnih formatih, eden izmed najbolj berljivih je **Turtle (TTL)**, ker je človeško berljiv in pogosto uporabljen v praksi.

Primer zapisa občine v obliki TTL:

```turtle
@prefix obcina: <https://onto.mdp.gov.si/obcina/> .
@prefix shema:  <https://onto.mdp.gov.si/shema/> .

obcina:ajdovscina a shema:Obcina ;
    shema:naziv "Ajdovščina" ;
    shema:steviloPrebivalcev 19895 .
```

> TO-DO: Razmisli kako dodati razreda (a)!?

</details>

### 4. Formalizacija podatkovnega modela z ontologijami

### 5. Raven 5 ★: povezani podatki in zunanji viri

### 6. Uporaba semantično opisanih podatkov s SPARQL

### 7. Sklepanje: prehod od podatkov k znanju

### 8. Vizualizacija in integracija v aplikacije

### 9. Povzetek in nadaljnji koraki
