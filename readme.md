# VillageGreen

https://dev.amorce.org/gsipiere/village/

> Boutique d'instrument de musique en ligne avec interface d'administration
> Ce projet est le file rouge proposé pour l'obtention de mon titre de Concepteur Développeur d'applications

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

![sequence](https://www.plantuml.com/plantuml/svg/0/lPH1ajem44NtFeLs90ikaCNKPC81KaMHVICtHa6Md6w92PNANR8Spi75yeKn6CRRP3D5gRjV__ybpxCcafHRRvH_P0wMAzsvq95GQ_0tEUiw2idygenv8Rjh9EPGVua-Yh5HmiR7LvQrpuo6TPIQnKuNDp6aVkvrwn9NlqURo2QS_uiTFNcLd7TAYRCOKhEglewiBG-Qk2tdoxlp1ILw8ULIMLIh-TFIV3BME-Ha520_8sjFRsfg9soJEVqndg0lfz9IDhizLeAwd3yjC2kdeytTwKsuD48GYZMhwIJMsIKrd0gq5bRjAwwbXlM6MbIBUQz3EEoZcmOLpWG5FvF40o1BG5Q0q6RZx1OGDXPcVMnWRL23_f65Yttw3diFgk5ROy1h2OxbtdQ_1bfhXAHT36xj-tMnxGfdTiuR1xtrFa_A0on4D8bhjWaO3i8Dl0gtZEkfXovJKr105TIuSt0wAVqsFfRxBWf2fIaEGGi1z-fY611vz8pqsZ1vrGoO5210VZOUxDMIILIooCfoTy7aqp1mUx8cXqjarmUm9-_ERFvPxXzVxljL2BKk6i-6qw7ZGTue2oW1kQM0wGzSrcJHZnLxVQI5sUbuteM4TD3ns88tLih61RNYqZNVpu_vplgERfplPGZPdkzIYlZJ4HTwaJtKfmDTurlzN_7SlgMxfuQ7NXZ5SCtz401dBLICclgEEFZ-relLKQMgdW73F-Q_ "sequence")
