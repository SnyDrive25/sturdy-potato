# sturdy-potato
TD 2 - Bitcoin - Développement Blockchain - GROS Alexandre, GOULAMHOUSSEN Sunil


PARTIE EXPLICATIONS DU CODE


1/ Créer un entier aléatoire pouvant servir de seed à un wallet de façon sécurisée

Pour cette partie, on génère un array vide que l'on remplie avec des valeurs aléatoires grâce à la fonction "window.crypto.getRandomValues()".
Puis on nettoie ce tableau et on transforme sa forme pour n'avoir qu'une seule ligne contenant le nombre en hexadécimal par la suite.



2/ Représenter cette seed en binaire et le découper en lot de 11 bits

Cette partie est partagée en deux parties : d'une part, le passage de la seed en héxadécimal à une seed en binaire et, d'autre part, le découpage de cette seed en lots de 11 bits.
Pour la conversion on utilise un "switch case" qui associe à chaque caractère héxadécimal son équivalent en binaire.
Pour le découpage, on ajoute ce qu'on appelle le "checksum", les 4 premiers bits de la seed, à elle-même en les passant dans un hash (CryptoJS.SHA256) pour avoir une seed de 132 et ainsi pouvoir les découper en lots de 11 bits chacun.



3/ Attribuer à chaque lot un mot selon la liste BIP 39 et afficher la seed en mnémonique

Dans un premier temps, on transforme chaque lot binaire en décimal puis dans la liste BIP39 on récupère le mot associé à ce nombre.
Dans cette partie, nous n'avons pas pû utiliser la bibliothèque BIP39 et donc nous avons dû "copier-coller" la liste dans le code.


4/ Permettre l’import d’une seed mnémonique

Dans cette partie, on fait le chemin inverse des parties précédentes donc on trouve les décimaux associés à chaque mots et on les transforme en binaire en mettant de côté le "checksum" (4 bits rajoutés pour pouvoir faire de lots de 11 bits).

C'est tout ce que nous avons réussi à faire sur ce td car pour la suite, nous n'avons pas trouvé de solutions pour extraire la master private key et le chain code à partir de la seed sans utiliser la fonction PBDF2.




PARTIE INSTRUCTIONS


A chaque étape il suffit d'appuyer sur le bouton "générer" pour valider les étaped décrites.
Arrivé à l'étape d'importation d'une seed, il faut rentrer une seed mnémonique dans l'input avant de cliquer sur le bouton "importer".

<<<<<<< HEAD
=======




>>>>>>> 8d36235a0153a2aeb71c33d6c04fc1473364d20e
