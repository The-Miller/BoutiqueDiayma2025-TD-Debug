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