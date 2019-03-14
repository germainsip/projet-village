# UML VillageGreen

***

## Cas d'utilisation

```plantuml
skinparam handwritten true
skinparam usecase {
  BackgroundColor cornflowerblue
  bordercolor cornflowerblue
  fontColor white
}
left to right direction
actor Utilisateur as U 
actor Admin as A
actor Commercial as C
U-->(consultation catalogue)
U-->(consulter et modifier son panier)
U-->(Effectuer une commande)
U-->(Valide sa commande)
C<|-U
C-->(Edition fiche client)
C-->(Catalogue fournisseur)
A<|-C
A-->(Edition fiche commerciaux)
A-->(Consultation statistiques des ventes)
```

***

## Description des cas d'utilisations

### Consultation catalogue
> **prérequis:** _Aucun_


- L'utilisateur clique sur "Accès direct à la boutique"
- L'utilisateur peut voir les produits de toutes les catégories
- L'utilisateur peut afficher le détail du produit et son prix HT
- L'utilisateur peut ajouter directement des produits au panier
- L'utilisateur peut consulter son panier

***

### Effectuer une commande
> **prérequis:** _L'utilisateur possède un compte client_

- L'utilisateur effectue une selection de produits dans son panier
- L'utilisateur enregistre son panier
- L'utilisateur se connecte et valide l'enregistrement du panier
- L'utilisateur vérifie ses coordonnées de livraison et de facturation
- Validation de la commande (cf: Validation commande).

***

## Diagramme de séquence

``` plantuml
skinparam participant {
  BackgroundColor cornflowerblue
  bordercolor cornflowerblue
  fontColor white
}
skinparam actor {
  BackgroundColor cornflowerblue
  bordercolor cornflowerblue
  fontColor white
}
actor Utilisateur as U
Participant System as S
Participant DataBase as D
U->S : clique sur l'accès direct à la boutique
activate S
S->D : récupère la liste des produits et l'adresse des images
activate D
D-->S : renvoie la liste des produit et adresse des images
destroy D
S-->U : affiche le catalogue produits
deactivate S
U->S : ajoute des produits à son panier
activate S
S-->U : rend disponible le compte d'article et l'accès au panier
note right : enregistrement du panier dans les cookies

deactivate S
U->S : enregistre son panier
S-->U : affiche la page de connection
U->S : utilisateur se connecte
activate S
S->D : recherche de l'utilisateur dans la table users
activate D
alt l'utililisateur a un compte
D-->S : valide l'existence de l'utilisateur et donne son type
S->D : enregistre la commande (en cours)
else l'utilisateur n'éxiste pas
D-->S :l'utilisateur n'est pas inscrit
S-->U : Affiche la page d'inscription
U->S : inscrit ses coordonnées
S->D : inscrit l'utilisateur dans la base
D-->S : valide l'existence de l'utilisateur et donne son type
S->D : enregistre la commande (en cours)
destroy D
deactivate S
end
S->U : demande la validation de la commande
U->S : Valide sa commande


```
