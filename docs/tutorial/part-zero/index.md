---
title: Asenna sinun kehitysympäristö
typora-copy-images-to: ./
disableTableOfContents: true
---

Ennen kuin aloitat sinun ensimmäisen Gatsby-sivuston rakentamisen, sinun on perehdyttävä joihinkin ydin web-teknologioihin ja varmistettava, että olet asentanut kaikki vaadittavat ohjelmistotyökalut.

## Tutustu komentoriviin

Komentorivi on tekstipohjainen käyttöliittymä, jota käytetään komentojen suorittamiseen tietokoneellasi. Saatat myös nähdä, että sitä kutsutaan terminaaliksi. Käytämme tässä tutoriaalissa molempia keskenään vaihtokelpoisesti.
Se on paljon kuin Finderin käyttö Macissa tai Resurssienhallinta Windowsissa. Finder ja Explorer ovat esimerkkejä graafisista käyttöliittymistä (GUI). Komentorivi on tehokas, tekstipohjainen tapa olla vuorovaikutuksessa tietokoneesi kanssa.

_**Huom:** Kaikki ohjeet ovat englanniksi._

Käytä hetki etsiäksesi ja avataksesi komentoriviliittymä (CLI) tietokoneellesi. Riippuen mitä käyttöjärjestelmää käytät, katso [**ohjeet Macille**](http://www.macworld.co.uk/feature/mac-software/how-use-terminal-on-mac-3608274/), [**ohjeet Windowsille**](https://www.lifewire.com/how-to-open-command-prompt-2618089) tai [**ohjeet Linuxille**](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/).

_**Huom:** Jos olet uusi komentoriville, "käynnissä" komento, tarkoittaa "kirjoittamalla annetut ohjeet komentokehotteessasi, ja painamalla Enter-näppäintä". Komennot näytetään korostettuna ruudussa, jotakuinkin `node --version`, but kaikki korostetut ruudut eivät ole komentoja! Jos jokin on komento se mainitaan, joka sinun täytyy suorittaa._

## Asenna Node.js sopivalle käyttöjärjestelmällesi

Node.js on ympäristö, joka voi suorittaa JavaScript-koodia verkkoselaimen ulkopuolella. Gatsby on rakennettu Node.js:llä. Jotta pääset alkuun Gatsbyn kanssa, tietokoneellasi on oltava asennettuna viimeisin versio. npm sisältyy Node.js-pakettiin, joten jos sinulla ei ole npm:tä, on todennäköistä, että sinulla ei ole myöskään Node.js:tä.

### Mac ohjeet

Kun asentaa Gatsbyn ja Node.js:n Macille, on suositeltavaa käyttää [Homebrewiä](https://brew.sh/). Pieni asennus alussa voi pelastaa sinut päänvaivoista myöhemmin!

#### Kuinka asentaa tai varmistaa Homebrewin tietokoneellasi:

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

> 💡 If the Linux distribution you are using is not listed here, please find instructions on the web.

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

1. Varmista, että jakelusi on valmis menemään:

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

When nvm is installed, it does not default to a particular node version. You’ll need to install the version you want and give nvm instructions to use it. This example uses the version 10 release, but more recent version numbers can be used instead.

```shell
nvm install 10
nvm use 10
```

Confirm that this worked:

```shell
npm --version
node --version
```

The output should look similar to the screenshot below, showing version numbers in response to the commands.

![Check node and npm versions in terminal](01-node-npm-versions.png)

Once you have followed the installation steps and you have checked everything is installed properly, you can continue to the next step.

## Install Git

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. When you install a Gatsby "starter" site, Gatsby uses Git behind the scenes to download and install the required files for your starter. You will need to have Git installed to set up your first Gatsby site.

The steps to download and install Git depend on your operating system. Follow the guide for your system:

- [Install Git on macOS](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)
- [Install Git on Windows](https://www.atlassian.com/git/tutorials/install-git#windows)
- [Install Git on Linux](https://www.atlassian.com/git/tutorials/install-git#linux)

## Using the Gatsby CLI

The Gatsby CLI tool lets you quickly create new Gatsby-powered sites and run commands for developing Gatsby sites. It is a published npm package.

The Gatsby CLI is available via npm and should be installed globally by running:

```shell
npm install -g gatsby-cli
```

_**Note**: when you install Gatsby and run it for the first time, you'll see a short message notifying you about anonymous usage data that is being collected for Gatsby commands, you can read more about how that data is pulled out and used in the [telemetry doc](/docs/telemetry)._

See the available commands:

```shell
gatsby --help
```

![Check gatsby commands in terminal](05-gatsby-help.png)

> 💡 If you are unable to successfully run the Gatsby CLI due to a permissions issue, you may want to check out the [npm docs on fixing permissions](https://docs.npmjs.com/getting-started/fixing-npm-permissions), or [this guide](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md).

## Create a Gatsby site

Now you are ready to use the Gatsby CLI tool to create your first Gatsby site. Using the tool, you can download “starters” (partially built sites with some default configuration) to help you get moving faster on creating a certain type of site. The “Hello World” starter you’ll be using here is a starter with the bare essentials needed for a Gatsby site.

1. Open up your terminal.
2. Create a new site from a starter:

```shell
gatsby new hello-world https://github.com/gatsbyjs/gatsby-starter-hello-world
```

> 💡 What just happened?
>
> - `new` is a gatsby command to create a new Gatsby project.
> - Here, `hello-world` is an arbitrary title — you could pick anything. The CLI tool will place the code for your new site in a new folder called “hello-world”.
> - Lastly, the GitHub URL specified points to a code repository that holds the starter code you want to use.

> 💡 Depending on your download speed, the amount of time this takes will vary. For brevity's sake, the gif below was paused during part of the install

3. Change into the working directory:

```shell
cd hello-world
```

> 💡 This says _'I want to change directories (`cd`) to the “hello-world” subfolder'_. Whenever you want to run any commands for your site, you need to be in the context for that site (aka, your terminal needs to be pointed at the directory where your site code lives).

4. Start the development mode:

```shell
gatsby develop
```

> 💡 This command starts a development server. You will be able to see and interact with your new site in a development environment — local (on your computer, not published to the internet).

<video controls="controls" autoplay="true" loop="true">
  <source type="video/mp4" src="./03-create-site.mp4" />
  <p>Sorry! Your browser doesn't support this video.</p>
</video>

### View your site locally

Open up a new tab in your browser and navigate to `http://localhost:8000/`

![Check homepage](04-home-page.png)

Congrats! This is the beginning of your very first Gatsby site! 🎉

You’ll be able to visit the site locally at `http://localhost:8000/` for as long as your development server is running. That’s the process you started by running the `gatsby develop` command. To stop running that process (or to “stop running the development server”), go back to your terminal window, hold down the “control” key, and then hit “c” (ctrl-c). To start it again, run `gatsby develop` again!

_**Note:** If you are using VM setup like `vagrant` and/or would like to listen on your local IP address, run `gatsby develop --host=0.0.0.0`. Now, the development server listens on both `http://localhost` and your local IP._

## Set up a code editor

A code editor is a program designed specifically for editing computer code. There are many great ones out there.

### Download VS Code

Gatsby documentation sometimes includes screenshots that were taken in VS Code, so if you don't have a preferred code editor yet, using VS Code will make sure that your screen looks just like the screenshots in the tutorial and docs. If you choose to use VS Code, visit the [VS Code site](https://code.visualstudio.com/#alt-downloads) and download the version appropriate for your platform.

### Install the Prettier plugin

We also recommend using [Prettier](https://github.com/prettier/prettier), a tool that helps format your code to avoid errors.

You can use Prettier directly in your editor using the [Prettier VS Code plugin](https://github.com/prettier/prettier-vscode):

1. Open the extensions view on VS Code (View => Extensions).
2. Search for "Prettier - Code formatter".
3. Click "Install". (After installation, you'll be prompted to restart VS Code to enable the extension. Newer versions of VS Code will automatically enable the extension after download.)

> 💡 If you're not using VS Code, check out the Prettier docs for [install instructions](https://prettier.io/docs/en/install.html) or [other editor integrations](https://prettier.io/docs/en/editors.html).

## ➡️ What’s Next?

To summarize, in this section you:

- Learned about the command line and how to use it
- Installed and learned about Node.js and the npm CLI tool, the version control system Git, and the Gatsby CLI tool
- Generated a new Gatsby site using the Gatsby CLI tool
- Ran the Gatsby development server and visited your site locally
- Downloaded a code editor
- Installed a code formatter called Prettier

Now, move on to [**getting to know Gatsby building blocks**](/tutorial/part-one/).

## References

### Overview of core technologies

It’s not necessary to be an expert with these already — if you’re not, don’t worry! You’ll pick up a lot through the course of this tutorial series. These are some of the main web technologies you’ll use when building a Gatsby site:

- **HTML**: A markup language that every web browser is able to understand. It stands for HyperText Markup Language. HTML gives your web content a universal informational structure, defining things like headings, paragraphs, and more.
- **CSS**: A presentational language used to style the appearance of your web content (fonts, colors, layout, etc). It stands for Cascading Style Sheets.
- **JavaScript**: A programming language that helps us make the web dynamic and interactive.
- **React**: A code library (built with JavaScript) for building user interfaces. It’s the framework that Gatsby uses to build pages and structure content.
- **GraphQL**: A query language that allows you to pull data into your website. It’s the interface that Gatsby uses for managing site data.

### What is a website?

For a comprehensive introduction to what a website is -- including an intro to HTML and CSS -- check out “[**Building your first web page**](https://learn.shayhowe.com/html-css/building-your-first-web-page/)”. It’s a great place to start learning about the web. For a more hands-on introduction to [**HTML**](https://www.codecademy.com/learn/learn-html), [**CSS**](https://www.codecademy.com/learn/learn-css), and [**JavaScript**](https://www.codecademy.com/learn/introduction-to-javascript), check out the tutorials from Codecademy. [**React**](https://reactjs.org/tutorial/tutorial.html) and [**GraphQL**](https://graphql.org/graphql-js/) also have their own introductory tutorials.

### Learn more about the command line

For a great introduction to using the command line, check out [**Codecademy’s Command Line tutorial**](https://www.codecademy.com/courses/learn-the-command-line/lessons/navigation/exercises/your-first-command) for Mac and Linux users, and [**this tutorial**](https://www.computerhope.com/issues/chusedos.htm) for Windows users. Even if you are a Windows user, the first page of the Codecademy tutorial is a valuable read. It explains what the command line is, not just how to interface with it.

### Learn more about npm

npm is a JavaScript package manager. A package is a module of code that you can choose to include in your projects. If you just downloaded and installed Node.js, npm was installed with it!

npm has three distinct components: the npm website, the npm registry, and the npm command line interface (CLI).

- On the npm website, you can browse what JavaScript packages are available in the npm registry.
- The npm registry is a large database of information about JavaScript packages available on npm.
- Once you’ve identified a package you want, you can use the npm CLI to install it in your project or globally (like other CLI tools). The npm CLI is what talks to the registry — you generally only interact with the npm website or the npm CLI.

> 💡 Check out npm’s introduction, “[**What is npm?**](https://docs.npmjs.com/getting-started/what-is-npm)”.

### Learn more about Git

You will not need to know Git to complete this tutorial, but it is a very useful tool. If you are interested in learning more about version control, Git, and GitHub, check out GitHub's [Git Handbook](https://guides.github.com/introduction/git-handbook/).
