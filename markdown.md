# Markdown

Cette documentation présente la syntaxe de base pour écrire en Markdown, un langage de balisage léger (_lightweight markup language_) qui offre une syntaxe facile à lire, à écrire et à analyser (_to parse_) par d'autres programmes. Le Mardown est souvent utilisé pour la documentation technique, notamment pour écrire des fichiers `README.md` qui décrivent le fonctionnement du code source d'un programme.

La plupart des éditeurs de texte supportent le Markdown soit nativement ou via une extension.

## Fonctionnement

Dans un éditeur de texte ou une plateforme web d'hébergement de code source comme GitHub ou GitLab, le Markdown comprend généralement une section _Contents_ pour écrire le code et une section _Preview_ pour obtenir le rendu d'une page.

## Extension

L'extension d'un fichier markdown est `.md`.

## Syntaxe

Les éléments de syntaxe qui suivent sont présentés en ordre alphabétique.

Pour consulter la table des matières, appuyez sur l'icône suivante, en haut à droite de cette page :

 ![Markdown Logo](/media/toc.png)

### Blocs de citation

#### Blocs de citation simples

Commencez la ligne avec un signe de comparaison "plus grand que" (`>`), ce qui va créer un bloc de citation indenté.

- Exemple :

```md
> Ceci est une citation en Markdown.
```

- Rendu :

> Ceci est une citation en Markdown.

#### Blocs de citation imbriqués

À l'intérieur d'une citation, commencez une ligne avec une indentation (`tab`) et deux signes de comparaison "plus grand que" (`>>`), ce qui va créer un second bloc de citation indenté et imbriqué.

- Exemple :

```md
> Ceci est une citation en Markdown.
    >> Ceci est une citation imbriquée en Markdown.
```

- Rendu :

> Citation
    >> Ceci est une citation impriquée.

## Blocs de code

Insérez trois accents grave (_backtick_) au début de la ligne (`ASCII : ALT + 96`), suivi du nom de langage de programmation et terminez le bloc avec trois premiers accents grave.

- Exemple :

```txt
Get-ChildItem -Path C:\temp\code.txt 
```

```txt
echo "Hello world !"
```

- Rendu :

```pwsh
Get-ChildItem -Path C:\temp\code.txt 
```

```bash
echo "Hello world !"
```

### Chaîne de caractères surlignée

Insérez un accent grave __( \` )__ avant et après la chaîne de caractères à surligner.

- Exemple :

```txt
`Ceci permet de surligner une chaîne de caractères`  
```

- Rendu :

`Ceci permet de surligner une chaîne de caractères.`

### En-têtes

#### Méthode 1

Ajoutez un carré / croissilon / dièse  (`#`) (_hashtag_) avant la chaîne caractères qui sera utilisée comme en-tête.

- Exemple :

```
# : En-tête niveau 1 
## : En-tête niveau 2
### : En-tête niveau 3
#### : En-tête niveau 4
```

#### Méthode 2

Ajoutez un signe égal (`=`) en dessous de la chaîne caractères qui sera utilisée comme en-tête (retour de chariot).

```
= : En-tête niveau 1 
== : En-tête niveau 2
=== : En-tête niveau 3
==== : En-têter niveau 4 
```

### Images

#### Images internes

Dans Git, il est possible d'ajouter des fichiers d'images dans un document en Markdown.

Commencez la ligne avec un point d'exclamation (`!`) suivi d'une description entre crochets (`[ ]`) et ajouter l'emplacement de l'image entre parenthèeses (`( )`).

- Exemple :

```
 ![Markdown Logo](./markdown.jpg)
```

- Rendu :
  
 ![Markdown Logo](/media/markdown.png)

#### Images du web

Il est également possible d'ajouter des images du web aussi, mais il peut y avoir des contraintes sur le format et le positionnement de l'image sur la page. 

Le procédé est le même que pour une image interne. 

> Le site [LightShot](https://app.prntscr.com/en/index.html) permet de faire des captures d'images et de les référencer directemnent en copiant le nouvel emplacement de l'image créée sur le site.

### Liens

#### Liens internes

Dans Git, il est possible d'ajouter des liens vers d'autres pages du dépôt de fichiers.

Insérez une description entre crochets (`[ ]`) et ajoutez l'emplacement du ficher entre parenthèeses (`( )`).

- Exemple :

```
[Document interne à lier](./Markdown/test.md)
```

- Rendu :

- [Document interne à lier](./Markdown/test.md)

#### Liens de référence

Les liens de références permettent d'insérer des liens numérotés (ou tout autre signe ou chaîne de caractères) pour ajouter une référence à une citation ou renvoyer à un contenu web ou interne.

1. Après la chaîne de caractères à référencer, ajoutez une suite de chiffres (des lettres ou un mot clé) entre crochets (`[ ]`) suivi du numéro d'un accent grave (`[ ^]`).

2. Ajoutez la référence (lien vers une page web) après son numéro entre crochets (`[ ]`) suivi d'un deux points [`:`] à la fin du document 

- Exemple :

```
# Insertion des liens

[1^]
[2^]
[3^]

[A^]
[B^]

[ref1^]
[ref2^]
```

- Exemple :

[^1]
[^2]
[^3]

```
# Ajout des références au bas du document.

[1]:https://google.com
[2]:https://microsoft.com
[3]:https://commvault.com
```



#### Liens web

Les liens webs peuvent être insérés en ajoutant une description entre crochets (`[ ]`) suivie de l'URL du site web entre parenthèeses (`( )`).

```
[Site Web](https://site.web) : 
```

- [Google](https://google.com)

#### Liens web direct

Les liens web peuvent être insérés directement dans un document lorsqu'ils sont entre les marqueures de relation "plus petit que" (`<`) et "plus grand que" (`>`).

- Exemple :

<https://google.com>

## Lignes horizontales

Insérez trois tirets au début d'une ligne (`---`) et une ligne horizontale apparaîtra en mode aperçu (_preview_).

> Il est également possible d'utiliser trois tirets bas.

- Exemple :

```
---
```

- Rendu :

---

### Littéral

Si vous devez écrire un caractère réservé comme `* ou -`, utilisez la barre oblique inversée (_backslash_) comme caractère d'échappement avant.

```
` \*` 
```

\*

### Listes

#### Listes à puces

Insérez un tiret au début d'une ligne et poursuivre avec la chaîne de caractères. Pour ajouter un sous-niveau de puces, ajoutez une espace avant le tiret.

> Il est également possible d'utiliser un astérisque (`*`) au lieu du tiret.

- Exemple :

```
-
-
-
 -
 -
```

- Rendu :
-
-
-
 -
 -

#### Listes numérotées

Commencez une ligne avec le chiffre 1 suivi d'un point (`1.`) et faire un retour de chariot pour que les lignes suivantes se numérotent automatiquement.

- Exemple :

```
1.
2.
3.
```

- Rendu :

1.
2.
3.

### Polices de caractères

#### Gras

Insérez un double tiret bas (_underscore_) (`__ __`) au début et à la fin de la chaîne de caractères.

> Il est également possible d'utiliser deux astérisques `**` au lieu du tiret.

```
__ABC__
```

```
**ABC**
```

- Rendu : __ABC__ 

#### Italique

Insérez un tiret bas (_underscore_) (`_ _`) au début et à la fin de la chaîne de caractères.

> Il est également possible d'utiliser un astérisque (`*`) au lieu du tiret.

```
_ABC_
```

```
*ABC*
```

- Rendu : _ABC_

## Tableaux

Commencez par définir des colonnes par des chaînes de caractères suivies d'une barre verticale (`|`). 

Faites un retour de chariot et ajoutez des tirets __(-)__ sous chaque nom de colonne suivis d'une barre verticale (`|`) pour définir les rangées (le nombre de tiret n'a pas d'importance).

Pour chaque champ, entrez une chaîne caractère pour le contenu, séparée d'une barre verticale (`|`) comme pour définir les colonnes.

Il n'est pas nécessaire de fermer le dernier élément avec une barre verticale.

- Exemple :

```
Colonne 1 | Colonne 2 | Colonne 3
--------- | --------- |---------
Contenu 1 | Contenu 2 | Contenu 3
Contenu 4 | Contenu 5 | Contenu 6
```

- Rendu :

Colonne 1 | Colonne 2 | Colonne 3
--------- | --------- |---------
Contenu 1 | Contenu 2 | Contenu 3
Contenu 4 | Contenu 5 | Contenu 6

### Tables des matières

La fonctionnalité "table des matières" (`TOC`) n'est pas supportée par tous les éditeurs de texte et les plateformes web comme GitHub et GitLab.

Pour l'utiliser, ajouter `_TOC_` enter tirets bas à l'intérieur d'une paire de crochets (`[[ ]]`).

```
[[_TOC_]] 
```
Dans GitHub, vous trouverez un bouton qui permet d'afficher une table des matières à droite du texte.

## Annexes

### Référer à des fichiers avec un lien relatif

Tableau pour l'usage des liens relatifs pour référer à d'autres pages dans Git.

Contexte | Lien relatif
-------- | --------
Référer à un fichier sur la même branche dans le même répertoire | (test.md)
Référer à un fichier sur la même branche dans un sous-répertoire | (./documents/textes/test.md)
Référer à un fichier sur la même branche dans un autre répertoire | (../documents/textes/test.md)
Référer à un fichier sur une autre branche | (/../documents/textes/test.md)

### Référer à une section d'un autre fichier

Ajoutez un carré / croissilon / dièse immédiatement après le lien du fichier et ajouter le nom de la section.

```
 [lien](./test.md#Section1) 
```

## Liens externes

- [Google Markdown Style Guide](https://google.github.io/styleguide/docguide/style.html)
- [markdownguide.org](https://www.markdownguide.org/tools/)
- [StackEdit Online Markdown Editor](https://stackedit.io/)

## Références

[^1]:https://google.com
[^2]:https://microsoft.com
[^3]:https://commvault.com
