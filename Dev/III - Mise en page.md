	
## 1. Gestionnaire `GridBagLayout`

Le gestionnaire de mise en page GridBagLayout est plus complexe mais plus versatile  que les gestionnaires basique. 

Ex1. 
![[Pasted image 20230920101750.png]]

On affecte le gestionnaire ai conteneur.

Ex2.
```java 
conteneur.setLayout(new GridBagLayout());
```

Pour ajouter un composant au conteneur, il faut lui associer un objet de la classe `GridBagConstraints`.

Ex3. (Basé sur l'Ex1, petit rectangle)
```java
contrainte = new GridBagConstraints();
contrainte.gridx = 1; // Quelle colone
contrainte.gridy = 0; // Quelle ligne
contrainte.gridwidth = 1; //Nombre de ligne qu'on veut utiliser ?
contrainte.gridheight = 1; //Nombre de Colone qu'on veut utiliser ?


contrainte.fill = GridBagConstraints.NONE; //Gère le remplissage de l'elt
// None, Vertical, Horizontal, Both

contrainte.anchor = GridBagConstraint.SOUTH; //Gère la position du component
// rose des vents : CENTER, NORTH, SOUTH, EAST, WEST, ...

contrainte.insets = new insets(5,5,5,5); //Marges exprimé en pixel 

contrainte.weightx = 0.1f; 
contrainte.weighty = 0.0f;
//Si le poids est 0, c'est que la taille préféré est déjà celle qu'on veut
//Sinon, plus l'on met une grande valeurs, alors on augmente la taille.

contrainte.add(composant, contrainte);
```

l'Objet contrainte peut être réutilisé pour les composants suivants, mais il vaut mieux écrire à nouveaux les 9 affectations pour chaque composants.

### 2. Interface pré-existantes

**1. JFileChoser**

Cette classe permet une sélection de fichiers à l'aide d'une interface déjà construite et familière.

Son comportement change suivant qu'il s'agit d'une ouverture ou d'une sauvegarde.

!! Attention au répertoire affiché par défaut. 

**2. JOptionPane**

Dans cette classe, on trouve une variété d'interfaces "pop.up"

```java
String reponses = JOptionPane.showInputDialog("Login :");
```
