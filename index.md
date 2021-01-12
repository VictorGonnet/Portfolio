# Blogpost GPR4100.1 création d'un premier jeu

![](https://Styshooteur.github.io/Images/robot%20ascend.PNG)

# Introduction :

J'avais pour envie de faire un jeu simple mais fun, un jeu auquel je prendrais plaisir à jouer pendant 5 min, c'est pour cela que je me suis inspiré de certains jeux mobiles. J'avais également envie d'apprendre à utiliser Unity pour un jeu 2D. 

# Concept du jeu :

Vous incarnez un petit robot qui entame son ascension en sautant de plateforme en plateforme jusqu'à la fin du niveau. Mais, attention, le temps joue contre vous et des rockets tombe du ciel, il faudra donc être rapide et agile.

# Mécaniques implémentés :

J'ai d'abord implémenté différents types de collisions en utilisant les layers. Quand mon personnage entre en contact avec ces gameobjetcs, une action différente se produit.
- La killingzone et les rockets tuent le joueur.
- Le bumper éjecte le joueur plus fort que le saut.
- Le endrobot déclenche l'écran de victoire.


![](https://Styshooteur.github.io/Images/collision.PNG)

Ensuite, je dirais que la mécanique la plus dure à implémenter a été celle des rockets. En effet, les rockets tombent du ciel et sont le danger principal pour le joueur. Je pensais avoir été malin en utilisant simplement la gravité pour faire tomber mes rockets ainsi je n'avais pas besoin de leur donner une trajectoire et une vitesse mais l'accélération qu'elles accumulent du fait de la gravité s'est montrée très vite problématique. J'aurais donc préferé tout changer pour enlever ce facteur physique mais finalement en réduisant le gravity scale et la masse de la rocket j'obtiens une mécanique qui fonctionne correctement pour ce niveau. Maintenant, je voulais également donner un paterne aléatoire à la fréquence des rockets et leurs positions, pour cela j'ai créé des spawners à différents endroits et je leur ai donné une fréquence semi-aléatoire. Je m'explique, je voulais que les rockets spawns au bout d'un certain temps (évidemment qui diffère selon les spawners pour que les rocket soient évitables) puis qu'à chaque fois qu'une nouvelle rocket spawn, un nouveau nombre soit calculé aléatoirement (entre 10 et 20 secondes par exemple) pour déterminer dans combien de secondes la prochaine doit spawn. Au final je n'ai pas réussi a créér quelque chose d'aussi aléatoire et donc le paterne est déterminé au début du niveau (à chaque fois que le niveau restart) car le jeu détermine une fréquence aléatoire et non un délai à chaque fois qu'une rocket spawn. En bref, le jeu a une bonne rejouabilité mais pas l'expérience opitmale que je voulais donner lorsque l'on fait le niveau une seule fois.
J'ai ainsi créé 3 scripts différents où j'ai simplement changé le temps après lequel la première rocket spawn ainsi que les valeurs du Random.Range.


![](https://Styshooteur.github.io/Images/Shootrocket.PNG)

# Progression personnelle :

Je pense avoir appris beaucoup de choses sur Unity grâce à ce projet mais je n'en maîtrise que très peu. J'aime beaucoup la façon dont Unity nous permet de faire reférence à tel ou tel élément ainsi que les commandes que Unity nous propose de base. Le C# me semble également plus simple que le C++ dans cette mesure. Il y a de nombreuses choses que j'ai pu découvrir et que j'aimerais pouvoir exploiter à nouveau jusqu'à les maîtriser parfaitement comme par exemple la gestion des animations, la création de menu, l'audio ainsi que les colliders. J'ai aussi eu l'occasion de créer un game manager pour automatiser la gestion de la victoire et de la défaite, j'aimerais apprendre à mieux m'en servir.

![](https://Styshooteur.github.io/Images/gamemanager.PNG)

# Conclusion : 

Je pense avoir mener à bien ce projet, respecté en partie les consignes et surtout avoir appris beaucoup de choses. 
J'ai toujours été habitué à tout faire au dernier moment mais avec la programmation je pense que je vais devoir changer mes habitudes car on ne sait jamais à l'avance le nombre de bug que l'on va devoir résoudre et c'est pour cela que j'ai eu chaud niveau timing.
J'ai également dresser une liste des bugs de mon jeu ainsi que des choses que je n'ai pas implémenté exactement comme je le souhaitais de manière à pouvoir y revenir ultérieurement pour retravailler le jeu.

- PS : J'ai fais 3 jours de crunch, grosse dédicace à CD Projekt Red et Florian Rossignol !
