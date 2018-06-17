# Documentation


## Convention BEM
* B -> Block
* E -> Element
* M -> Modifier

```HTML
<!-- __mainList = Block-->
<ul class="mainList mainList-xmas">
  <!-- __item = Element-->
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink mainList__itemLink--isActive"href="/home">Home</a>
  </li>
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink"href="/home">About</a>
  </li>
  <li class="mainList__item">
    <!-- __itemLink = Element-->
    <a class="mainList__itemLink"href="/home">Works</a>
  </li>
</ul>
```


## Pseudo attributs

Les pseudo attributs `before` et `after` permettent de créer des noeux HTML et CSS.
Ils sont généralement utiliser pour ajouter des ornements, des décorations ... On
peut bien entendu faire des animations avec, les positionner par rapport à leurs
parents (relative / absolute) **Ils doivent obligatoirement avoir un `content: ''`**
afin de s'afficher.

```HTML
<section>
  <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
</section>
```
```CSS
.cover {
  background: #FDFDFD;
  padding: 20px;
  &__mainTitle {
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;
    &::before,
    &::after {
      position: absolute;
      content: '';
      width: 50px;
      height: 50px;
      background: green;
    }
    &::before {
    left : 0;
    }
    &::after {
      right: 0;
    }
  }
}
```

## REM, EM, %, VW Sizing

### %

### EM

```CSS
.cover {
  font-size: 100%; /* 100% = 16px */
  &__mainTitle {
    /* 1.6em === 16px */
    font-size: 1.6em;
    /* 32rem === 320px */
    width: 32rem;
  }
}
```

### REM

* Le REm est basé sur la taille de la racine (soit la balise <html>) qui, par
défaut à une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire de
l'écraser  en donnant une base de 10px soit 62,5%.
* Le REM est intéraissant à utiliser si les media-queries emplyées sont en REM
également. Cela vous permettra de garder des proportions égales lorsqu'on va
redimensionner la page.
* Ses proportions seront également gardées quand l'utilisateur zoomera dans
votre page.

```CSS
html 
  font-size: 62,5%;
}
```

### VW(idth) / VH(eight)

* Unités relatives à la taille de votre écran (peu importe le device)
* Attention au VH et à son contenu. 100vh === 100vh quoi qu'il arrive
* VW : très utile pour les interfaces fluides.

### Display 

```CSS
Display: flex;
Justify-content: center // Centre horizontal
Justify-content: flex-end // Start à la fin
Justify-content: flex-wrap // Aide au responsive img
Justify-content: space-between // Colle à droiteGauche
Justify-content: space-arround // Stylé
text-align: center // Centre texte horizontal
align-item: center // Centre vertical
```

```CSS
Display: none; // invisible 
Display: block; // en block
```

## Les MédiasQueries
Emples de MediaQueries, qui servent au responsive (Mode desktop / tablette / phone). C'est à nous de définir quand on veut changer de mode.

```CSS
@media all and (max-device-width: 480px) {
}
@media screen and (max-width: 640px) {
}
@media screen and (min-width: 200px) and (max-width: 640px) {
}
```

## SCSS

Création d'une variable à réutiliser n'importe ou :

```CSS
$mainColor : blue;
```
Exemple de SCSS : 

```CSS
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;
  }
  &__item {
    list-style: none;
  }
  &__itemLink {
    color: red;
    &--isActive {
      color: white;
    }
  }
}
```

## Liens utiles :

* [Caniuse](https://caniuse.com/) : "c'est compatible partout ou pas?"
* [FrontEndQuizz](https://github.com/h5bp/Front-end-Developer-Interview-Questions)
* [CssNext](http://cssnext.io/)
* [MDN web docs](https://developer.mozilla.org/fr/)

## Flexbox Grid

* Télécharger [flexboxgrid](http://flexboxgrid.com/) et mettre dans un dossier (.min.css) css avec le style.

* **Ne jamais utilisé de margin ou padding sur les class="col-xxx" quand on utilise une grille**

* col-xs > desktop / col-sm > tablette / col-lg > téléphone etc.
* offset permet de "sauter" des collonnes.

```html
<div class="container">
<div class="row">

<div class="col-xs-6 col-lg-4" >
<h2> Titre 1</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus fugit eligendi quo quia praesentium. Nam facere, est modi enim corporis perspiciatis, provident cumque.</p>
</div>

<div class="col-xs-6 col-lg-4">
<h2>Titre 2</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore ad provident molestiae reprehenderit explicabo aliquid atque incidunt unde amet.</p>
</div>

<div class="col-xs-6 col-lg-4">
<h2>Titre 3</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum rerum eum, quae voluptatum omnis aut eligendi, placeat ullam suscipit!</p>
</div>

<div class="col-xs-6 col-lg-6">
<h2>Titre 4</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Perferendis, eos aliquam sed quas optio porro architecto doloribus dicta. Rem voluptatibus corporis, molestias eos atque, sint!</p>
</div>

<div class="col-xs-12 col-lg-5 col-lg-offset-1">
<h1>Titre 5</h1>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt error hic, autem sapiente delectus magni expedita. Eveniet blanditiis quod provident.</p>
</div>

</div>
</div>
```
## Installer parcel

* Installer node.js et homebrew
* Aller dans un dossier de développement
* mkdir parcel-boilerplate
* cd parcel-boilerplate
* npm -v
* npm init > name = parcel-boilerplate > author = Simon
* ll
* sudo npm install -g parcel-bundler
**installer yarn si sa marche pas**
* touch index.html index.js
➜  parcel-boilerplate git:(master) ✗ mkdir styles
➜  parcel-boilerplate git:(master) ✗ cd styles
➜  styles git:(master) ✗ touch styles.scss
➜  styles git:(master) ✗ ll
total 0
-rw-r--r--  1 simonsoleau  staff     0B 27 fév 14:38 styles.scss
➜  styles git:(master) ✗ cd ..
➜  parcel-boilerplate git:(master) ✗ ll
* yarn OU npm install
* yarn start OU npm start
* cd styles
* mkdir global && mkdir components && mkdir mixins
* cd global
* touch _variables.scss && touch _reset.scss
* touch mixins/_forsize.scss
* ➜  global git:(master) ✗ cd ..
➜  styles git:(master) ✗ touch mixins/_forsize.scss
➜  styles git:(master) ✗ touch components/_header.scss
➜  styles git:(master) ✗ touch global/_reset.scss
➜  styles git:(master) ✗ touch global/_variables.scss
* touch .postcssrc
* npm install auto prefixer(Pour les npm)
* yarn add autoprefixer (Pour Yarn)
* dans postcssrc > mettre 
{
  "plugins": {
    "autoprefixer": {
      "browsers": [">1%", "last 4 versions", "Firefox ESR", "not ie < 9"],
      "flexbox": "no-2009",
      "grid": true
    }
  }
}
* touch .babelrc
* Pour npm > nmp install -D babel-preset-env OU yarn add -d babel-preset-env
{
  "presets": [
     ["env", {
      "targets": {
        "browsers": ["last 2 versions", "safari >= 7"]
      }
    }]]
}
* test si ça marche
* mkdir src, mv styles src / index.js src / index.html src et changer package.json main/ start / build et y mettre src
* 

## MEDIA 

Les médias servent à rendre un site responsive plus proprement.

```CSS
.Exemple {
display: flex;
	@media screen and (max-width: 1024px) {
	}
}

```


# PHP

php -S localhost:8000 démare un serveur php

* Mettre composer : 
git init
composer init
composer dump-autoload (A refaire à chaque changement du composer)



#Liens et trucs utiles
* [Caniuse](https://caniuse.com/) : "c'est compatible partout ou pas?"
* [FrontEndQuizz](https://github.com/h5bp/Front-end-Developer-Interview-Questions)
* [CssNext](http://cssnext.io/)
* [MDN web docs](https://developer.mozilla.org/fr/)
* [Firebase](https://firebase.google.com/)
* [Doc Vu.JS](https://github.com/vuejs/awesome-vue)
* [MédiaQueries](https://www.alsacreations.com/article/lire/930-css3-media-queries.html)
* [helpAjax](https://openclassrooms.com/courses/ajax-et-l-echange-de-donnees-en-javascript)

## Github
git init
touch .gitignore (On met dedans ce que l'on veut ignorer)
git status
git add .
git commit -m "Mon message"

rm -rf .git remove git

* https://github.com/h5bp/Front-end-Developer-Interview-Questions

* ImageOption réduit l'image au maximum

* http://cssnext.io/


Récupérer un repositories :
* git clone https://lien-du-repo.git

Linker son dossier de travail à un répo GitHub :
* git remote add origin (url du github)

**Travailler sur le master est déconseillé, voir interdit selon les projets pour cela utiliser les branchs :**

* git checkout -b (nom de la branch) : créer une nouvelle branch
* git checkout (nom de la branch) : changer de branch

Push un projet sur GitHub :

* git add .
* git commit -m "message"
* git push origin (nom de la branch )

Pull un projet de GitHub :

* git pull origin (nom de la branch)

## FORK

On fork le repo d'une autre personne, le repo va alors aller sur notre compte. 
Quand on a fini, on fait un pull request sur le compte du copain.


# MYSQL

```mysql
create table `kandt-pages`.`pages-content`(
`id` INT UNSIGNED NOT NULL AUTO_INCREMENT,
  `page`       varchar(110),
  `title`      varchar(70),
  `h1`         varchar(3000),
  `p`          varchar(100),
  `span-class` varchar(50),
  `span-text`  varchar(100),
  `img-alt`    varchar(2048),
  `img-src`    varchar(30),
  `nav-title`  varchar(100),
  primary key (`page`)
);
```

mysql.server start --skip-grand-tables (Mode YOLO)

## SEO
### Nombre de charactères pour optimisation seo
Page
___
* **Titre** VARCHAR(110)
* **H1** VARCHAR(70)
* **Paragraphe** VARCHAR(3000)
* **Span-Class** VARCHAR(100)
* **Span-Text** VARCHAR(50)
* **Img-Alt** VARCHAR(100) (min 70)
* **Img-Source** VARCHAR(2048)
* **Nav-Title** VARCHAR(30)
* **Slug** VARCHAR(100)

___


# A DL en cas de changement d'ordi

craftmanager
php
SASS
brew install php70 > pour upgrade une version php sur son ordinateur.
Xcode 
Ajax
Homebrew
Mysql / Workbenche
Node.js

# Homebrew 
* Brew doctor


# Wordpress 
* Importation de base de donnée : mysql -u USER -pMOT_DE_PASSE BDD < CHEMIN_DU_FICHIER.SQL
* Exportation de base de donnée : Se mettre dans le fichier où l'on veut exporter puis mysql -u USER -pMOT_DE_PASSE BDD > bdd.SQL

## Changer URL
Exemple :
UPDATE cest_pas_faux_options SET option_value = replace(option_value, 'http://localhost:81/kaamelot', 'http://localhost:8000') WHERE option_name = 'home' OR option_name = 'siteurl';

Aller dans MYSQL puis entrer dans une base de donnée.
Mettez le nom d'une tables, ici cest_pas_faux (Que l'on trouve sur Wordpress wp_config $table_prefix.

http://localhost:81/kaamelot est l'url du site, la nouvelle

http://localhost:8000 là ou on veut le mettre


# JS
* Empeche un form de refresh

```JS
function(envent) {
event.preventDefaukt
}
```
* Data.js pour faire une bibliothèque

* DeltaY permet de voir le scroll + wheel

```JS
window.addEventListener('wheel', function(event)
```
