# SQL
#### 1 - Toujours ajouter des BEGIN...END après if et where
Écrire SQL cette habitude quand on est Junior, ça te permet d'éviter beaucoup d'erreurs.
c'est comme des parenthèses en mathématique, vu l'importance.

#### 2 - éviter d'insérer les IDs (Identity) en dur
- Si qlq supprime les données de la table et reinsére les données, les Ids changent, car Identity continue par la suite. On préfère de pouvoir les récupérer par des selects:
    ```
    WHEN departement_code IN ('01' , '03')	
    THEN (select region_id from region_cyu where short_name = 'ARA')
    ```
# C#
#### 1 - Si un code marche, évite de le modifier !
Au lieu de modifier les codes que marchent déjà correctement.
On ajoute une IF en plus tant que cela est possible, même si ça rend les codes un peu plus long et moche.
