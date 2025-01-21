# SAE24 - Projet Web avec Adaptations et Améliorations

## Présentation
Ce projet est développé dans le cadre de la SAE24 par Guizani Ahmed Mouadh, Groupe A2. Il s'agit de la création et de l'adaptation d'un site web en intégrant des fonctionnalités interactives et des améliorations sur le front-end et la sécurité.

## Fonctionnalités Clés

### 1. **Modifications du site web**
#### Analyse
- **Programme de base :**
  - Le site utilise un fichier contrôleur `amathController.php` qui transmet les variables à un programme Python (`Koch.py`).
  - Le programme Python `nees_carre.py` attend 4 paramètres : 
    - Hasard (valeur entre 0 et 1).
    - Hasardangle (valeur entre 0 et 1).
    - Nombre de colonnes (type int).
    - Nombre de lignes (type int).
- Une image `reponse.png` est générée par `nees_carre.py` et est liée à une variable pour être affichée.

#### Adaptation
- Une nouvelle route et un fichier `nouveau.index.twig` ont été ajoutés.
- Les utilisateurs peuvent sélectionner les 4 valeurs via une interface intuitive (glissiers).
- Les valeurs saisies sont transmises à une fonction `calculer_nees` dans `amathController.php`.
- Le programme Python `nees_carre.py` est appelé avec ces paramètres et génère une image.

### 2. **Améliorations**
- **Navbar** : Une barre de navigation stylée à l'aide de Bootstrap (thème Bootswatch).
- **Dropdown** : Ajout d'un script JavaScript pour faciliter la navigation via un menu déroulant.
- **Compte rendu** : Ajout d'une section pour afficher un compte rendu du projet.
- **Pied de page** : Intégration d'un copyright au bas des pages.

### 3. **Sécurité : Protection par mot de passe**
- **Configuration Apache** :
  - Modification du fichier `amath.conf` pour activer `AllowOverride All`.
  - Création des fichiers `.htaccess` et `.htpasswd` pour restreindre l'accès au site.
- **Test de sécurité** : Une fenêtre de login/mot de passe est maintenant présentée à l'accès.

## Installation et Lancement

### Prérequis
- Serveur web avec support PHP (Apache).
- Python3 installé sur le serveur.
- Modules Python requis (voir `requirements.txt` si disponible).

### Étapes
1. Clonez le dépôt Git :
   ```bash
   git clone https://github.com/<votre-utilisateur>/<votre-repo>.git
   ```
2. Configurez le serveur Apache :
   - Copiez le contenu dans le répertoire `/var/www/html/amath`.
   - Activez `AllowOverride All` dans le fichier `amath.conf`.
3. Installez le fichier `.htaccess` et configurez `.htpasswd` pour la protection par mot de passe.
   ```bash
   htpasswd -c /chemin/vers/.htpasswd guizani
   ```
4. Redémarrez Apache :
   ```bash
   sudo service apache2 restart
   ```
5. Accédez au site à partir du navigateur web.

## Utilisation
1. Naviguez vers la nouvelle route créée pour choisir les valeurs des paramètres.
2. Générez une image en cliquant sur le bouton.
3. Explorez les œuvres d'art générées et profitez des nouvelles fonctionnalités du site.
