## Bibliothèque MariaDB
**SGBD** : Système de gestions de base de données.

Pour exploiter une bibliothèque (en général), il faut déposer ses fichiers dans un emplacement de notre choix. 

Le Chemin de cet emplacement est ensuite ajouté au "Classpath" pour la compilation de l'exécution. 

Cette liste de chemin peut être spécifié par la variable d'environnement `CLASSPATH` ou par l'option `-cp`. 

Dans le cas du pilote de MariaDB, nous n'utiliserons pas directement ses classes, donc nous n'avons pas besoin d'importer ses packages $ ni de changer le Classpathlors de la compilation. 

Pour s'assurer que le pilotes est bien disponible, on peut le tester.
```java
Class.forName("org.mariadb.jdbc.Driver"); 
/* Relève une ClassNotFOundException*/
```
## Connexion au SGBD

On établit une connexion avant de pouvoir soumettre des requêtes.

```java
Connection conn = DriverManager.getConnextion("jdbc:mariadb://dwarves.iut-fbleau.fr/bob", "Bob", "p@ssw0rd");
```

EN cas de problème, on obtient une SQL Exception. 
## Soumettre une requête 

On prépare une requête avant de l'exécuter afin d'éviter les injections.

```Java
PreparedStatement req = con.prepareStatement("INSERT INTO Mesure(valeurs) VALUES (?)");
req.setInt(1, 72);
req.execute.update();
req.setInt(1, 33);
req.execute.update();
```

## Parcourir les résultats

Pour que les requêtes qui produisent des résultats, on change de méthode.
```java
ResultSet rs = req.executeQuery();
```
Cet objet contient un _curseur_ qui sélectionne une ligne de résultat. La position initial est "avant la première ligne". Pour bouger le curseur, on emploie
- Next : Prochaine ligne
- Previous : Ligne précédente
- First : Première ligne
- Last : Dernière ligne
- Move : Ligne souhaité

Le plus conseillé est d'utilisé "Next"

```java
final int VALEUR = 1;

while(rs.next()){
	System.out.println(rs.getInt(VALEUR));
}
```

## Nettoyage

Il faut fermer les objets créés quand on ne s'en sert plus.

Les objets dependent les uns des autres: tant qu'on ne ferme pas un PreparedStatement, la Connection est bloquée.

Fermer la connection ferme le PreparedStatement

!!! La connexion doit être fermée dans tous les cas. 

