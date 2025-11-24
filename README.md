# Boubacar NIANG
# Master 2 - GLSI

# Boutique Diayma

# Question 1 – Récupérer et exécuter le code dans Visual Studio 
# j’ai récupéré et exécuté l’application fournie dans le sujet via clonage depuis Github avec le lien fourni.
# Une fois l’opération terminée, Visual Studio a ouvert automatiquement la solution associée.
# Exécution de l’application en mode Débogage, l’application a pu être compilée avec succès.
# Le navigateur s’est ouvert automatiquement sur l’URL locale de l’application (http://localhost:60000/), ce qui confirme que le lancement de l’application est réussi.
# Conformément au sujet, la fenêtre d’avertissements  affichée au démarrage a été simplement fermée, sans interrompre l’exécution de l’application.

# Question 2 – Quels sont les projets de la solution ?
# La solution Visual Studio fournie contient un unique projet : Diayma, une application Web ASP.NET Core MVC.

# Question 3 – Quelle est la version du SDK .NET utilisée ?
# Pour déterminer la version du SDK .NET utilisée, j’ai vérifié l’environnement .NET installé sur la machine à l’aide de la commande : dotnet --list-sdks
# Cette commande affiche les SDK disponibles, en l’occurrence j'ai :
# .NET SDK 8.0.416
# .NET SDK 10.0.100
# Le projet Diayma a été analysé via son fichier Diayma.csproj, dans lequel le framework ciblé est :
# <TargetFramework>netcoreapp2.1</TargetFramework>
# Ainsi, même si le projet cible le framework .NET Core 2.1, la compilation est réalisée à l’aide des SDK récents (versions 8 et 10) installés sur la machine.

# Question 4 – Installez le SDK
# Le SDK .NET (8.0.416) ainsi que les runtimes .NET Core 2.1 ont été installés et vérifiés via les commandes dotnet --list-sdks et dotnet --list-runtimes, ce qui permet désormais de compiler et d’exécuter le projet Diayma dans Visual Studio 2026.

# Question 5 – Créez votre propre dépôt GitHub pour y stocker le code
# le dépot Github a été créé et le code stocké, accessible à l’adresse suivante : https://github.com/The-Miller/BoutiqueDiayma2025-TD-Debug

# Question 6 – Explorez l’application. Signalez 2 bugs trouvés ?
# Bug 1 : Problème de sélection de la langue espagnole
# L’application propose un menu de sélection de langue avec trois choix : Anglais, Français et Espagnol. Lorsque l’utilisateur sélectionne Anglais ou Français, l’interface s’affiche correctement dans la langue choisie. En revanche, lorsque l’utilisateur sélectionne Espagnol, l’interface bascule en français.
# Bug 2 : Erreur dans le calcul du total du panier
# Lorsqu’on ajoute plusieurs articles au panier, dont un article par exemple article2, le calcul de la somme totale du panier est incorrect. Le prix de article2 n’est pris en compte qu’une seule fois, même si plusieurs exemplaires de cet article sont ajoutés.

# Question 7 - Placez un point d’arrêt sur les lignes suivantes du code : a)CartSummaryViewComponent ligne 12 / b)ProductController ligne 15 / c)OrderController ligne 17 / d)CartController ligne 15 / e)Startup ligne 20
# Au niveau des lignes demandés, on a mis les points d’arrêt en faisant F9 sur chaque ligne concernée dans Visual Studio.

# --------------------------------------------------------------------------------------------------------------------------
# --------------------------------------------------------------------------------------------------------------------------
# --------------------------------------------------------------------------------------------------------------------------
# Question 8 - Quels sont les namespaces, classes et méthodes visités avant l’affichage des produits sur l’écran d’accueil de votre navigateur ? Choisissez le mode approprié selon le contexte, "Pas à pas détaillé", "Pas à pas principal" ou "Pas à pas sortant". Vos réponses doivent être détaillées dans le fichier README du dépôt.
# Lors du lancement de l’application en mode Débogage et de la navigation vers la page d’accueil affichant la liste des produits, l’exécution passe par plusieurs composants du framework et de l’application.

# Ci-dessous, le chemin observé est détaillé avec, pour chaque étape, le namespace, la classe, la méthode et le mode de pas à pas utilisé.

# ============================================
# 1. DÉMARRAGE DE L’APPLICATION
# ============================================

# Namespace : P2FixAnAppDotNetCode
# Classe : Startup
# Méthode : Startup(IConfiguration configuration)
# Le runtime instancie Startup et initialise la configuration.
# Mode utilisé : Pas à pas principal

# Namespace : P2FixAnAppDotNetCode
# Classe : Startup
# Méthode : ConfigureServices(IServiceCollection services)
# Enregistrement des services
# Mode utilisé : Pas à pas principal

# Namespace : P2FixAnAppDotNetCode
# Classe : Startup
# Méthode : Configure(IApplicationBuilder app, IHostingEnvironment env)
# Mise en place du pipeline HTTP
# Mode utilisé : Pas à pas principal

# ============================================
# 2. ROUTAGE & APPEL DU CONTRÔLEUR
# ============================================

# Route par défaut → ProductController.Index()

# Namespace : P2FixAnAppDotNetCode.Controllers
# Classe : ProductController
# Méthode : ProductController(IProductService, ILanguageService)
# Injection
# Mode utilisé : Pas à pas détaillé

# Namespace : P2FixAnAppDotNetCode.Controllers
# Classe : ProductController
# Méthode : Index()
# Mode : Pas à pas détaillé

# ============================================
# 3. COUCHE SERVICE & ACCÈS DONNÉES
# ============================================

# Namespace : P2FixAnAppDotNetCode.Models.Services
# Classe : ProductService
# Méthode : GetAllProducts()
# encapsulation métier + appels au repository.
# Mode : Pas à pas détaillé

# Namespace : P2FixAnAppDotNetCode.Models.Repositories
# Classe : ProductRepository
# Méthode : GetAllProducts()
# retourne la liste des produits depuis la source de données.
# Mode : Pas à pas principal
# Retour vers ProductController.Index()
# Mode : Pas à pas sortant

# ============================================
# 4. RENDU DE LA VUE
# ============================================

# Namespace : P2FixAnAppDotNetCode.Components
# Classe : CartSummaryViewComponent
# Méthode : Invoke()
# affichage du résumé du panier.
# Mode : Pas à pas principal

# Ce chemin couvre les couches : démarrage, contrôleur, service, repository, vue.
# --------------------------------------------------------------------------------------------------------------------------
# --------------------------------------------------------------------------------------------------------------------------
# --------------------------------------------------------------------------------------------------------------------------

# Question 9 - Déployez votre solution sous forme d’exécutable Windows.
# La solution a été publiée sous forme d’exécutable Windows à l’aide de l’assistant de publication de Visual Studio :
# 1. Dans l’Explorateur de solutions, le projet `Diayma` a été sélectionné puis la commande **Publier…** a été utilisée.
# 2. Un profil de publication de type **Dossier** a été créé, avec comme cible un répertoire local `C:\Publish\Diayma`.
# 3. Dans les paramètres de publication, le mode de déploiement a été configuré en **Self-contained** avec le runtime cible **`win-x64`**, afin de générer un exécutable Windows autonome.
# 4. Après publication, Visual Studio a généré un fichier `Diayma.exe` dans le dossier de sortie. L’exécution de cet exécutable lance le serveur Kestrel et permet d’accéder à l’application via une URL locale (`http://localhost:5000`) dans le navigateur.

# Question 10 - Fournir un lien drive Google, Onedrive etc. à l’exécutable ci-dessus.
# Voici le lien drive : https://drive.google.com/file/d/1I88RR4lqGiLiUcfTFaTTBtXou3kv5inK/view?usp=drive_link

# Question 11 - Optionnel
