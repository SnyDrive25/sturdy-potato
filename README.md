# TD 2 - Bitcoin - Développement Blockchain
#### _GROS Alexandre, GOULAMHOUSSEN Sunil_
##### _03/10/2022_

Tester le site ici : <a href="https://sunil.fr/sturdy-potato/" target="_blank">https://sunil.fr/sturdy-potato/</a>

## `PARTIE EXPLICATION DU CODE`


#### 1/ Créer un entier aléatoire pouvant servir de seed à un wallet de façon sécurisée

Pour cette partie, on génère un array vide que l'on remplie avec des valeurs aléatoires grâce à la fonction "window.crypto.getRandomValues()".
Puis on nettoie ce tableau et on transforme sa forme pour n'avoir qu'une seule ligne contenant le nombre en hexadécimal par la suite.



#### 2/ Représenter cette seed en binaire et la découper en lot de 11 bits

Cette partie est partagée en deux parties : d'une part, le passage de la seed en héxadécimal à une seed en binaire et, d'autre part, le découpage de cette seed en lots de 11 bits.
Pour la conversion on utilise un "switch case" qui associe à chaque caractère héxadécimal son équivalent en binaire.
Pour le découpage, on ajoute ce qu'on appelle le "checksum", les 4 premiers bits de la seed, à elle-même en les passant dans un hash (CryptoJS.SHA256) pour avoir une seed de 132 et ainsi pouvoir les découper en 12 lots de 11 bits chacun.



#### 3/ Attribuer à chaque lot un mot selon la liste BIP 39 et afficher la seed en mnémonique

Dans un premier temps, on transforme chaque lot binaire en décimal puis dans la liste BIP39 on récupère le mot associé à ce nombre.
Dans cette partie, nous n'avons pas pû utiliser la bibliothèque BIP39 et donc nous avons dû "copier-coller" la liste dans une variable globale (appelée "words") dans le code.


#### 4/ Permettre l’import d’une seed mnémonique

Dans cette partie, on fait le chemin inverse des parties précédentes donc on trouve les décimaux associés à chaque mots et on les transforme en binaire en mettant de côté le "checksum" (4 bits rajoutés pour pouvoir faire de lots de 11 bits).

Par le procesus inverse de tout à l'heure, nous avons cherché à retrouver la root seed grâce à notre nouvelle variable binaire de 128 bits. Cependant, cette seed nous affiche 64 premiers "bons" bits et ensuite 64 bits nuls.
_Exemple :_
- _root seed_ = `e6d561d256c4b2a036ddfe377a477314`
- _root seed retrouvée à partir de la seed mnemonique_ = `e6d561d256c4b0000000000000000000`

C'est tout ce que nous avons réussi à faire sur ce TD pour l'instant car pour la suite, nous n'avons pas encore trouvé de solutions pour extraire la master private key et le chain code à partir de la seed sans utiliser la fonction PBKDF2.




## `PARTIE INSTRUCTIONS`


A chaque étape il suffit d'appuyer sur le bouton "générer" pour valider les étapes décrites.
Arrivé à l'étape d'importation d'une seed, il faut rentrer une seed mnémonique dans l'input avant de cliquer sur le bouton "importer".

