# VillageGreen

> Boutique d'instrument de musique en ligne avec interface d'administration

## Création de la base

```php
# Affichage de la table appro
# ------------------------------------------------------------

DROP TABLE IF EXISTS `appro`;

CREATE TABLE `appro` (
  `appro_fournisseur_id` int(11) NOT NULL,
  `appro_produit_id` int(11) NOT NULL,
  `appro_prix_achat` decimal(7,2) NOT NULL,
  `appro_date_com` date NOT NULL,
  `appro_date_livr` date NOT NULL,
  `appro_qtite` int(11) NOT NULL,
  `appro_id` int(11) NOT NULL,
  PRIMARY KEY (`appro_id`),
  KEY `appro_fournisseur_id` (`appro_fournisseur_id`),
  KEY `appro_produit_id` (`appro_produit_id`),
  CONSTRAINT `appro_ibfk_1` FOREIGN KEY (`appro_fournisseur_id`) REFERENCES `fournisseur` (`fournisseur_id`),
  CONSTRAINT `appro_ibfk_2` FOREIGN KEY (`appro_produit_id`) REFERENCES `produit` (`produit_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


```

***
## Uml

### Cas d'utilisation

![Class Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/germainsip/projet-village/master/puml/cas_util.puml)

***

### Description des cas d'utilisations

#### Consultation catalogue

> **prérequis:** _Aucun_


- L'utilisateur clique sur "Accès direct à la boutique"
- L'utilisateur peut voir les produits de toutes les catégories
- L'utilisateur peut afficher le détail du produit et son prix HT
- L'utilisateur peut ajouter directement des produits au panier
- L'utilisateur peut consulter son panier

***

#### Effectuer une commande

> **prérequis:** _L'utilisateur possède un compte client_

- L'utilisateur effectue une selection de produits dans son panier
- L'utilisateur enregistre son panier
- L'utilisateur se connecte et valide l'enregistrement du panier
- L'utilisateur vérifie ses coordonnées de livraison et de facturation
- Validation de la commande (cf: Validation commande).

***

### Diagramme de séquence

![Sequence Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/germainsip/projet-village/master/puml/sequence1.puml)
