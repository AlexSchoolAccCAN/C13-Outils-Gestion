![Wikipedia](Wikipedia_fr.png) [Page Wikipédia](https://fr.wikipedia.org/wiki/Instruction_conditionnelle_(programmation)#)

[//]: # (Je n'ai trouvé aucune citation en rapport avec mon sujet Wikipédia)

# Instruction conditionnelle (programmation)
\
En [informatique](https://fr.wikipedia.org/wiki/Informatique), **une instruction conditionnelle**, (aussi appelé **expression conditionnelle**), est une fonction d'un [langage de programmation](https://fr.wikipedia.org/wiki/Langage_de_programmation), qui effectue différents calculs ou actions, en fonction de l'évaluation d'une condition [booléenne](https://fr.wikipedia.org/wiki/Bool%C3%A9en), à savoir _vraie_ ou _fausse_.

Dans les langages de [programmation impératifs](https://fr.wikipedia.org/wiki/Programmation_imp%C3%A9rative), le terme « instruction conditionnelle » est souvent utilisé, alors qu'en programmation fonctionnelle, le terme « expression conditionnelle » est préféré, parce que ces termes ont tous une signification distincte.

[//]: # (J'ai essayé de placer les images de la meilleure manière possible)

![Diagramme de flux de Si](Diagramme_de_flux_de_Si.png) Diagramme de flux de Si

[//]: # (Image lien RELATIF vers un dossier local au dessus)

## Si–alors(–sinon)
---
![Un organigramme de programmation](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/IF-THEN-ELSE-END_flowchart.svg/220px-IF-THEN-ELSE-END_flowchart.svg.png) Un [organigramme de programmation](https://fr.wikipedia.org/wiki/Organigramme_de_programmation) de « Si-alors-sinon » (_If–then–else_ en anglais)

La structure `si–alors` (parfois appelé `si–alors–sinon`) est commune à de nombreux langages de programmation. Bien que la syntaxe varie quelque peu selon le langage, la structure de base (sous forme de pseudocode) ressemble à ceci :

```Ada
 If (condition booléenne) Then
    (conséquent)
 Else
    (alternative)
 End If
```
 Quand un [interprète](https://fr.wikipedia.org/wiki/Interpr%C3%A8te_(informatique)) trouve un `Si`, il attend une condition [booléenne](https://fr.wikipedia.org/wiki/Bool%C3%A9en) – par exemple, `x > 0`, ce qui signifie « la variable _x_ contient un nombre qui est supérieur à zéro » – et évalue cette condition. Si la condition est `vraie`, les instructions suivant le `alors` sont exécutées. Dans le cas contraire, l'exécution se poursuit jusqu'au branchement suivant – soit au niveau du block `sinon` (qui est usuellement optionnelle), ou s'il n'y a pas de branchement `sinon`, alors après le `fin Si`. 

 Après qu'un branchement a été exécuté, le [contrôle](https://fr.wikipedia.org/wiki/Structure_de_contr%C3%B4le) revient au point après fin Si. 

 Dans les premiers langages de programmation, en particulier certains dialectes du [BASIC](https://fr.wikipedia.org/wiki/BASIC) des [ordinateurs personnels](https://fr.wikipedia.org/wiki/Ordinateurs_personnels) des années 1980, une instruction `si–alors` pouvait seulement contenir des instructions [GOTO](https://fr.wikipedia.org/wiki/Goto_(informatique)). Cela a conduit à un style de programmation difficile à lire, connue sous le nom de [programmation spaghetti](https://fr.wikipedia.org/wiki/Programmation_spaghetti), avec des programmes de ce style appelé **_code spaghetti_**. En conséquence, la [programmation structurée](https://fr.wikipedia.org/wiki/Programmation_structur%C3%A9e), qui admet (virtuellement) les instructions arbitraires à l'intérieur d'une instruction `si`, gagne en popularité, jusqu'à ce qu'elle devienne la norme dans la plupart des programmes en BASIC. De tels mécanismes et principes ont été tirés de la famille de langages [ALGOL](https://fr.wikipedia.org/wiki/Algol_(langage)) plus âgés, mais plus avancés, et les langages ressemblant à l'ALGOL, tels des [Pascal](https://fr.wikipedia.org/wiki/Pascal_(langage)) et [Modula-2](https://fr.wikipedia.org/wiki/Modula-2). Bien qu'il soit possible d'utiliser uniquement les instructions `GOTO` dans un `si-alors` pour écrire des programmes non-spaghetti, tout aussi bien structurés et lisibles que des programmes écrits dans un langage de programmation structuré, la programmation structurée rend cela plus facile, et l'applique. L'instruction structurée `si-alors-sinon`, comme dans l'exemple ci-dessus est l'un des éléments de la programmation structurée, et est présente dans les langages de programmation de haut niveau tels que le [C](https://fr.wikipedia.org/wiki/C_(langage)), [Java](https://fr.wikipedia.org/wiki/Java_(langage)), [JavaScript](https://fr.wikipedia.org/wiki/JavaScript) et [Visual Basic](https://fr.wikipedia.org/wiki/Visual_Basic). 

 L'instruction else, présente dans de nombreux langages, signifie que la [grammaire non contextuelle](https://fr.wikipedia.org/wiki/Grammaire_non_contextuelle) est ambiguë. Plus précisément, 

```
si a alors si b alors s sinon s2
```
peut être analysé comme
```
si a alors (si b alors s) sinon s2
```
ou
```
si a alors (si b alors s sinon s2)
```
selon que `sinon` est associé avec le premier ou le second `si`. Ceci est connu sous le problème portant le nom du dangling else, et est résolu de différentes manières, en fonction de son langage.

### **Sinon si (else if)**
---
En utilisant l'instruction `sinon si`, il est possible de combiner plusieurs conditions. Seuls les énoncés suivant la première condition qui se trouve être vraie seront exécutés. Toutes les autres déclarations seront ignorées. Exemple :

```Ada
if condition then
   -- déclaration
elsif autre_condition then
    -- autre déclaration
elsif encore_autre_condition then
    -- encore une autre déclaration;
-- ...
else
    -- dernière déclaration;
end if;
```

`elsif` (sinon si) en [Ada](https://fr.wikipedia.org/wiki/Ada_(langage)), est un [sucre syntaxique](https://fr.wikipedia.org/wiki/Sucre_syntaxique) pour `else` suivi de `if`. En Ada, la différence est qu'une seule instruction de fin `end if` est nécessaire si on utilise `elsif` au lieu de `else if`. [PHP](https://fr.wikipedia.org/wiki/PHP) utilise le mot-clef `elseif`<sup>[1](https://fr.wikipedia.org/wiki/Instruction_conditionnelle_(programmation)#cite_note-php_elseif-1)</sup> à la fois pour sa syntaxe à accolades ou celle à points-virgules. [Perl](https://fr.wikipedia.org/wiki/Perl_(langage)) fournit le mot-clé `elseif` et [Python](https://fr.wikipedia.org/wiki/Python_(langage)) le mot-clé `elif` afin d'éviter un grand nombre de parenthèses ou d'indentations qui seraient autrement nécessaires. Certaines implémentations de [BASIC](https://fr.wikipedia.org/wiki/BASIC), tel [Visual Basic](https://fr.wikipedia.org/wiki/Visual_Basic)<sup>[2](https://fr.wikipedia.org/wiki/Instruction_conditionnelle_(programmation)#cite_note-vb_elseif-2)</sup>, disposent aussi d'un `ElseIf`. La syntaxe shell POSIX utilise `elif`<sup>[3](https://fr.wikipedia.org/wiki/Instruction_conditionnelle_(programmation)#cite_note-posixshell-3)</sup>.

Cependant, dans de nombreuses langages dérivés d'Algol, tel que [Algol 68](https://fr.wikipedia.org/wiki/Algol_68), [Simula](https://fr.wikipedia.org/wiki/Simula), [Pascal](https://fr.wikipedia.org/wiki/Pascal_(langage)), [BCPL](https://fr.wikipedia.org/wiki/BCPL) et [C](https://fr.wikipedia.org/wiki/C_(langage)), la construction `sinon si` n'est pas présente. Dans les nombreux dérivés syntaxiques de C, tels que [Java](https://fr.wikipedia.org/wiki/Java_(langage)), [ECMAScript](https://fr.wikipedia.org/wiki/ECMAScript), etc. on utilise `else if` et non un mot-clef `elseif` dédié qui serait superflu car ces langages permettent à une expression de suivre une condition sans être enfermée dans un bloc. 

### **Expressions si–alors–sinon (if–then–else)**
---
Beaucoup de langues prennent en charge l'_expression si_, qui est similaire à l'instruction si, mais qui par la suite renvoie une valeur. Ainsi, il existe des expressions vraies (qui évaluent à une valeur), et non des instructions (qui modifient l'état du programme ou exercent une sorte d'action). 

## Instruction switch
---
 Article détaillé : [Switch (instruction)](https://fr.wikipedia.org/wiki/Switch_(instruction)).
___
 
Les [instructions switch](https://fr.wikipedia.org/wiki/Switch_(instruction)) permettent d'effectuer un branchement à partir de la valeur d'une variable. Dans les langages dynamiques, les switchs ne peuvent pas être limitées à des expressions constantes, et pourraient étendre le [filtrage par motif](https://fr.wikipedia.org/wiki/Filtrage_par_motif).

## Filtrage par motif
---
Article détaillé : [filtrage par motif](https://fr.wikipedia.org/wiki/Filtrage_par_motif).
___

Le [filtrage par motif](https://fr.wikipedia.org/wiki/Filtrage_par_motif) peut être considéré comme une alternative plus sophistiquée à la fois des _si-alors-sinon_, et des [_switchs_](https://fr.wikipedia.org/wiki/Switch_(instruction)). Il est disponible dans de nombreux langages de programmation avec des fonctionnalités de programmation fonctionnels, tels que le [Wolfram Language](https://fr.wikipedia.org/wiki/Wolfram_Language), [ML](https://fr.wikipedia.org/wiki/ML_(langage)) et beaucoup d'autres. Voici un exemple simple écrit dans le langage [OCaml](https://fr.wikipedia.org/wiki/OCaml) :

```OCaml
 match fruit with
 | "pomme" -> cuisiner tarte
 | "noix de coco" -> cuisinier dango_mochi
 | "banane" -> mixer;;
```

## Conditionnelles basées sur un hashage
---
Dans les langages de programmation qui ont des [tableaux associatifs](https://fr.wikipedia.org/wiki/Tableau_associatif), tels que [Python](https://fr.wikipedia.org/wiki/Python_(langage)), [Perl](https://fr.wikipedia.org/wiki/Perl_(langage)), [PHP](https://fr.wikipedia.org/wiki/PHP) ou [Objective-C](https://fr.wikipedia.org/wiki/Objective-C), il est idiomatique de les utiliser pour mettre en œuvre un assignement conditionnel<sup>[4](https://fr.wikipedia.org/wiki/Instruction_conditionnelle_(programmation)#cite_note-4)</sup>.

```OCaml
animal = raw_input("Entrez le type d'animal que vous voulez nommer : ")
animaux_connus = {"Chien": "Fido",
              "Chat": "Meowsles",
              "Oiseau": "Tweety"}
mon_nom = animaux_connus[animal]
```
## Prédiction de branchement
---
Dans l'[assembleur](https://fr.wikipedia.org/wiki/Langage_d%27assemblage), la prédiction de branchement est une caractéristique de certains processeurs des ensembles d'instructions qui permet l'exécution conditionnelle d'instructions, sans avoir à effectuer des sauts conditionnels coûteux. 

## Voir aussi
---
- [Branchement](https://fr.wikipedia.org/wiki/Branchement)
- [Compilation conditionnelle](https://fr.wikipedia.org/w/index.php?title=Compilation_conditionnelle&action=edit&redlink=1)
- [COBOL](https://fr.wikipedia.org/wiki/COBOL)
- [Test (Unix)](https://fr.wikipedia.org/wiki/Test_(Unix))
- [condition Yoda](https://fr.wikipedia.org/wiki/Condition_Yoda)
- [Style de programmation](https://fr.wikipedia.org/wiki/Style_de_programmation)
- [algorithme](https://fr.wikipedia.org/wiki/Algorithme)

## Références
---
- (**en**) Cet article est partiellement ou en totalité issu de l’article de Wikipédia en [anglais](https://fr.wikipedia.org/wiki/Anglais) intitulé « [Conditional (computer programming)](https://en.wikipedia.org/wiki/Conditional_(computer_programming)?oldid=739830864) » ([voir la liste des auteurs](https://en.wikipedia.org/wiki/Conditional_(computer_programming)?action=history)).

1. [↑ _syntaxe elseif dans PHP_](http://php.net/manual/control-structures.elseif.php) [[_archive_]](https://archive.wikiwix.com/cache/?url=http%3A%2F%2Fphp.net%2Fmanual%2Fcontrol-structures.elseif.php)
2. [↑ _Visual Basic ElseIf syntax_](http://php.net/manual/control-structures.elseif.php) [[_archive_]](https://archive.wikiwix.com/cache/?url=https%3A%2F%2Fdocs.microsoft.com%2Fdotnet%2Fvisual-basic%2Flanguage-reference%2Fstatements%2Fif-then-else-statement)
3. [↑ _POSIX standard shell syntax_](http://php.net/manual/control-structures.elseif.php) [[_archive_]](https://archive.wikiwix.com/cache/?url=http%3A%2F%2Fpubs.opengroup.org%2Fonlinepubs%2F009695399%2Futilities%2Fxcu_chap02.html)
4. [↑ _"Pythonic way to implement switch/case statements"_](http://php.net/manual/control-structures.elseif.php) [[_archive_]](https://archive.wikiwix.com/cache/?url=http%3A%2F%2Fcodingstyleguide.com%2Fstyle%2F180%2Fpython-pythonic-way-to-implement-switchcase-statements)

### Sommaire
1. [Début](#instruction-conditionnelle-programmation)
2. [Si–alors(–sinon)](#si–alors–sinon)
    1. [Sinon si (else if)](#sinon-si-else-if)
    1. [Expressions si–alors–sinon (if–then–else)](#expressions-si–alors–sinon-if–then–else)
5. [Instruction switch](#instruction-switch)
6. [Filtrage par motif](#filtrage-par-motif)
7. [Conditionnelles basées sur un hashage](#conditionnelles-basées-sur-un-hashage)
8. [Prédiction de branchement](#prédiction-de-branchement)
9. [Voir aussi](#voir-aussi)
10. [Références](#références)