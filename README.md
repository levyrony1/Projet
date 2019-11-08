# Collaborer sur des projets avec Git & Github

<!-- TOC START min:2 max:3 link:true asterisk:true update:true -->
* [Ce que vous apprendrez durant ce cours](#ce-que-vous-apprendrez-durant-ce-cours)
* [Git & Github](#git--github)
  * [Qu’est ce que Git et le VCS ?](#quest-ce-que-git-et-le-vcs-)
  * [Et Github ?](#et-github-)
  * [Utiliser Git sur le Terminal pour vos projets](#utiliser-git-sur-le-terminal-pour-vos-projets)
  * [Bien écrire son fichier README.md](#bien-écrire-son-fichier-readmemd)
* [La gestion de projets Agile](#la-gestion-de-projets-agile)
  * [Agile VS Waterfall](#agile-vs-waterfall)
  * [La méthode SCRUM](#la-méthode-scrum)
* [Ressources](#ressources)
<!-- TOC END -->

## Ce que vous apprendrez durant ce cours

A mesure que vous allez grandir en tant que développeur, vous allez devoir collaborer sur des projets. Ecrire du code ensemble sur un même projet peut être très simple comme cauchemardesque si on ne sait pas comment s’y prendre. Ce cours est justement ici pour vous apprendre comment développer en équipe. Après le cours, vous saurez :

*   Comprendre ce qu’est le Version Control System (VCS)
*   Utiliser Git avec le terminal et poster votre code sur Github
*   Utiliser des branches et faire des commits et des pull requests
*   Collaborer sur un projet de développement via la méthode agile


## Git & Github


### Qu’est ce que Git et le VCS ?

Lorsque l’on code un projet, il arrive qu’on ait plusieurs versions à faire celui-ci. Par exemple, vous avez un premier fichier :


```
monprojet.py
```


Puis, vous décidez d’améliorer le projet, du coup vous avez créé une copie de ce fichier que vous avez appelé


```
monprojet_V2.py
```


Et puis, il est possible que vous ayez une troisième version du projet et que vous ayez fait une nouvelle copie de votre fichier etc. Vous pouvez continuer ainsi pendant encore un peu de temps de cette manière mais à mesure que votre projet devient de plus en plus complexe, vous aurez du mal à maintenir tout ceci en ordre.

C’est ce à quoi sert un VCS ou Version Control System. Grâce à ce système, vous allez pouvoir de manière automatique et serenne créer des versions de vos projets sans perdre ou casse le code initial.

Parmi ces VCS, on compte Git qui est le plus populaire et le plus utilisé de tous. Nous allons donc apprendre à l’utiliser afin de travailler sur projets complexes.


### Et Github ?


#### Qu’est ce que c’est ?

Une fois que vous avez un VCS et que vous l’utilisez, c’est très bien mais, il y a encore plus puissant. Imaginez que vous n’ayez même plus à échanger vos fichiers de machine en machine entre collaborateurs mais que vous pouvez tout mettre dans le cloud afin que toutes les personnes autorisées aient accès aux ressources à n’importe quelle heure. C’est le principe de Github.


Grâce à cette outil, vous pourrez créer ce qu’on appelle des “dépôts” et y déposer vos projets, interagir avec toutes les personnes qui collaborent sur le projets et déployer vos projets.


Dans Github, on peut avoir un profil (vous même) et ce profil peut faire partie d’une organisation (ex : Jedha). Expliquons un peu les deux.


#### Votre profil

De la même manière que dans tous réseaux sociaux, pour accéder à Github, il faut que vous ayez un profil. Pour ce faire, rien de plus simple. Il vous suffira d’aller sur [github.com](https://github.com/) et d’entrer :

1. Un nom d’utilisateur github
2. Un email
3. Un mot de passe

Une fois que vous avez tout ca, vous pouvez commencer à utiliser l’outil.

Vous verrez que sur votre profil, vous pourrez voir :

*   Les dépôts que vous avez
*   Les dépôts que vous suivez via les _stars_
*   Votre nombre de followers
*   Le nombre de gens que vous suivez

Si vous avez besoin de paramétrer quoique ce soit sur votre compte, il suffira d’aller à droite de la barre de navigation, cliquer sur votre avatar et un menu dropdown devrait apparaître dans lequel vous pourrez voir les paramètres du compte (ou _settings_ en anglais)


#### Faire partie d’une organisation

Si vous êtes dans une entreprise tech, il est fortement probable que cette entreprise ait une “page” sur Github. Au lieu de l’appeler “Page”, on l’appelle en fait organisation. Cela sert à créer des équipes de personnes qui travaillent sur des projets commun.

Avec une organisation, vous pouvez créer des dépôts propres à elle, gérer les personnes qui ont accès aux dépôts et manager des projets d’équipe. C’est très utile de créer une organisation ou de faire partie de l’une d’entre elle si vous êtes amené à travailler avec beaucoup de personnes sur le projet. Au fur et à mesure que nous allons utiliser Git & Github, vous allez mieux comprendre comment tout ceci fonctionne. Alors entrons maintenant dans le vif du sujet.


### Utiliser Git sur le Terminal pour vos projets

Entrons maintenant dans le dur et apprenons comment se servir de Git et de Github pour des projets complexes.

[https://guides.github.com/activities/hello-world/](https://guides.github.com/activities/hello-world/)

#### Télécharger Git

Tout d’abord, il faudra télécharger Git sur votre machine pour que vous puissiez utiliser les commandes sur votre console. Pour ce faire, il faudra aller sur ce lien  :

[https://git-scm.com/downloads](https://git-scm.com/downloads)

Sélectionnez le système d’exploitation qui correspond à celui de votre ordinateur et hop, quelques minutes plus tard, git sera installé sur votre ordinateur.


#### Paramétrer votre username et email

Une dernière chose à vérifier avant de commencer à coder est de voir si votre git est bien configuré au bon nom d’utilisateur et au bon email.

Ouvrez donc votre console et entrez la commande suivante :


```
git config --global user.name
```


Si votre nom d’utilisateur qui apparaît est le bon, très bien. Si vous devez le changer, il vous suffit de faire


```
git config --global user.name "votre nom"
```


Vous devrez ensuite faire de même avec votre email. Le processus est le même, vous devrez simplement remplacer `.name` par `.email` de la façon suivante :


```
git config --global user.email
```


Ceci va permettre à git d’associer votre nom et votre email aux contributions que vous allez faire dans le code. ATTENTION, le nom d’utilisateur sur git est différent de celui sur Github. Ce n’est pas parce que vous avez un nom d’utilisateur A sur git que ce sera le même sur Github.


#### Créer un dépôt sur Github

Venons en maintenant à l’outil principal de Github : _le dépôt_ (_repository_ en anglais). Un dépôt est un dossier dans lequel vous pourrez mettre tous vos fichiers et les stocker dans le cloud afin que d’autres personnes puissent collaborer dessus. Voyons donc comment on peut créer un dépôt



1. Dans la barre de navigation de Github, vous verrez un signe +, cliquez dessus, vous pourrez voir que vous pouvez créer un nouveau dépôt
2. Donnez un nom à votre dépôt
3. Vous pouvez aussi donner une description à votre dépôt pour donner plus de détails sur le but de ce dépôt
4. Choisissez ensuite si le dépôt devra être public, c’est à dire visible par tous ou alors privée. ATTENTION, avoir des dépôts privés n’est pas gratuit cependant.
5. Initialiser un fichier README.md, un gitignore et un type de licence si besoin. Nous développerons plus tard ces points dans le cours.

Une fois que vous avez créé le dépôt, nous allons exporter le code que vous avez créé en local


#### Faire un premier commit


##### Qu’est ce qu’un commit

Pour l’instant, notre dépôt est vide. Pour ajouter du contenu dans dépôt, il faut faire ce que l’on appelle un _commit_. C’est à dire une sauvegarde de nos fichiers à un instant-T. Voyons donc comment faire :


##### Créer un dossier en local

Tout d’abord, il créer un dossier en local dans lequel, nous aurons le code que nous voulons mettre dans notre dépôt Github. Pour cela, rien de plus simple, allez dans votre console, sélectionnez un emplacement pour votre dossier puis créez le dossier. Pour rappel :

Se déplacer dans la console : `cd`

Créer un dossier : `mkdir`

Une fois que vous êtes dans votre dossier, vous devrez initialiser git via la commande suivante :


```
git init
```


Cette commande va initialiser git dans le dossier dans lequel vous vous trouvez.

Une fois que vous avez fait cette étape, vous pouvez regarder ce qui a été exporté ou qui est encore seulement en local dans votre machine via :


```
git status
```


Prenons un exemple :


```
git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

README.md

nothing added to commit but untracked files present (use "git add" to track)
```


Ici, nous pouvons voir que nous sommes sur la branche _master_ et que nous n’avons encore jamais fait aucun commit et que nous avons un fichier que git ne traque pas, qui est : README.md


##### Ajouter un fichier dans un commit

Pour pouvoir faire notre premier commit, il faudra donc faire :


```
git add nom_du_fichier
```


Dans notre exemple :


```
git add README.md
```


Si vous retapez : _git status, _vous verrez que maintenant le fichier _README.md_ apparaît en vert. C’est à dire qu’il est prêt à être exporté. Si vous remodifiez le fichier, il réapparaitra en rouge et vous devrez refaire un _git add_


##### Créer le commit

Une fois ceci fait, vous n’avez plus qu’à faire votre commit via la commande suivante :


```
git commit -m "nom_de_votre_commit"
```


Vous devez forcément donner un nom à votre commit. Celui-ci doit être court et doit expliquer clairement ce que vous avez fait dans votre code.

Exemple :


```
git commit -m "ajout de README.md"
```



##### Exporter sur Github

Pour terminer et tout exporter sur github, vous devrez ajouter ce qu’on appelle une _remote_ qui permet à git de savoir où exporter le code que vous avez écrit. Vous devrez donc taper :


```
git remote add origin https://github.com/votre_nom_utilisateur_github/nom_de_votre_depot.git
```


Ici, on a ajouter une _remote_ que l’on appelé _origin _et l’URL d’_origin _est _[https://github.com/votre_nom_utilisateur_github/nom_de_votre_depot.git](https://github.com/votre_nom_utilisateur_github/nom_de_votre_depot.git)_ qui correspond à l’endroit où se trouve votre dépôt dans Github.

Pour terminer, vous pouvez entrer la commande _push_ qui servira à exporter votre code. Vous devrez préciser sur quelle _remote_ vous souhaitez exporter le code. Voici la commande :


```
git push origin master
```


Vous avez vu ici qu’on a ajouté aussi la commande _master_. C’est le nom de la branche sur laquelle on veut exporter notre code. Ici, nous l’avons exporter sur la branche maîtresse. Nous expliquerons ce concept dans la prochaine partie.

Le tour est joué, votre code est uploadé sur votre profil Github!

**NB** : Il est possible que la première fois que vous fassiez ceci, la console vous demande votre nom d’utilisateur github et votre mot de passe.

Maintenant que vous avez une idée de comment fonctionne git, voyons les fonctionnalités les plus utiles de l’outil pour collaborer et améliorer vos applications sans jamais casser votre code.


#### Créer une branche

Parlons de branches. La deuxième chose qui fait un VCS et qui est si pratique est le fait de pouvoir créer des branches. Une branche est une exacte copie de votre code d’origine que vous pouvez changer comme bon vous semble sans pour autant changer de le code d’origine. Cela vous permet donc de travailler sur de nouvelles features de votre projet sans prendre le risque de faire des erreurs qui pourraient être fatales. Regardons donc les commandes utiles liées aux branches


##### Regarder toutes les branches de votre dépôt

Pour regarder toutes les branches présentes dans votre projet, il faudra taper :


```
git branch
```


La commande affichera toutes les branches créées.


##### Créer une branche

Pour créer une nouvelle branche, il suffira simplement d’ajouter à la commande du dessus, le nom de la branche que vous souhaitez créer


```
git branch nom_de_votre_branche
```



##### Accéder à une branche

Nous avons maintenant créé notre nouvelle branche. Il faut pouvoir y accéder. C’est la commande suivante qui va nous permettre d’arriver à nos fins


```
git checkout nom_de_votre_branche
```



##### Fusionner des branches

Une fois que le code que vous avez écrit sur votre nouvelle branche fonctionne, vous pouvez fusionner votre branche sur la branche maîtresse de la façon suivante :


```
git merge nom_de_la_branche_que_vous_souhaitez_fusionner
```


ATTENTION, il faut bien comprendre dans quelle branche vous vous trouvez quand vous faites un `git merge`. Si vous vous trouvez sur la branche `master` et que vous faites `git merge`


```
une_branche, vous allez fusionner la branche une_branche à la branche master
```



##### Supprimer une branche

Pour terminer, il est utile de savoir supprimer une branche qui n’est plus utile. Pour ce faire :


```
git branch -d nom_de_la_branch
```


ATTENTION : Vous ne pouvez pas supprimer une branche si vous êtes en ce moment dessus. Si vous tentez de le faire, une erreur apparaîtra.


#### Créer un pull request

Si vous devez collaborer sur un projet avec d’autres personnes, il y a de fortes chances pour que vous ne fusionniez pas vos branches directement en local. Vous irez plutôt sur Github et vous créerez un _pull request_.

Un _pull request_ permet de demander à faire une fusion de branche via Github. Ceci a l’avantage que d’autres personnes peuvent regarder votre travail, ajouter des commentaires avant d’officiellement fusionner les branches. C’est donc une sécurité supplémentaire très utile. Voyons donc comment on peut faire ceci.

Pour créer un pull request, vous devez d’abord créer une branche et faire un _git push_ de votre branche vers votre dépôt Github.


```
git checkout -b nouvelle_branche
```


**Avant de faire un push,** effectuez la commande suivante :


```
git pull nom_de_votre_remote nom_de_votre_branche
```


La commande pull permet d’être certain que vous êtes à jour dans le code qui a été déposé dans le dépôt. Une fois que vous êtes à jour sur votre machine, vous pouvez faire :


```
git push nom_de_votre_remote nom_de_votre_branche
```


Une fois que vous avez fait cela, allez dans Github dans votre dépôt et cliquez sur _pull requests_ puis _New Pull Request_

![](https://drive.google.com/uc?export=view&id=1AbWxZ85K8HKS0s6LAPrb2lMzvPaUHKt-)

Ensuite, vous devriez voir la branche sur laquelle vous avez fait un _git push_ et que vous pouvez fusionner

![](https://drive.google.com/uc?export=view&id=1qu48hYjpVCFVTAp88ch4O2cbxq6y9x-O)


Une fois que vous l’avez sélectionné, vous pourrez appuyer sur _Create New Pull Request,_ donner un nom à celle-ci et un premier commentaire. Une fois que ceci est fait, vous pouvez cliquer sur _merge pull request_ et le tour est joué.

![](https://drive.google.com/uc?export=view&id=1t0HBnyGB8SNGmLwvt6INdKJKs5s1x5R3)


Si vous regardez les onglets de cette branche, vous pourrez voir tous les différents commit et les changements qui ont été effectués

![](https://drive.google.com/uc?export=view&id=1TNqBclxUKmegb5AfVudRF2OUUx54aNtc)


Vous pouvez donc regarder le code et commenter à votre guise pour collaborer sur le projet avant de fusionner les branches.


#### Revoir ses commits

Il arrive souvent que l’on se trompe et qu’on souhaite revenir à une version précédente de notre code. Vous avez donc deux options pour cela :


```
git reset nom_de_votre_commit
```


Ceci va annuler tous les commits que vous avez fait après le commit que vous avez spécifié dans votre commande. Cela ne va pas pour autant effacer le code que vous avez écrit sur votre éditeur de texte en local.


```
git reset --hard nom_de_votre_commit
```


Cette commande va, elle, effacer le code que vous avez écrit en local pour revenir exactement à la commit que vous avez spécifié dans votre commande.

NB : Pour connaître le nom de votre commit, entrez la commande


```
git log
```

Vous verrez apparaître les différents commit effectué et le nom de celle-ci, comme dans l’exemple ci-dessous :

![](https://drive.google.com/uc?export=view&id=16x0HuljQ2aUxPq7qvreTx0UEOe59-Rve)


#### Ignorer des fichiers

Il arrive souvent que vous ayez des fichiers que vous n’aimeriez pas avoir public dans le web. Par exemple, vous avez un fichier dans lequel contient des codes ou des clés d’API qui sont censées rester secrètes.

C’est pour cela qu’on a mis en place .gitignore. Si vous créez un fichier que vous nommez _.gitignore_, tous les noms de fichiers présents dans celui-ci seront ignorés par git. Donc, si par exemple, vous faites un _git push_, tous les fichiers qui seront présents dans ._gitignore_ ne seront pas poussés dans github.

![](https://drive.google.com/uc?export=view&id=1Rrm9a9K3iz8fDHNs-xOpBpUDwBXsQ2sM)


Dans cet exemple, le fichier *un_fichier.html* sera ignoré par git.


### Bien écrire son fichier README.md

Il y a une chose qu’il est important de connaître pour faire du bon travail sur Github qui est : Bien écrire ses fichiers README.md

Le fichier README.md est ce que Github va afficher par défaut lorsque vous ouvrez un dépôt. C’est ce qui va permettre de comprendre le projet et d’apprendre comment l’aborder. Si vous avez un fichier README.md bien fait, vous aurez plus de monde qui pourront vous aider dans votre projet.

Il y a donc quelques techniques à connaître pour écrire dans un fichier _.md_


#### Faire des titres

Rien de plus simple, il vous suffira de mettre une _#_ pour designer que vous texte est un titre. Par exemple :


```
# Ceci est un titre
```


Plus vous ajoutez de # , plus vous descendez dans la hiérarchie d’importance des titres. Par exemple :


```
## Ceci est un sous-titre
### Ceci est un sous-sous-titre
#### Ceci est un sous-sous-sous-titre
##### etc
###### Ceci est le maximum
```



#### Styliser vos textes


Vous pouvez mettre votre texte en italique, gras avec ce code

![](https://drive.google.com/uc?export=view&id=1PheXPG-cTHrbOUzFfe6j3HdjyVe9JY9C)


#### Ajouter du code dans vos textes

Il arrivera très souvent que vous souhaitiez incorporer du code dans votre fichier. Vous pouvez le faire tout simplement en ajoutant trois contre-apostrophes avant et après votre code. Par exemple


```
```
for item in variable
    print("hello world")

```
```

#### Mettre un lien

Pour mettre un lien dans Github, il faudra procéder de la manière suivante :


```
[Le texte à mettre en lien ](l'url vers lequel rediriger)
```

Par exemple


```
[Jedha](https://jedha.co)
```


Ceci sont les commandes principales pour écrire votre fichier README.md, il y en a, bien sûr, pleins d’autres que vous pouvez utiliser. N’hésitez pas à regarder dans la partie Ressource du cours pour en connaître plus.


## La gestion de projets Agile

Il y a plusieurs méthodes de management qui se sont développées au fur et à mesure des années. Une très en vogue est la méthode _Agile._ Cette méthode est très utile, rapide et flexible. Surtout lorsqu’elle s’applique aux équipe techniques. Voyons en donc les grands principes


### Agile VS Waterfall

Les méthodes Agile consistent à pouvoir développer rapidement un produit ou une feature de produit. L’idée est de pouvoir être flexible et de s’adapter rapidement aux besoins du marché.

Vous allez donc définir avec votre équipe un MVP ou Minimum Viable Product. Ce qui veut dire que vous allez inclure le strict minimum possible dans votre produit et qu’il est un minimum d’attractivité. Vous allez ensuite tester ce produit en le lançant sur le marché puis vous allez récolter des retours de votre cible et vous allez “itérer” sur le produit, c’est à dire l’améliorer pour le rendre plus attractif. Une fois que vous avez créé votre deuxième version, vous allez la renvoyer sur le marché et ainsi de suite, jusqu’à ce que vous ayez le produit parfait.

Ces méthodes sont très à la mode car elles fonctionnent extrêmement bien pour les services et les softwares. Ce qui fait une belle partie de l’économie aujourd’hui.  

Cependant, elles ont leurs limites lorsqu’on parle de produits industriels où les cycles de productions sont très longs et ne permettent pas autant de flexibilité. C’est pourquoi on utilisera plus des méthodes Waterfall où l’idée est de préparer un plan d’action qu’on exécute de bout en bout. On voit bien ici qu’il y a moins de flexibilité dans cette méthode mais, au moins, elle permet de fixer un cap pour toute l’équipe dans le développement d’un projet.


### La méthode SCRUM

Une fois qu’on a parlé des grands principes de gestion de projet, nous aimerions nous attarder principalement sur l’une des méthodes agile : _SCRUM._ Vous serez amené très souvent à gérer des projets ou faire partie de projets gérés par la méthode SCRUM. Nous allons donc l’expliquer plus en détails


#### Les acteurs de la méthode

Tout d’abord, le cadre du _SCRUM._ On distingue trois rôles au sein d’une équipe _SCRUM_ :



1. Un _Product Owner_ qui va porter la vision du produit. C’est à dire qu’il va expliquer comme il voit le produit finit
2. Une _Equipe de Développement_ qui va s’occuper de construire le produit
3. Un _Scrum Master_ qui va garantir que la méthodologie _SCRUM_ est appliquée

Les équipes _SCRUM_ peuvent être de 3 jusqu’à 9 personnes. Au delà, on perd en agilité.


#### Sprint

Au début de la méthode SCRUM, il y a le Sprint. C’est à dire qu’on définit les éléments que l’équipe de développement va réaliser durant une période définie. Les sprints sont souvent sur 30 jours.

Les éléments dont on parle font tout d’abord partie du _Product Backlog_. C’est à dire les éléments mis en attente de développement. Le product Owner va définir les éléments à développer en priorité et assigner des ressources dessus. Une fois que ceci est définie, l’équipe de développement se met au travail.


#### Daily Stand Up

Tous les jours, l’équipe de développement prend 15 minutes pour expliquer ce sur quoi elle va travailler et ce qu’elle a terminé. Cela permet à chacun d’être à la page et d’avancer rapidement dans la journée.


#### Revue du sprint

Une fois que le Sprint est terminé, l’équipe de développe va mettre à plat toutes les features qu’ils ont réussi à développer. On recueille aussi le feedback des utilisateurs et du product owner et on prépare le prochain sprint.


#### Retrospective du sprint

Enfin, on fait une dernière réunion qui est une retrospective du sprint. Cette réunion est plus liées à “comment améliorer la productivité de l’équipe”. On va faire une introspective et voir ce qui a marché et ce qui a moins marché après l’expérience du sprint.


## Ressources

Git cheatsheet - [https://services.github.com/on-demand/downloads/fr/github-git-cheat-sheet/](https://services.github.com/on-demand/downloads/fr/github-git-cheat-sheet/)

Git best practice - [https://guides.github.com/introduction/flow/](https://guides.github.com/introduction/flow/)

Paramétrer votre nom d’utilisateur et email sur git - [https://help.github.com/articles/setting-your-username-in-git/](https://help.github.com/articles/setting-your-username-in-git/)

Créer un dépôt sur Github - [https://help.github.com/articles/create-a-repo/](https://help.github.com/articles/create-a-repo/)

Ecrire sur Github Débutant - [https://help.github.com/articles/basic-writing-and-formatting-syntax/](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

Ecrire sur Github Avancé - [https://help.github.com/articles/organizing-information-with-tables/](https://help.github.com/articles/organizing-information-with-tables/)

La méthode SCRUM - [https://agiliste.fr/introduction-methodes-agiles/](https://agiliste.fr/introduction-methodes-agiles/)

Lean Startup - [http://theleanstartup.com/](http://theleanstartup.com/)
