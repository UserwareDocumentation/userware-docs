← [Retour à Général](/docs/9/1)
# Guide d'installation de l'environnement de développement OpenSilver
Vous trouverez ci-dessous un document détaillé sur la configuration de votre environnement de développement lors de l'utilisation d'OpenSilver.

## Table des matières
1. Installation de la dernière version de Visual Studio 2022
2. Installation du plugin OpenSilver pour Visual Studio
3. Téléchargement du SDK .NET
4. Installation des outils WebAssembly pour .NET
5. Téléchargement et installation du module de réécriture d'URL IIS

## 1. Installation de la dernière version de Visual Studio 2022
### Instructions étape par étape :
1. **Accéder au site Web de Visual Studio :**
   - Ouvrez votre navigateur Web et rendez-vous sur le site officiel de Visual Studio : [Site officiel Visual Studio](https://visualstudio.microsoft.com/vs/)
2. **Télécharger l'installateur :**
   - Cliquez sur le bouton "Télécharger" pour Visual Studio 2022 Community Edition, qui est gratuit pour les développeurs individuels, les projets open-source, la recherche académique, l'éducation et les petites équipes professionnelles.
3. **Exécuter l'installateur :**
   - Une fois le téléchargement terminé, exécutez le fichier d'installation depuis votre dossier Téléchargements.
4. **Installer Visual Studio 2022 :**
   - Lorsque vous y êtes invité, sélectionnez les charges de travail que vous souhaitez installer. Assurez-vous d'avoir au moins sélectionné : "Développement .NET Desktop" et "Développement ASP.NET et web".
   - Cliquez sur "Installer" et attendez que l'installation soit terminée.
5. **Terminer la configuration :**
   - Après l'installation, lancez Visual Studio et connectez-vous avec votre compte Microsoft (facultatif mais recommandé pour la synchronisation des paramètres).

## 2. Installation du plugin OpenSilver pour Visual Studio
### Instructions étape par étape :
1. **Téléchargement :**
   - Obtenez-le depuis la [page de téléchargement Opensilver](https://forms.opensilver.net/download.aspx)
2. **Installation :**
   - Fermez toutes les instances de Visual Studio en cours d'exécution
   - Double-cliquez dessus et suivez les étapes
   - Assurez-vous de sélectionner "Visual Studio 2022" comme version de VS pour laquelle installer le plugin
   - Lorsque vous redémarrerez Visual Studio 2022, le plugin OpenSilver sera installé

## 3. Téléchargement du SDK .NET
### Instructions étape par étape :
1. **Accéder à la page de téléchargement .NET :**
   - Accédez à la page de téléchargement officielle .NET : [Télécharger .NET](https://dotnet.microsoft.com/en-us/download)
2. **Sélectionner le SDK approprié :**
   - Choisissez le SDK en fonction de votre système d'exploitation Windows
3. **Télécharger et installer le SDK :**
   - Cliquez sur le lien de téléchargement et exécutez l'installateur une fois le téléchargement terminé

## 4. Installation des outils WebAssembly pour .NET
### Instructions étape par étape :
1. **Ouvrir une invite de commande ou un terminal :**
   - Sous Windows, vous pouvez rechercher "cmd" ou "Invite de commandes" dans le menu Démarrer
2. **Installer les outils WebAssembly :**
   - Tapez la commande suivante et appuyez sur Entrée :
     ```bash
     dotnet workload install wasm-tools
     ```

## 5. Téléchargement et installation du module de réécriture d'URL IIS
### Instructions étape par étape :
1. **Visiter la page de téléchargement du module de réécriture d'URL IIS :**
   - Accédez à la page officielle Microsoft IIS pour télécharger le module de réécriture d'URL : [Page officielle du module de réécriture d'URL IIS](https://www.iis.net/downloads/microsoft/url-rewrite)
2. **Télécharger le module :**
   - Sélectionnez la version appropriée pour votre système et cliquez sur le lien de téléchargement
3. **Installer le module :**
   - Exécutez l'installateur téléchargé et suivez les instructions à l'écran pour installer le module
4. **Vérifier l'installation :**
   - Ouvrez le Gestionnaire IIS depuis le Panneau de configuration ou en recherchant dans le menu Démarrer pour vous assurer que le module de réécriture d'URL est installé