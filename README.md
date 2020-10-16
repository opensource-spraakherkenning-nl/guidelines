# Minimale richtlijnen voor software kwaliteit & duurzaamheid

* De broncode van software hoort altijd **open** te zijn en in een **versiebeheersysteem** (wij gebruiken
  **git**) opgeslagen te zijn. Dit bevordert samenwerking en inzichtelijkheid
  van het ontwikkelingsproces.
    * Dit geldt zowel voor grote softwareproject
  alsmede voor kleinere verzamelingen aan scripts.
    * Dit geldt vanaf het prille
  begin van een softwareproject en moet geen gedachte achteraf zijn.
* De Stichting Open Spraaktechnologie heeft een [github
  groep](https://github.com/opensource-spraakherkenning-nl/) beschikbaar
  waaronder repositories voor specifieke softwareprojecten ondergebracht kunnen
  worden:
    * Per softwarepakket zou eigenlijk een ‘maintainer’ aangesteld moeten zijn
      die het beheert, d.w.z. diepe inhoudelijke kennis heeft van de software
      (meestal de lead developer), issues kan beantwoorden/oplossen, releases
      kan doen, etc...  Software die niet beheert wordt verouderd en wordt op
      den duur onbruikbaar omdat het niet meer compatibel is met andere software,
      of simpelweg omdat er zich problemen in voordoen die niet opgelost worden.
* Alle broncode moet vergezeld zijn van een passende open source **licentie**. De keuze
  hier gaat veelal om copyleft licenties als GPLv3 versus minder restrictieve licenties
  als MIT, Apache of BSD. Onze voorkeur gaat uit naar GPLv3 vanwege de share-alike/copyleft
  component die ervoor zorgt dat de code ook altijd open blijft. Een variant op deze
  licentie is de AGPL, die garandeert dat de code ook open vrijgegeven dient ook als men het
  alleen als een service via het web aanbiedt.
* Zorg bij elk softwareproject op zijn minst voor **documentatie** in de vorm van een README document,
  en uiteraard liever meer documentatie. De README moet op zijn duidelijk maken wat de software doet,
  voor wie het bestemd is, hoe het te installeren is, hoe het te gebruiken is, en wat überhaupt [de bruikbaarheidsstaat](http://repostatus.org) ervan is.
* Problemen/vragen als bug reports en feature requests dienen in de **issue
  tracker** gerapporteerd te worden die aan de source repository verbonden is.
  Dit houdt alles op één plek en maakt de staat en progressievan bepaalde vragen voor iedereen te volgen.
* Grote data (bv. grote getrainde modellen, veelal in een binair formaat) passen
  niet in de source repositories (tenzij middels bv. Git LFS/Annex extensies)
  en horen daarvan gescheiden te worden. In deze gevallen raden we aan dat er
  een download script meegeleverd is in de source repository die de installatie
  van alle benodigde data regelt, dwz. de data download en op een juiste plek
  lokaal beschikbaar maakt
* Software hoort zo veel mogelijk **bouwbaar**/compileerbaar en vervolgens installeerbaar
  te zijn volgens standaard manieren die bij het ecosysteem van de gekozen programmeertaal
  horen. Lever de nodige bouw-scripts (bv. setup.py voor Python, Makefile/autoconf/cmake
  voor C/C++, pom.xml voor Java, etc..)
* Als het ecosysteem een **software repository** biedt om software beschikbaar te
  maken en het gaat om een software(component) met enig potentieel voor
  (her)gebruik; gebruik deze repositories dan (bv Python Package Index voor
  Python, Maven voor Java, CRAN voor R, crates.io voor Rust, npm voor
  javascript, enz.. )
* Doe expliciete software **releases**; geef software versienummers volgens
  [semantic versioning](https://semver.org). Gebruik de release functionaliteit op github en lever
  releases aan software repositories zoals genoemd in het vorige punt.
    * Persistente archivering van software releases (en verkrijgen van een DOI voor
      citatie) kan via bv. Zenodo. Je kan een automatisch [koppeling tussen github
      releases en zenodo](https://guides.github.com/activities/citable-code/) instellen.
* Voor **distributie van complexe software-oplossingen** van vaak meerdere software
  componenten is een container (bv. Docker) aan te raden. De container image bevat alle
  software componenten, inclusief het onderliggende OS. Deze zijn voorgeconfigureerd zodat
  het geheel met minimale inspanningen in de lucht te brengen is..
    * Een specifieke oplossing die we hanteren vanuit CLARIAH en ook openstaat voor
      de stichting is [LaMachine](https://proycon.github.io/LaMachine); integratie in
      LaMachine biedt per definitie een container-oplossing (naast andere vormen).
      Een oplossing voor software metadata is hierin ook voorzien middels CodeMeta.

Meer uitgebreide richtlijnen zijn
[hier](https://github.com/CLARIAH/software-quality-guidelines) vastgelegd in
het kader van het CLARIAH project, belangrijke aspecten als testbaarheid en interoperabiliteit zijn bv. nog niet meegenomen in het bovenstaande lijstje.
