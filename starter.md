# Configuration d'une Clé SSH sur GitLab

## 1. Installer Git Bash (Windows uniquement)

Si vous utilisez **Windows**, il est recommandé d'installer **Git Bash** pour exécuter les commandes Git et SSH plus facilement.

1. **Téléchargez Git pour Windows** depuis [gitforwindows.org](https://gitforwindows.org/).
2. **Installez-le** en suivant les instructions par défaut.
3. **Ouvrez Git Bash** en recherchant "Git Bash" dans le menu Démarrer.

Vous pouvez maintenant continuer avec la configuration SSH.


## 2. Vérifier si une Clé SSH Existe

Avant de générer une nouvelle clé, vérifions si une clé SSH est déjà présente sur votre système :

```bash
ls ~/.ssh/
```

Si un fichier `id_edxxxx.pub` existe, passez directement à l'étape **4. Ajouter la Clé SSH à GitLab**.



## 3. Générer une Nouvelle Clé SSH

Si aucune clé n'est trouvée, générez-en une nouvelle avec la commande suivante :

```bash
ssh-keygen
```

- Appuyez sur **Entrée** pour accepter l'emplacement par défaut (`~/.ssh/idxxxx.pub`).
- Vous pouvez choisir d'ajouter une passphrase pour plus de sécurité ou laisser vide.

## 4. Ajouter la Clé SSH à GitLab

### Copier la Clé Publique

Affichez et copiez votre clé publique :

```bash
cat ~/.ssh/id_xxxxxx.pub
```

Le résultat sera une ligne ressemblant à ceci :

```
ssh-edxxxx AAAAC3NzaC1lZDI1NTE5AAAAIFrhNzV969+O1zTNuUn3SS/5zkXeGl1KvUTapLWUxmCu ridi@ridi-Nitro-AN515-57
```

Copiez **tout** ce contenu.

### Ajouter la Clé sur GitLab

1. Rendez-vous sur **GitLab**.
2. Allez dans **Preferences** > **SSH Keys**.
3. Collez votre clé publique dans le champ **Key**.
4. Cliquez sur **Add key**.



## 5. Utiliser Git avec SSH pour cloner le depot localement 

- **Lorsque vous clonez un dépôt, utilisez l'URL SSH :**

```bash
git clone git@gitlab.com:nom-utilisateur/nom-du-repo.git
```


- **Rendez-vous  à l'interieur du dépot récemment cloné**
```bash
cd fusionforks  
```


- **En suite, entrez vos configurations**

```bash
git config --local user.name "Votre nom complet "
git config --local user.email "xxxxx@crosemont.qc.ca"
``` 

- **Basculez sur la branche frontend du projet**

```bash
git checkout frontend
```

faites un test et assurez-vous d'etre sur la branche frontend, ensuite vous pouvez travailer.

```bash 
git branch # verification de la branche 
```

