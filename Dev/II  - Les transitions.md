## Le changements de fenêtre

On change de fenêtre lorsque l'ancienne fenêtre ne contient rien d'utile pour la suite du programme. 

### Fermer une Fenêtre 

- **Set Visible**
La méthode qui permet d'afficher ou non est **setVisible(boolean)**
```java
JFrame fenetre = new JFrame();
fenetre.setVisible(false);
```
Si on va réutiliser la fenêtre, pas besoin de la supprimé. Simplement, on la cache de l'env graphique. 

- **Dispose**
Sinon, pour fermer **définitivement** notre fenêtre on peu utiliser la méthode ***dispose(void);***
```java
fenetre.dispose();
```

- **Exit ?** 
On peut fermer le programme directement. 
```Java
System.exit(1);
```
### Ouvrir une fenêtre

Il est d'ailleurs préférable de créer la fenêtre à  l'avance. 
```Java
frame.setVisible(true);
```


>[!IMPORTANT]
> Le set visible ne dois JAMAIS se trouver dans le même controlelr d'où on construit la fenêtre. Ainsi, celle-ci peut-être construite à l'avance.

### Fenêtre Modale

Une fenêtre __modale__ s'affiche par dessus une autre fenêtre et bloque l'accès à celle-ci. On peut en construire une en se basant sur la classe `JDialog`. 

La classe de base des fenêtres modale est `JDialog`. (CF SAE21_2023 --> Algorithme)

## Modification de la fenêtre

On peut changer l'apparence des composantes avec un simple rafraîchissement.

Pour des modifications tierce et qui sont à faire régulièrement, on peut utiliser un `repaint` de la fenêtre. `Repaint` de la classe `JComponent`. 
### Ajouter / Supprimer
Sinon, on peut ajouter des composants avec `add` ou en retirer avec `remove`.
```java
Point point = new Point();

##Ajouter
fenetre.add(point);

##Supprimer
fenetre.remove(point);
```

> [!WARNING]
> Un composant qui à subit un `remove` ne peut plus jamais redevenir visible.

Une fois tous les changements demandés, on les appliques avec `revalidate`.

### Rafraîchir 

Pour `refresh` notre fenêtre où simplement quelques valeurs ont changés, alors on utilise `repaint` 

```Java
frame.repaint();
```


Pour modifier la position d'objets, leurs tailles ou leur nombre il faut **revalider** la fenêtre. Pour ça, on utilise `revalidate` de la classe `Component` car tout cela nécessite une nouvelle répartition de l'espace. 

```java
fenetre.revalidate();
```

`Revalidate` est un `repaint` beaucoup plus massif qui demande à la fenêtre d'ajouter les différents éléments et de remettre en place tous les nouveaux objets. 

## Modifications avec `CardLayout`

Le gestionnaire de mise en page `CarLayout` permet des transitions complètes et très rapide.

Exemple :
```Java
JFrame||JPanel conteneur = new JFrame||JPanel();
conteneur.setLayout(new CardLayout());
```

>[!IMPORTANT]
>Il faut toujours renseigner la zone dans laquelle on souhaite mettre notre éléments. Cela permet une meilleur chasse aux bugs si besoin.

Ensuite, il faut donner un nom à chaque composant.

```Java
conteneur.add(composant, "Mon composant")
//Avec Arg[0] le composant et arg[1] le nom donné à ce composant
```

L'ordre de l'ajout est important. Le dernier composant ajouté sera le seul visible.

Pour provoquer une transition, on emploie les méthodes de `CardLayout`. 
- `next`
- `previous`
- `first`
- `last`
- `show("Mon composant")`

Ces méthodes doivent êtres utilisé sur le `CardLayout`. 

>[!WARNING]
>En fait, une `JFrame` n'est pas vraiment un conteneur. En effet, elle aurait trop de rôle à jouer (appels système, interactions) donc elle donne son rôle de conteneur à un *Vrai* conteneur qu'elle se contentera d'afficher.
>
>Donc, pour avoir le conteneur de cette `JFrame`, la référence au conteneur doit être obtenue avec `getContentPane`. 