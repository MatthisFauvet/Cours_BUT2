## Le changements de fenêtre

On change de fenêtre lorsque l'ancienne fenêtre ne contient rien d'utile pour la suite du programme. 

La méthode qui permet d'afficher ou non est **setVisible(boolean)**
```java
JFrame fenetre = new JFrame();
fenetre.setVisible(true);
```

Sinon, pour fermer définitivement notre fenêtre on peu utiliser la méthode **dispose(void);**
```java
fenetre.dispose();
```


On peut aussi garder la fenêtre ouverte mais en la rendant inactive en ouvrant une **fenêtre modale**

La classe de base des fenêtres modale est **JDialog**. (CF SAE21_2023 --> Algorithme)

## Modification de la fenêtre

On peut changer l'apparence des composantes avec un simple rafraîchissement.

Pour des modifications tierce et qui sont à faire régulièrement, on peut utiliser un **repaint** de la fenêtre. Repaint de la classe **JComponent**. 

Pour changer leurs positions, leurs tailles ou leur nombre il faut **revalider** la fenêtre. Pour ça, on utilise **revalidate** de la classe **Component**.
```java
fenetre.revalidate();
```

Sinon, on peut ajouter des composants avec **add** ou en retirer avec **remove**.
```java
Point point = new Point();

##Ajouter
fenetre.add(point);

##Supprimer
fenetre.remove(point);
```

Une fois tous les changements demandés, on les appliques avec **revalidate**.

## Modifications avec CardLayout

Un conteneur géré par **CardLayout** donne à tous ses enfant la totalité de sa surface. Cependant, il n'en affiche qu'un seul. 

On ajoute un enfant au conteneur avec une constante de type String. 