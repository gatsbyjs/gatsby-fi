---
title: Pystytä kehitysympäristösi
typora-copy-images-to: ./
disableTableOfContents: true
---

Ennen kuin aloitat ensimmäisen Gatsby-sivustosi rakentamisen, sinun on perehdyttävä joihinkin ydinweb-teknologioihin ja varmistettava, että olet asentanut kaikki vaadittavat ohjelmistotyökalut.

## Tutustu komentoriviin

Komentorivi on tekstipohjainen käyttöliittymä, jota käytetään komentojen suorittamiseen tietokoneellasi. Usein sitä voidaan kutsuta myös terminaaliksi. Käytämme tässä tutoriaalissa molempia vaihtokelpoisesti. Sen käyttö muistuttaa paljon Finderin käyttöä Macilla tai Resurssienhallintaa Windowsissa. Finder ja Resurssienhallinta ovat esimerkkejä graafisista käyttöliittymistä (GUI). Komentorivi on tehokas, tekstipohjainen tapa olla vuorovaikutuksessa tietokoneesi kanssa.

Käytä hetki etsiäksesi ja avataksesi komentoriviliittymä (CLI) tietokoneellesi. Riippuen mitä käyttöjärjestelmää käytät, katso [**ohjeet Macille**](http://www.macworld.co.uk/feature/mac-software/how-use-terminal-on-mac-3608274/), [**ohjeet Windowsille**](https://www.lifewire.com/how-to-open-command-prompt-2618089) tai [**ohjeet Linuxille**](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/).

_**Huom:** Jos olet uusi komentoriville, "käynnissä" komento, tarkoittaa "kirjoittamalla annetut ohjeet komentokehotteessasi, ja painamalla Enter-näppäintä". Komennot näytetään korostettuna ruudussa, jotakuinkin `node --version`, mutta kaikki korostetut ruudut eivät ole komentoja! Jos jokin on komento se mainitaan, joka sinun täytyy suorittaa._

## Asenna Node.js sopivalle käyttöjärjestelmälle

Node.js on ympäristö, joka voi suorittaa JavaScript-koodia verkkoselaimen ulkopuolella. Gatsby on rakennettu Node.js:llä. Jotta pääset alkuun Gatsbyn kanssa, tietokoneellasi on oltava asennettuna viimeisin versio. npm sisältyy Node.js-pakettiin, joten jos sinulla ei ole npm:tä, on todennäköistä, että sinulla ei ole myöskään Node.js:tä.

### Mac ohjeet

Kun asentaa Gatsbyn ja Node.js:n Macille, on suositeltavaa käyttää [Homebrewiä](https://brew.sh/). Pieni asennus alussa voi pelastaa sinut päänvaivoista myöhemmin!

#### Kuinka asentaa tai varmistaa Homebrew tietokoneellasi:

1. Avaa terminaali.
2. Katso onko Homebrew asennettu. Sinun pitäisi nähdä "Homebrew" ja versionumero.

```shell
brew -v
```

3. Jos ei, lataa ja asenna [Homebrew ohjeiden avulla](https://docs.brew.sh/Installation).
4. Kun olet asentanut Homebrewin, toista vaihe 2 vahvistaaksesi.

#### Asenna Xcode Komentorivityökalut:

1. Avaa terminaali.
2. Asenna Xcode Komentorivityökalut suorittamalla:

```shell
xcode-select --install
```

> 💡 Jos se epäonnistuu, lataa se [suoraan Applen sivulta](https://developer.apple.com/download/more/), kirjautumisen jälkeen Applen kehittäjätilillä.

3. Kun sinua kehotetaan aloittamaan asennus, sinua pyydetään uudestaan hyväksymään ladattavien työkalujen ohjelmistolisenssi.

#### Asenna Node

1. Avaa terminaali.
2. Asenna node Homebrewin avulla:

```shell
brew install node
```

> 💡 Jos et halua asentaa sitä suoraan Homebrewin kautta, lataa uusin Node.js versio [viralliselta Node.js-verkkosivustolta](https://nodejs.org/en/), kaksoisnapsauta ladattua tiedostoa ja käy läpi asennusprosessi.

### Windows ohjeet

- Lataa ja asenna uusin Node.js versio [viralliselta Node.js-verkkosivustolta](https://nodejs.org/en/)

### Linux ohjeet

Asenna nvm (Node Version Manager) ja tarvittavat riippuvuudet. nvm:tä käytetään Node.js:n ja kaikkien siihen liittyvien versioiden hallintaan.

> 💡 Kun asennat pakettia, jos se kysyy vahvistusta, kirjoita `y` ja paina enter.

Valitse distro:

- [Ubuntu, Debian, ja muut apt pohjautuvat distrot](#ubuntu-debian-ja-muut-apt-pohjautuvat-distrot)
- [Arch, Manjaro, ja muut pacman pohjautuvat distrot](#arch-manjaro-ja-muut-pacman-pohjautuvat-distrot)
- [Fedora, RedHat, ja muut dnf pohjautuvat distrot](#fedora-redhat-ja-muutr-dnf-pohjautuvat-distrot)

> 💡 Jos käyttämääsi Linux-jakelua ei ole lueteltu tässä, etsi ohjeita verkosta.

#### Ubuntu, Debian, ja muut `apt` pohjautuvat distrot:

1. Varmista, että Linux-jakelusi on valmis käynnistämään päivityksen ja parannuksen:

```shell
sudo apt update
sudo apt -y upgrade
```

2. Asenna curl, jonka avulla voit siirtää tietoja ja ladata lisäriippuvuuksia:

```shell
sudo apt-get install curl
```

3. Lataa asennuksen jälkeen viimeisin nvm-versio:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

4. Vahvista, että tämä on toiminut. Ulostulon tulee olla versionumero.

```shell
nvm --version
```

5. Jatka kohdasta: [Aseta oletus Node.js-versio](#aseta-oletus-nodejs-versio)

#### Arch, Manjaro, ja muut `pacman` pohjautuvat distrot:

1. Varmista, että jakelusi on valmis käyttöön:

```shell
sudo pacman -Sy
```

2. Nämä distrot on asennettu curl-ohjelmalla, joten voit käyttää sitä nvm:n lataukseen:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

3. Ennen nvm:n käyttöä sinun on asennettava lisäriippuvuudet suorittamalla:

```shell
sudo pacman -S grep awk tar
```

4. Vahvista, että tämä on toiminut. Ulostulon tulee olla versionumero.

```shell
nvm --version
```

5. Jatka kohdasta: [Aseta oletus Node.js-versio](#aseta-oletus-nodejs-versio)

#### Fedora, RedHat, ja muut `dnf` pohjautuvat distrot:

1. Nämä distrot on asennettu curl-ohjelmalla, joten voit käyttää sitä nvm:n lataukseen:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

2. Vahvista, että tämä on toiminut. Ulostulon tulee olla versionumero.

```shell
nvm --version
```

3. Jatka kohdasta: [Aseta oletus Node.js-versio](#aseta-oletus-nodejs-versio)

#### Aseta oletus Node.js-versio

Kun nvm on asennettu, se ei ole oletus tiettyyn node versioon. Sinun on asennettava haluamasi versio ja annettava nvm:lle ohjeet sen käyttämiseksi. Tässä esimerkissä käytetään version 10 julkaisua, mutta sen sijaan voidaan käyttää uudempia versionumeroita.

```shell
nvm install 10
nvm use 10
```

Varmista, että tämä toimi:

```shell
npm --version
node --version
```

Ulostulon tulisi näyttää samanlaiselta kuin alla oleva kuvakaappaus, joka näyttää versionumerot vastauksena komentoihin.

![Tarkista node ja npm-versiot terminaalissa](01-node-npm-versions.png)

Kun olet suorittanut asennusvaiheet ja tarkistanut, että kaikki on asennettu oikein, voit jatkaa seuraavaan vaiheeseen.

## Asenna Git

Git on ilmainen ja avoimen lähdekoodin hajautettu versionhallintajärjestelmä, joka on suunniteltu käsittelemään kaikkea pienistä erittäin suuriin projekteihin nopeudella ja tehokkuudella. Kun asennat Gatsby "aloitussivun", Gatsby käyttää Gitiä kulissien takana ladataksesi ja asenna starterille tarvittavat tiedostot. Sinulla on oltava asennettuna Git asentaaksesi ensimmäisen Gatsby-sivustosi.

Gitin lataus- ja asennusvaiheet riippuvat käyttöjärjestelmästäsi. Seuraa opasta järjestelmällesi:

- [Asenna Git macOSille](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)
- [Asenna Git Windowsille](https://www.atlassian.com/git/tutorials/install-git#windows)
- [Asenna Git Linuxille](https://www.atlassian.com/git/tutorials/install-git#linux)

## Gatsby CLI:n käyttö

Gatsby CLI-työkalun avulla voit luoda nopeasti uusia Gatsby-pohjaisia sivustoja ja suorittaa komentoja Gatsby-sivustojen kehittämiseen. Se on julkaistu npm paketti.

Gatsby CLI on saatavana npm:n kautta, ja se tulisi asentaa globaalisti suorittamalla:

```shell
npm install -g gatsby-cli
```

_**Huom**: Kun asennat Gatsbyn ja käytät sitä ensimmäistä kertaa, näet lyhytsanoman, joka ilmoittaa sinulle nimettömistä käyttötiedoista, joita kerätään Gatsby-komennoille. Voit lukea lisää siitä, kuinka nämä tiedot vedetään ja käytetään [telemetryn dokumentaatiossa](/docs/telemetry)._

Katso käytettävissä olevat komennot:

```shell
gatsby --help
```

![Tarkista gatsby-komennot terminaalissa](05-gatsby-help.png)

> 💡 Jos et pysty suorittamaan Gatsby CLI:tä onnistuneesti käyttöoikeusongelman takia, sinun kannattaa tutustua [npm:n dokumentaatioon oikeuksien korjaamisesta](https://docs.npmjs.com/getting-started/fixing-npm-permissions), tai
[tämä ohje](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md).

## Luo Gatsby-sivusto

Nyt olet valmis käyttämään Gatsby CLI-työkalua ensimmäisen Gatsby-sivustosi luomiseen. Työkalun avulla voit ladata “starter” (osittain rakennettuja sivustoja, joissa on joitain oletusasetuksia), jotta voit siirtyä nopeammin tietyn tyyppisen sivuston luomiseen. Tässä käyttämäsi "Hello World"-alusta on starter, jolla on vain välttämättömät tarpeet Gatsby-sivustolle.

1. Avaa terminaali.
2. Luo uusi sivusto starterista:

```shell
gatsby new hello-world https://github.com/gatsbyjs/gatsby-starter-hello-world
```

> 💡 Mitä juuri tapahtui?
>
> - `Uusi` on gatsby-komento uuden Gatsby-projektin luomiseen.
> - Täällä, `hello-world` on mielivaltainen otsikko — voisit valita minkä tahansa. CLI-työkalu sijoittaa uuden sivustosi koodin uuteen kansioon nimeltä “hello-world”.
> - Viimeiseksi, GitHub URL-osoite osoittaa repolle, joka sisältää haluamasi aloituskoodin.

> 💡 Latausnopeudesta riippuen, tämä aika vaihtelee. Lyhyyden vuoksi alla oleva gif keskeytettiin osan asennuksen aikana.

3. Vaihda toimivaan hakemistoon:

```shell
cd hello-world
```

> 💡 Tämä sanoo _'Haluan vaihtaa hakemiston ("cd") "hello-world" alikansioon'_. Aina kun haluat suorittaa komentoja sivustollesi, sinun on oltava kyseisen sivuston kontekstissa (eli terminaalin on osoitettava hakemistoon, jossa koodisi asuu).

4. Käynnistä kehitystila:

```shell
gatsby develop
```

> 💡 Tämä komento käynnistää kehityspalvelimen. Voit nähdä uuden sivustosi ja olla vuorovaikutuksessa sen kanssa kehitysympäristössä - lokaalisesti (tietokoneellasi, ei julkaistuna internettiin).

<video controls="controls" autoplay="true" loop="true">
  <source type="video/mp4" src="./03-create-site.mp4" />
  <p>Anteeksi! Selaimesi ei tue tätä videota.</p>
</video>

### Katso sivustoasi lokaalisesti

Avaa uusi välilehti selaimessa ja siirry kohtaan `http://localhost:8000/`

![Tarkista kotisivu](04-home-page.png)

Onnittelut! Tämä on ensimmäisen Gatsby-sivustosi alku! 🎉

Voit käydä sivustossa lokaalisti osoitteessa `http://localhost:8000/` niin kauan kuin kehityspalvelimesi on käynnissä. Se on prosessi, jonka aloitit suorittamalla `gatsby develop` komennon. Voit lopettaa prosessin suorittamisen (tai “lopettaa kehityspalvelimen suorittamisen”) palaamalla terminaali-ikkunaan, pitämällä control-näppäintä painettuna ja napsauttamalla sitten “c” (ctrl-c). Käynnistä se uudestaan suorittamalla `gatsby develop` komento uudelleen!

_**Huom:** Jos käytät VM-asetuksia, kuten `vagrant`, ja/tai haluat kuunnella sinun lokaalia IP-osoitettasi, suorita `gatsby develop --host=0.0.0.0`. Nyt kehityspalvelin kuuntelee sekä `http://localhost` että lokaalia IP:tä._

## Pystytä koodieditori

Koodieditori on ohjelma, joka on suunniteltu erityisesti tietokonekoodin muokkaamiseen. Siellä on monia hyviä.

### Lataa VS Code

Gatsbyn dokumentaatio sisältää toisinaan kuvakaappauksia, jotka on otettu VS Codessa, joten jos sinulla ei vielä ole ensisijaista koodieditoria, VS Coden käyttö varmistaa, että näyttösi näyttää täysin samalta kuin tutoriaalin ja dokumenttien kuvakaappaukset. Jos valitset VS Coden, käy [VS Code sivustolla](https://code.visualstudio.com/#alt-downloads) ja lataa käyttöjärjestelmällesi sopiva versio.

### Asenna Prettier plugin

Suosittelemme myös [Prettier](https://github.com/prettier/prettier) työkalun käyttöä, joka auttaa muotoilemaan koodin virheiden välttämiseksi.

Voit käyttää Prettieriä suoraan editorissasi käyttämällä [Prettier VS Code pluginia](https://github.com/prettier/prettier-vscode):

1. Avaa laajennusnäkymä VS Codessa (Näytä => laajennukset).
2. Hae "Prettier - Code formatter".
3. Paina "Asenna". (Asennuksen jälkeen sinua kehotetaan käynnistämään VS Code uudelleen laajennuksen sallimiseksi. VS Coden uudemmat versiot aktivoivat laajennuksen automaattisesti lataamisen jälkeen.)

> 💡 Jos et käytä VS Codea, katso Prettierin [asennusohjeen](https://prettier.io/docs/en/install.html) tai [muiden editorien integroinnin](https://prettier.io/docs/en/editors.html) dokumentaatio.

## ➡️ Mitä seuraavaksi?

Lyhyesti, tässä osiossa sinä:

- Opit komentorivistä ja kuinka sitä käytetään
- Asensit ja opit Node.js:ää ja npm CLI-työkalusta, versionhallintajärjestelmä Gitin ja Gatsby CLI-työkalun
- Luoit uuden Gatsby-sivuston Gatsby CLI-työkalun avulla
- Suoritit Gatsby-kehityspalvelimen ja vierailit sivustollasi lokaalisti
- Latasit koodieditorin
- Asensit Prettier-nimisen koodimuotoilijan

Nyt siirry kohtaan [**tutustuminen Gatsbyn rakennuspalikoihin**](/tutorial/part-one/).

## Viitteet

### Yleiskatsaus ydinteknologioihin

Ei ole välttämätöntä olla asiantuntija näissä jo — jos et ole, älä huoli! Keräät paljon tietoa tämän tutoriaalisarjan aikana. Nämä ovat tärkeimmistä verkkotekniikoista, joita käytät rakentaessasi Gatsby-sivustoa:

- **HTML**: Merkintäkieli, jonka jokainen selain pystyy ymmärtämään. Se tarkoittaa HyperText Markup Language. HTML antaa verkkosisällöllesi universaalin informaatiorakenteen, joka määrittelee esimerkiksi otsikot, kappaleet ja muut.
- **CSS**: Esityskieli, jota käytetään verkkosisällön (kirjasimet, värit, asettelu jne.) ulkoasun muotoiluun. Se tarkoittaa Cascading Style Sheets.
- **JavaScript**: Ohjelmointikieli, joka auttaa meitä tekemään verkosta dynaamisen ja vuorovaikutteisen.
- **React**: Koodikirjasto (rakennettu JavaScriptillä) käyttöliittymien rakentamiseen. Se on framework, jota Gatsby käyttää sivujen rakentamiseen ja sisällön rakentamiseen.
- **GraphQL**: Kyselykieli, jonka avulla voit vetää tietoja verkkosivustollesi. Se on käyttöliittymä, jota Gatsby käyttää sivustotietojen hallintaan.

### Mikä on verkkosivusto?

Katsaus verkkosivuston kattavaan esittelyyn - mukaan lukien HTML- ja CSS-esittely -- tarkista “[**Ensimmäisen verkkosivustosi rakentaminen**](https://learn.shayhowe.com/html-css/building-your-first-web-page/)”. Se on hyvä paikka aloittaa oppimisen verkosta. Lisätietoja enemmän käytännöllisestä johdannosta [**HTML**](https://www.codecademy.com/learn/learn-html), [**CSS**](https://www.codecademy.com/learn/learn-css), ja [**JavaScript**](https://www.codecademy.com/learn/introduction-to-javascript), tarkista tutoriaalit Codecademystä. [**Reactillä**](https://reactjs.org/tutorial/tutorial.html) ja [**GraphQL:lä**](https://graphql.org/graphql-js/) on myös omat johdanto tutoriaalit.

### Opi lisää komentorivistä

Hyvään johdantoon komentorivin käyttöön, tarkista [**Codecademyn komentorivi tutoriaali**](https://www.codecademy.com/courses/learn-the-command-line/lessons/navigation/exercises/your-first-command) Mac ja Linux käyttäjille, ja [**tämä tutoriaali**](https://www.computerhope.com/issues/chusedos.htm) Windows käyttäjille. Vaikka olet Windowsin käyttäjä, Codecademy tutoriaalin ensimmäinen sivu on arvokas lukea. Se selittää komentorivin, ei vain miten interface sen kanssa.

### Opi lisää npm:stä

npm on JavaScript-paketinhallinta. Paketti on koodimoduuli, jonka voit valita sisällyttävän projektiisi. Jos olet juuri ladannut ja asentanut Node.js:n, npm asennettiin sen mukana!

npm:llä on kolme erillistä komponenttia: npm sivusto, npm rekisteri, ja npm komentoriviliittymä (CLI).

- npm verkkosivustolla voit selata, mitä JavaScript-paketteja on saatavilla npm rekisterissä.
- npm rekisteri on suuri tietokanta JavaScript-paketeista, jotka ovat saatavilla npm:ssä.
- Kun olet tunnistanut haluamasi paketin, voit käyttää npm CLI:tä asentaaksesi sen projektiisi tai globaalisti (kuten muutkin CLI-työkalut). npm CLI on se, mikä puhuu rekisterille - olet yleensä vuorovaikutuksessa vain
npm verkkosivuston tai npm CLI:n kanssa.

> 💡 Tarkista npm:n johdanto, “[**Mikä on npm?**](https://docs.npmjs.com/getting-started/what-is-npm)”.

### Opi lisää Gitistä

Sinun ei tarvitse tietää Gitiä saada valmiiksi tätä tutoriaalia, mutta se on erittäin hyödyllinen työkalu. Jos olet kiinnostunut oppimaan lisää versionhallinnasta, Gitistä ja GitHubista, tarkista GitHubin [Git Käsikirja](https://guides.github.com/introduction/git-handbook/).
