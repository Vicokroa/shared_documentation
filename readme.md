# Commissionaire de transport 

* date butoire février
* Pas de commande en Janvier
* Pas de CDT rétroactif
* Lien camid à conserver
* Conserver un fonctionnement alternatif tant que qu'on n'est pas payé directement par le CAMID
* Comment le CAMID va payer ? Chorus ? 


---


# Scénarii à mettre en place pour continuer à developper et tester le CDT pendant la phase d'exploitation GDF.

1. branche commune
    1. Booléen global + vérification d'un déposit
        * Le passage de GDF vers CDT se fait sans mise en prod ni script de migration des commandes militaires
        * Test constant de la stabilité du site sur deux environnement distincts
        * PPROD iso PROD
        * Machine spécifique pour la recette de CDT
        * Une seule branche commune permet de limiter les problèmes de commit / merge puisque DEV et LEGACY = emoovz_minarm
1. Deux branches     
    1. Production sans séparation technique
        * Une branche bug-fix + évol gdf (emmovz-ged)
        * Une branche evol CDT (emoovz_minarm) 
        * Rigulièrement faire des mergze de emoovz_minarm vers emmovz-ged afin de garantir un code le plus identique possible
        * Si service séparés : faire manuellement le merge de celui-ci
    1. Production avec sépaation technique
        * Une branche bug-fix + évol gdf (emmovz-ged)
        * Une branche evol CDT (emoovz_minarm) 
        * Rigulièrement faire des mergze de emoovz_minarm vers emmovz-ged afin de garantir un code le plus identique possible
        * Faire deux fois le service pour GDF (emmovz-ged) en revanche le merge est en automatique sauf dans le cas où nous sommes en CDT
1. Mode altéré
    * 1 branche fusionnant emoovz-ged et emoovz_minarm
    * Comportement du CDT adapté au cas por cas pour resté iso GDF
    * Surcout en developpement pour adapter une fonctionnalité CDT provisoirement au GDF
    * Le fonctionnement à très peu de chance d'être ISO GDF
1. Scénario bisounours
    * Le comportement actuel est figé pour 6 mois
    * Nouveau projet mis en route avec les phases de test / recette / etc mise en plce pour le fonctionnement CDT