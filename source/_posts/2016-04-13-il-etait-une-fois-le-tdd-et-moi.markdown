---
layout: post
title: "Il était une fois le TDD... et moi"
date: 2016-04-13 17:27:36 +0200
comments: true
categories: [tdd, craftsmanship]
---

Il était une fois une jeune fille pleine de projets, de passions et un chouilla hyperactive.  
Elle n'aime pas particulièrement raconter sa vie et se demande donc fortement comment elle va réussir à faire cet article.  
Parmi ses rêves de gosse se trouvaient d'apprendre plein de choses sur les sciences, notamment les biosciences, et sur l'informatique. Elle a donc démarré avec les biosciences (d'ailleurs c'est méga passionant, rien de plus complexe et de mieux architecturé que le corps humain) puis a décidé d'enchaîner avec l'informatique. Cependant, le cursus suivi en informatique n'a duré qu'un an (moitié cours, moitié stage). Evidemment, il ne s'agissait que d'une porte d'accès au monde qu'elle souhaitait tant découvrir.

<!-- more -->

N'ayant pas beaucoup de connaissances ni d'expériences en informatique, elle était (et elle est toujours) à la recherche de méthodes, d'outils et de bonnes pratiques qui lui permettraient de progresser et de produire du code propre. Parmi ces outils se trouve le TDD.

Le TDD est un outil de développement qui préconise l'écriture des tests avant le code de production. Il a été inventé par Kent Beck. Et vous savez quoi ? C'est un truc de dingue ;-)
Dans cet article, je vais vous parler de mon expérience personnelle concernant le TDD : les débuts, les avantages et inconvénients et quelques idées pour le mettre en place.

## Les débuts

Au départ, je voyais l'intérêt théorique de cet outil et le concept me passionnait particulièrement (je trouve ça malin). Par contre, en pratique, je trouvais que ça me ralentissait un peu et que c'était un peu compliqué.  
Je l'ai expérimenté pour la première fois vers la fin de ma première année de développement et au sein d'un projet assez complexe en termes de métier, de technologies et d'enjeux. Autant dire que je n'avais pas que le TDD à intégrer dans ma petite tête ! Du coup, j'essayais de le faire quand je n'étais pas débordée et le plus souvent possible. Par ailleurs, la grande majorité des développeurs de ce gros projet n'utilisaient pas cet outil. Il était donc parfois un peu dur de faire du TDD dans ce contexte mais il était hors de question d'abandonner, je voyais le potentiel de cet outil et je savais qu'il fallait persévéver.

Après cette première année d'expérience dans le développement, où j'ai énormément appris, et une petite expérience en TDD, j'ai décidé de dédier du temps à des projets personnels. Et là, tout a changé. Partant d'un projet de zéro, avec toutes les libertés possibles, je pouvais expérimenter encore plus facilement le TDD.

Après une bonne nuit de sommeil, j'ai donc commencé mon projet avec un test. C'était trop beau. A ce moment précis, j'ai compris un certain nombre d'avantages que le TDD peut nous apporter.

## Les avantages

### Exprimer le besoin plutôt que de réaliser une implémentation
On se concentre sur le besoin plutôt que sur une implémentation.

### Travailler unitairement et être plus efficace
On ne fait qu'une chose à la fois donc on est plus efficace.
Contrairement à ce que je pensais au tout début, j'ai rapidement compris que le TDD permettait d'aller plus vite. En effet, on ne se pose pas vingt questions à la fois, voire des questions existentielles pour savoir comment construire le meilleur design. Je ne dis pas qu'il ne faut plus se poser de question. D'ailleurs, je pense qu'il le faut et que cela doit faire partie de notre métier de développeur. Par contre, le TDD permet de se poser des questions encore plus pertinentes et ciblées, sur une fonctionnalité à la fois.

### Disposer d'un harnais de test
En commençant par les tests, non seulement on est certain d'en avoir mais on est sûr d'avoir des tests pertinents. En effet, ils couvrent de vrais besoins métiers.  
Ce harnais de test permet d'assurer que notre code est protégé et que, lors de refactorings ou ajout de nouvelles fonctionnalités, on pourra facilement et rapidement détecter des régressions, les tests unitaires étant les moins coûteux en terme de réalisation et permettant d'avoir un feedback extrêmement rapide.

### Gagner en confiance
En faisant du TDD, je sais que je développe ce qu'il faut exactement développer, ce qui n'est pas négligeable ! Ceci m'a permis de gagner en confiance dans mes développements.

### Faire émerger un design propre
Le TDD permet de se rendre compte quand le design n'est pas correct. En effet, si on n'arrive pas à tester notre code, cela veut dire que notre design n'est plus adapté ou ne l'a jamais été. Il s'agit ainsi d'une alerte pour nous encourager à le rendre plus simple et adapté à notre besoin à un instant T. Par exemple, si on a besoin de mocker et de fixer un comportement pour en tester un autre qui en dépend et qu'on n'y arrive pas, cela veut peut-être dire que nos classes sont trop couplées. Ceci peut arriver quand on fait un appel statique dans une classe. Dans ce cas, les classes sont fortement liées car on ne peut pas changer l'implémentation de ce qui est utilisé. Or, les classes doivent être fortement découplées pour que le système soit plus maintenable (évolutif et extensible en changeant les implémentations facilement).

De plus, j'ai pu constater que le design qui émerge en utilisant du TDD est plutôt simple. Je pense qu'il s'agit du résultat obtenu par l'ensemble des avantages du TDD : se concentrer sur le besoin, réaliser une seule chose à la fois et avoir plus confiance en soi résultent en la construction d'un design propre.

## Les inconvénients

Actuellement, j'en vois aucun et j'ai du mal à en imaginer.
D'ailleurs, je suis surprise de voir que le TDD est parfois mal perçu dans le monde du travail. Il est souvent vu comme étant une perte de temps mais j'ai pu confirmer qu'il s'agit d'une fausse impression. Il faut évidemment un temps d'adaptation et celui-ci peut varier en fonction des développeurs. Néanmoins, je pense que le TDD serait un bon investissement et mérite d'être mis en place. Oui, mais comment ?

## Mise en place

Ce n'est jamais facile d'essayer quelque chose de nouveau, mais si on ne se remettait jamais en question et si on ne repoussait jamais nos limites, on passerait à côté de choses extraordinaires et on s'ennuierait beaucoup aussi.  
Mais comment mettre en place cet outil dans une structure ? Je pense que, comme tout, cela dépend du contexte et il faut toujours s'adapter au mieux à celui-ci. Je vais néanmoins essayer de partager quelques idées à ce sujet.

### Commencer avec des petits objectifs
Etre ambitieux c'est génial mais il est difficile d'arriver au sommet du Mont Blanc, dès la première fois, d'une traite. De la même manière, il faut que nos objectifs, lors de la mise en place du TDD, soient mesurés et bien définis dès le départ. Il pourrait s'agir, par exemple, d'encourager simplement tous les membres de l'équipe à faire du TDD quelques fois dans la semaine. Ainsi, ils peuvent se familiariser petit à petit avec l'outil.

### Ne pas se précipiter, ni se décourager
D'après mon expérience personnelle, il ne sert à rien de vouloir intégrer l'outil en deux minutes et juger ensuite s'il est adapté ou pas. D'ailleurs, si tout le monde nous jugeait en deux minutes, on aurait certainement toujours une perception pas forcément pertinente ou incomplète de nous. Il est important de prendre le temps nécessaire pour connaître l'outil, le comprendre et bien l'utiliser.

### Ne pas le considérer comme quelque chose en dehors des développements
Tout comme le refactoring, le TDD doit, selon moi, faire partie de nos développements. Il ne doit donc pas s'agir de quelque chose dont on doit demander la permission mais plus d'une étape intégrante de nos développements. Par conséquent, il faut prendre en compte le temps d'adaptation dans nos éventuels chiffrages, d'où l'importance d'avoir de petits objectifs au début. Une fois le temps d'adaptation passé, il est bien possible que les chiffrages baissent : je pense que le TDD permet d'aller plus vite, pour les raisons évoquées précédémment, et en plus on aura le temps d'adaptation en moins.

### En faire une affaire d'équipe
Je ne pense pas qu'allouer seulement quelques membres d'une équipe pour tester l'outil soit une bonne idée. Il faut que tous soient concernés au même titre dès le départ. Sinon, je pense que les chances de réussite diminuent considérablement. En effet, si uniquement quelques personnes sont réellement concernées par l'outil, les autres risquent de s'y désintérésser. De plus, si la communication sur l'expérience ne se fait pas idéalement, le temps alloué à celle-ci sera mal utilisé (les résultats peuvent être nuls, certains membres de l'équipe peuvent être découragés et ceux qui ont testé peuvent être déçus). Finalement, on risque de passer à côté d'une belle collaboration entre collègues et donc de meilleurs résultats.

### Avoir une bonne communication au sein de l'équipe
Il ne faut pas hésiter à en parler entre vous. Les différents points de vue vont enrichir l'expérience. Néanmoins, n'oubliez pas le conseil n°2 : ne vous découragez pas !

# Conclusion
Le TDD est un outil de développement qui comporte énormément d'avantages. Il n'est pas forcément évident de les voir du premier coup mais il ne faut pas abandonner le navire car le voyage est vraiment superbe ! J'espère que vous avez apprécié cette histoire et qu'elle vous sera utile. A bientôt !