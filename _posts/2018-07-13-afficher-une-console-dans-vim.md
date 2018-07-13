---
layout: post
title: "Afficher une console dans Vim ?"
categories: workflow, dev, vim 
---

Il est possible d'avoir une console dans la plupart de nos IDE favoris. Alors pourquoi
pas Vim ?


> J'utilise vim dans un terminal, pas en mode GUI. Ces astuces s'appliquent donc à ce
type d'environnement.


D'après ce que j'ai pu trouvé sur le web, il n'est pas vraiment possible d'avoir sous la main
un terminal embarqué dans Vim. Par contre, il existe quelques solutions de contournement. 


## 1. Miniser Vim dans la console. 

Premier truc tout bête : une fois dans Vim, vous pouvez utiliser le raccourci `Ctrl + z` pour
"minimiser" Vim. Vous devriez donc retrouver la console en arrière plan. 

Pour retourner ensuite dans Vim, tapez la commande `fg` puis faites `Enter`. Vous voilà de retour dans
Vim. 

## 2. Lancer une ligne de commande depuis Vim

Vous pouvez aussi lancer une ligne de commande directement depuis Vim en mode Normal.
Vim passera alors la commande en question à votre terminal, se minimisera, et passera la 
main au terminal. 

En mode Normal, utilisez la syntaxe suivante `:! echo 'Ma ligne de commande a été exécutée.'`.

Vous devrez alors taper la touche `Entrée` pour retourner à Vim là où vous l'aviez laissé. 


## 3. Ma favorite, utiliser tmux

C'est de loin la solution que je préfère. [Tmux](https://doc.ubuntu-fr.org/tmux) est un "multiplexeur de terminal", il vous permet de 
gérer plusieurs sessions dans un seul écran. On peut afficher plusieurs sessions en simulatnée via
un système de splits d'écran. 

![Afficher une console a cote de vim avec tmux]({{ site.url }}/assets/images/2018-07-13-afficher-une-console-dans-vim/tmux-vertical-split-vim.jpg)


### Installation de tmux

Rien de bien compliqué pour les habitués :


```bash
sudo apt-get install tmux
```

### Démarrer tmux


```bash
tmux
``` 

### Une session pour Vim, une pour le terminal

Une fois que tmux est lancé, tapez le raccourci `Ctrl + b` suivi de `%`. Votre écran sera séparé verticalement 
en 2 avec chacun une session distincte.

> Pour séparer votre écran à l'horizontal, utilisez `Ctrl +b` suivi de `"`.

Le but sera donc d'afficher Vim dans une des sessions, puis garder le terminal dans l'autre. 

* Pour switcher entre vos sessions, faites `Ctrl + b` suivi de `o`. 

* Pour permuter vos écrans : `Ctrl + b + o`.

* Et enfin, pour redimensionner vos fenêtres, utilisez `Ctrl + b` suivi de `Alt + une touche directionnelle`.

Vous pouvez trouvez une liste de raccourcis tmux [ici](https://doc.ubuntu-fr.org/tmux#les_principaux_raccourcis)


Au final, c'est la solution de tmux que je préfère, qui laisse les 2 écrans visibles, et qui se rapproche plus du confort que j'avais trouvé
avec d'autres IDE.


__Références__

> [https://doc.ubuntu-fr.org/tmux](https://doc.ubuntu-fr.org/tmux)
