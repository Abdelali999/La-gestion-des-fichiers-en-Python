# La-gestion-des-fichiers-en-Python
La gestion des fichiers en Python implique plusieurs opérations comme la création, la lecture, l'écriture, la modification et la suppression de fichiers. Python offre des modules intégrés comme os et shutil pour manipuler les fichiers et les répertoires, ainsi que des méthodes pour gérer leur contenu.
Principales opérations sur les fichiers
A. Ouvrir un fichier
La fonction intégrée open() permet d'ouvrir un fichier. Voici les modes couramment utilisés :

'x': Create | crée un fichier, échoue si le fichier existe déjà.
'w': write | Écriture. Crée un nouveau fichier ou écrase le fichier existant.
'a': append | Ajoute les données à la fin du fichier existant.
'r': read |Lecture seule. Le fichier doit exister.
'r+': read and write | Lecture et écriture. Le fichier doit exister.
'W+': Lecture et écriture. Crée un nouveau fichier ou écrase le fichier existant.
'r+': Lecture et ajout. Ajoute les données à la fin du fichier existant.
1. crée un fichier
crée un fichier, échoue si le fichier existe déjà, vous devez utiliser les modes 'x'.

Exemple créetion :

open('exemple.txt', 'x')
1.1 Chemin relatif et chemin absolu

Chemin relatif : Le chemin relatif indique l’emplacement du fichier par rapport au script Python en cours d'exécution.
Exemple de chemin relatif :

# Fichier dans le même répertoire que le script
with open("exemple.txt", "r") as fichier:
    print(fichier.read())
Ici, le fichier exemple.txt est situé dans le même dossier que le script Python. C'est un chemin relatif.

Chemin absolu : Le chemin absolu donne l’emplacement complet du fichier, en commençant depuis la racine du système.
Exemple de chemin absolu :

# Fichier situé à un emplacement absolu
with open("/home/utilisateur/documents/exemple.txt", "r") as fichier:
    print(fichier.read())
Dans ce cas, le chemin commence depuis la racine du système (/ sur Linux/macOS, ou C:\ sur Windows) et donne la position exacte du fichier exemple.txt.

La différence entre les deux est que le chemin absolu sera toujours valide, peu importe où le script est exécuté, tandis que le chemin relatif dépend de l’emplacement du script.

2. Écrire dans un fichier
Pour écrire ou ajouter du contenu dans un fichier, vous devez utiliser les modes 'w', 'a'.

Exemple d'écriture :

fichier = open('exemple.txt', 'w')
fichier.write("Ceci est un texte exemple.\n")
Exemple pour ajouter du contenu :

fichier = open('exemple.txt', 'a')
fichier.write("Nouvelle ligne ajoutée.\n")
3. Fermer un fichier
Il est essentiel de fermer le fichier après utilisation pour libérer les ressources :

fichier.close()
4. Lire un fichier
Une fois le fichier ouvert, voici les méthodes pour lire son contenu :

read(): lire tout le fichier.
readline(): lire une seule ligne.
readlines(): lire toutes les lignes dans une liste.
Exemple :

contenu = fichier.read()   # lire tout le fichier
ligne = fichier.readline() # lire une ligne
lignes = fichier.readlines() # lire toutes les lignes
5. Utiliser un gestionnaire de contexte
Le mot-clé with est une méthode élégante et sécurisée pour manipuler les fichiers :

with open('exemple.txt', 'r') as fichier:
    contenu = fichier.read()
Manipulation avancée des fichiers
Python offre des bibliothèques comme os et shutil pour des opérations plus complexes.

Supprimer un fichier :
import os
os.remove('fichier.txt')
Renommer un fichier :
os.rename('ancien_nom.txt', 'nouveau_nom.txt')
Copier un fichier :
import shutil
shutil.copy('source.txt', 'destination.txt')
Gestion des répertoires
Créer un dossier :
import os
os.mkdir('nouveau_dossier')
Supprimer un dossier vide :
os.rmdir('dossier_a_supprimer')
Supprimer un dossier non vide :
import shutil
shutil.rmtree('dossier_non_vide')
Lister le contenu d'un dossier :
contenu = os.listdir('dossier_existant')
Naviguer dans les répertoires :
os.chdir('nouveau_dossier')
repertoire_actuel = os.getcwd()
Créer des répertoires intermédiaires :
os.makedirs('parent/enfant', exist_ok=True)
Copier un dossier :
shutil.copytree('dossier_source', 'dossier_destination')
Déplacer un dossier :
shutil.move('dossier_source', 'nouvel_emplacement/dossier_destination')
Installation des bibliothèques
Installation de colorama
pip install colorama
Installation de la bibliothèque FileMa
pip install FileMa
Utilisation de FileMa
1. Création & Suppression de fichiers
FileMa.touch('fichier.txt')  # Crée ou met à jour un fichier
FileMa.rm('fichier.txt')     # Supprime un fichier
2. Lecture & Écriture de fichiers
FileMa.nano('fichier.txt', 'w', 'Contenu')  # Écrire ou ajouter
FileMa.cat('fichier.txt')                    # Lire le contenu
3. Opérations sur les fichiers
FileMa.ren('ancien.txt', 'nouveau.txt')      # Renommer
FileMa.mv('source.txt', 'destination.txt')   # Déplacer
FileMa.copy('source.txt', 'dest.txt', 'w')   # Copier
4. Gestion des répertoires
FileMa.mkdir('dossier')        # Créer un dossier
FileMa.rmdir('dossier')        # Supprimer un dossier
FileMa.mkdirs('parent/enfant') # Créer des répertoires intermédiaires
FileMa.rmdirs('chemin_dossier') # Supprimer des répertoires récursivement
5. Navigation & Liste des répertoires
FileMa.cd('chemin')              # Changer de répertoire
FileMa.pwd()                     # Afficher le répertoire actuel
FileMa.ls('chemin')              # Lister le contenu
6. Métadonnées des fichiers
FileMa.istime('nom_fichier')     # Heure d'accès
FileMa.size('nom_fichier')       # Taille du fichier
7. Informations système
FileMa.get_info()                # Variables d'environnement
FileMa.get_path()                # Chemins des exécutables
Cet aperçu vous offre une vue d'ensemble sur la gestion des fichiers en Python ainsi que sur l'utilisation de la bibliothèque FileMa.
