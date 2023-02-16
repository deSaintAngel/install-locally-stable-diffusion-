# install-locally-stable-diffusion-
installation local de stable diffusion

      Installation de la version 1.5 de Stable diffusion en local sur sa machine. 
      
∆ ! : pres recquis pour faire tourner sur ça machine le programme, il fait au minimum une carte graphique NVIDIA 4GB  ou AMD Radeon 4GB.
      
    • Etape  1 : Installation de Python 3.11.0
	
C’est l’IDE (environnement de développement intégré ) qui va interpréter le code pour l’exécuter. 
Rdv sur : https://www.python.org/downloads/ pour télécharger la version 3.11.0 

![adresse_python](https://user-images.githubusercontent.com/58695529/219095906-fe9e0dfa-1b96-45ac-b3fc-999ef0464cda.png)
	

∆ ! bien penser a cocher la case : add Python to path

![adresse_python2](https://user-images.githubusercontent.com/58695529/219095936-75fd4042-b0a0-4c05-bda3-eb405788a059.png)

En effet, cela va permettre d’ajouter python en variable d’environnement sur le pc, et donc de l’utiliser en ligne de commande pour la suite de l’installation. 


    • Étape 2 : Installation de Git  

c’est un système de contrôle de version open-source qui permet de suivre et de gérer les modifications apportées à un projet de manière efficace.
Rdv sur : https://git-scm.com/downloads


    • Étape 3 : installation du GIT stable diffusion 

1. Taper dans la barre de recherche la commande cmd. Pour accéder au terminal de votre ordinateur.


![adresse_cmd](https://user-images.githubusercontent.com/58695529/219095479-e35c11e6-d930-49e8-aeef-1583a4aa3237.png)


2. Après avoir créer un dossier que vous pouvez nommer « stable_diffusion », rendez vous à partir de votre terminal dans le dossier. Pour cela tapez la commande : 
cd suivie de l’adresse de votre dossier :

cd C:\Users\XXX\stable_diffusion

vous verrez alors l’adresse de votre terminal complété par l’adresse de votre répertoire 
"PS C:\Users\XXX>" devient "PS C:\Users\XXX\stable_diffusion>"

3. Vous allez maintenant cloner le git disponible en ligne dans votre espace local en tapant la commande dans le terminal : 

"git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git"

![adresse_cmd2](https://user-images.githubusercontent.com/58695529/219095639-c5315f70-5ee2-43fd-a9bc-d546e6d88570.png)


vous pourrez alors vérifier que dans votre dossier « stable_diffusion » c’est ajouter l’ensemble des codes sources  présent dans le git en ligne. 


![adresse_cmd_repertoire](https://user-images.githubusercontent.com/58695529/219095572-4b439de4-0d85-403e-b28b-e9b7268bed43.png)



Si vous n’êtes pas a l’aise avec les lignes de commandes via un terminal vous pouvez toujours recharger le zip et décompresser a la main dans le dossier que vous avez sélectionné. Mais pour la suite vous devrez quant même vous rendre dans votre dossier via le terminal. 

    • Étape 4 : Télécharger les poids du modèle. 
    
 Les « models » sont les poids entraînée du réseaux de neurones que vous allez utiliser qui sont des ficher .ckpt

∆ ! Par souci juridique, stable diffusion a ré entraîné le réseaux a partir de zéro en autant les données issus de licences privé comme par exemple Disney, certains artistes reconnue … Donc le choix du modèle entre la version 1.5 ou 2.0 va dépendre de l’usage que vous prévoyez d’effectuer. La version 2.0 sera moins pertinente en terme de résultat mais vous serez plus protégé en terme de droit que la version 1.5. 

1. vous allez donc télécharger les fichiers .ckpt via le site hugginface  https://huggingface.co/ ( il vous faut donc un compte, celui ci est gratuit l’inscription en ligne et l’acceptation des conditions vous donnera un ‘access Token’ que vous n’aurais pas a gérer. Un token est une chaîne de caractères aléatoires utilisée pour authentifier et autoriser l'accès d'une application): rendez vous donc sur le site et télécharger le fichier .ckpt : https://huggingface.co/runwayml/stable-diffusion-v1-5


![adresse_hugginface](https://user-images.githubusercontent.com/58695529/219095832-74bdd61c-07d0-47fa-872b-774066d00246.png)



2. Vous allez ensuite déplacer le fichier.ckpt téléchargé dans le repertoir : models\Stable-diffusion

C:\Users\XXX\Stable_Diffusion\stable-diffusion-webui\models\Stable-diffusion


![adresse_hugginface2](https://user-images.githubusercontent.com/58695529/219095862-bea1289b-9fa7-4c0a-8f19-448b6054425e.png)


    • Étape 5 : le GFPGan (optionnel mais recommandé pour un meilleur résultat)


Pour amélioré le rendu des visages lorsque vous allez générer des images, vous allez pouvoir utiliser un deuxième réseaux conçu pour cela. 
Rendez vous sur https://github.com/TencentARC/GFPGAN , et télécharger le modèle V1.4. 


![adresse_gpfgan2](https://user-images.githubusercontent.com/58695529/219095813-1bb023d6-37e6-440c-b35d-a4dddfb6dad1.png)

Vous allez déposer le fichier télécharger : GFPGANv1.4.pth à la racine du dossier stable-diffusion-webui créé. C:\Users\XXX\Stable_Diffusion\stable-diffusion-webui

    • Etape 6 : Télécharger les librairies python annexe pour le code

1. Dans le même dossier stable-diffusion-webui vous avez un fichier «webui-user.bat ». faites click droit modifier.

2.  Après la commande set COMMANDLINE_ARGS=, au niveau de la ligne vide surligné en jaune, vous rajoutez la commande «git pull ». Cette commande va permettre de télécharger automatiquement les dépendances nécessaire à python pour la compilation de votre programme.


 
![adresse_gitpull](https://user-images.githubusercontent.com/58695529/219095718-831be6df-d666-4cf8-9231-83cdf1275904.png)



3. Une fois la modification effectué enregistrer le fichier.
    • Étape 7 : Lancer le programme et l’installation. 

1. retourner dans le terminal et lancer la commande : « .\webui-user.bat » , qui exécutera le script.
La première exécution prendra un peut de temps car le script installe toutes les dépendances, mais les suivantes seront plus rapides. 


![adresse_commande_install](https://user-images.githubusercontent.com/58695529/219095667-c1e19d33-89ef-4095-835b-6fe48df87b6b.png)


Apres l’installation vous pouvez vous rendre a l’ULR proposé qui vous amèneras a l’interphase d’utilisation de stable diffusion via votre navigateur web. Mais ce n’est que pour l’interphase, les calcules sont effectué sur votre machine.  Pour cela vous maintenez le bouton CTRL et vous clicker sur le lien de l’url : http://127,0,01:XXXX,

∆ ! Surtout ne fermer pas le terminal, car c’est lui qui exécute les commandes. Laissez le en fond et aller sur votre page web qui à était ouvertes. 


![adresse_commande_install2](https://user-images.githubusercontent.com/58695529/219095675-c209b2d0-bff4-4e14-a139-d02cdee759d8.png)


Vous pouvez alors dans ‘txt2img’ tapez votre prompte. Pour générer votre image. Choisir votre méthode et le nombre d’images généré par lot avec le paramétrés batch count. 
Par la suite vous pouvez vous même entraîner vos propres modèles en rajoutant votre tête. D’où la fenêtre checkpoint qui vous permet de choisir les poids du réseaux. 
Dans la partie img2img, vous pourrez générer une image a partir d’une autre images, et dans la partie Extras vous pourrez modifier votre image pour par exemple augmenter la résolution ….
En cochant la case ‘restaure faces ‘, vous aller effectuer une inférence sur le réseaux GFPGan pour améliorer vos visage. 

∆ ! Il se peut que vous rencontriez des problème de saturation de la mémoire vive, pour cela vous pouvez installer le module xformers qui aidera python a gerer cotre mémoire. 
Dans le terminal utiliser la commande : pip install -U xformers

bonne créativité à vous …. 
      
