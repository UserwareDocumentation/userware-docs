# Guide du Développeur OpenSilver : Migration WPF

Ce guide est conçu pour les développeurs WPF souhaitant migrer leurs applications vers OpenSilver. OpenSilver est un puissant framework qui permet de transformer des applications basées sur XAML en environnements web modernes, en implémentant parfaitement l'architecture et les paradigmes de développement principaux de WPF dans un contexte web. Il maintient notamment le support de l'architecture basée sur CustomControl de WPF tout en permettant des applications web haute performance via la technologie WebAssembly.

## Table des Matières

1. Vue d'ensemble
2. Architecture Principale
3. Contrôles Personnalisés
4. Architecture MVVM
5. Gestion des Ressources
6. Intégration avec la Plateforme Web
7. Différences par rapport à WPF et Stratégies de Migration
8. Stratégie et Processus de Migration
9. Configuration de l'Environnement de Développement
10. Communauté et Ressources

## 1. Vue d'ensemble

OpenSilver, qui a commencé comme une alternative moderne à Silverlight, a migré avec succès de nombreuses applications legacy dans des environnements web à travers le monde. C'est une solution puissante qui permet aux applications basées sur XAML et .NET de fonctionner dans des navigateurs web modernes. Des applications provenant de diverses plateformes, y compris WPF, Xamarin, UWP, WinUI 3, .NET MAUI, Uno Platform et AvaloniaUI, peuvent être migrées vers le web tout en maintenant une grande compatibilité.

**Principaux Différenciateurs**

* Performance Native Basée sur WebAssembly
* Implémentation de l'Architecture CustomControl de WPF
* Intégration Flexible entre XAML et Technologies Web
* Support de la Méthodologie de Développement Entreprise
* Implémentation des Animations de Niveau WPF

Grâce à la technologie WebAssembly, OpenSilver offre une performance proche du natif, gérant efficacement des logiques métier complexes et le traitement des données. Cet avantage est particulièrement visible dans les applications d'entreprise à grande échelle.

L'architecture CustomControl de WPF a été parfaitement implémentée dans l'environnement web. Toutes les fonctionnalités, y compris la personnalisation de ControlTemplate, les parties de template et les états visuels, sont entièrement prises en charge, permettant une implémentation identique de structures et d'interactions UI complexes.

L'intégration entre XAML et les technologies web est très flexible. Les éléments HTML peuvent être combinés naturellement avec les contrôles XAML, et les interactions avec les styles CSS et le JavaScript se font sans heurts. Les systèmes de mise en page puissants de WPF, comme Grid, StackPanel et DockPanel, peuvent être utilisés tels quels.

Les modèles de développement d'applications d'entreprise essentiels, comme le pattern MVVM, l'injection de dépendances, la distribution des projets et la modularisation des contrôles, sont entièrement pris en charge. Cela garantit la maintenabilité et la scalabilité des projets à grande échelle.

Les puissantes capacités d'animation de WPF sont fidèlement implémentées dans l'environnement web. Des éléments d'animation comme Storyboard, KeyFrame et Timeline sont fournis à un niveau élevé sans chutes de frame, permettant des interfaces utilisateurs fluides et dynamiques.

OpenSilver va au-delà d'un simple outil de migration ; c'est un véritable framework d'application web de niveau entreprise qui implémente parfaitement les technologies et l'architecture principales basées sur XAML de la plateforme WPF dans un environnement WebAssembly. Un des grands avantages est la possibilité d'utiliser l'architecture CustomControl de WPF telle quelle, permettant une migration fluide même pour des applications très complexes.

## 2. Architecture Principale

OpenSilver implémente l'architecture principale de WPF dans l'environnement web. Utilisant la technologie WebAssembly, il offre des performances proches du natif et permet aux développeurs d'utiliser l'environnement de débogage de Visual Studio, offrant ainsi une expérience de développement familière pour les développeurs WPF.

**Caractéristiques Architecturales**

* Structure de Projet WPF Native
* Système de Routage SPA
* Pattern d'Architecture MVVM
* Framework d'Injection de Dépendances
* Structure de Distribution des Projets
* Modularisation et Injection de Vue

OpenSilver maintient la structure de projet et l'approche de développement de WPF tout en offrant les avantages du développement web moderne. Les développeurs peuvent utiliser les définitions d'UI basées sur XAML et les patterns de code-behind de manière identique, minimisant ainsi la courbe d'apprentissage pour les développeurs WPF existants. La cohérence des applications est maintenue à travers l'injection de dépendances et les structures de services basées sur les fenêtres.

Le système de routage SPA intègre naturellement la structure basée sur la fenêtre avec le routage des URL de Blazor. Cela permet aux développeurs d'utiliser les caractéristiques de navigation par URL propres au web tout en maintenant les patterns de développement WPF.

Le pattern MVVM suit fidèlement l'implémentation de WPF, avec un support complet pour la liaison de données, les commandes et les notifications de changement. Tous les frameworks et bibliothèques XAML basés sur .NET Standard 2.0, comme CommunityToolkit.MVVM, peuvent être utilisés, permettant une mise en œuvre stable de l'architecture indépendante de la plateforme.

L'injection de dépendances fournit une structure qui réduit le couplage entre les modules et facilite les tests unitaires. Elle prend en charge la découverte et l'injection de services basées sur la réflexion, avec une intégration flexible avec le pattern service locator.

La structure du projet est optimisée même pour les développements d'applications à grande échelle. La logique métier peut être implémentée indépendamment de la plateforme à travers des projets partagés, et le chargement dynamique et l'intégration des modules sont pris en charge.

La modularisation et l'injection de vues permettent un design architectural flexible. Les composants peuvent être modularisés par réflexion d'assemblage et injection de vues basée sur le pattern singleton, et une UI/UX cohérente peut être mise en œuvre via des systèmes de design basés sur des templates. Cela permet une migration efficace tout en maintenant les approches modernes de développement de WPF.

## 3. Contrôles Personnalisés

OpenSilver implémente fidèlement l'architecture CustomControl de WPF dans l'environnement web. Il prend en charge les contrôles de base de WPF et permet une personnalisation étendue via ControlTemplate. Les contrôles personnalisés complexes développés dans WPF peuvent être réutilisés avec peu de modifications, et les riches fonctionnalités UI de WPF, telles que les états visuels, les déclencheurs et les animations, peuvent être utilisées telles quelles.

**Caractéristiques Principales**

* Implémentation de la Bibliothèque de Contrôles Standard de WPF
* Système ControlTemplate et DataTemplate
* Support des DependencyProperty
* Système de Routage d'Événements

L'architecture CustomControl d'OpenSilver hérite du système de contrôles principal de WPF. L'apparence et le comportement des contrôles peuvent être personnalisés de manière étendue via ControlTemplate, et des contrôles de base comme ContentControl et ItemsControl fonctionnent avec des structures identiques à WPF.

Le système de template inclut les fonctionnalités principales de WPF. Les apparences des contrôles peuvent être redéfinies via ControlTemplate, et la génération dynamique d'UI basée sur les données est possible via DataTemplate et DataTemplateSelector. Ce système de templates fonctionne avec des patterns identiques à WPF, ce qui améliore la réutilisabilité du code des templates existants.

Le système de propriétés de dépendance implémente les mécanismes principaux de WPF. Il inclut l'héritage des valeurs de propriétés via DependencyProperty, les notifications automatiques de changement de propriété, et le support des animations. Les CustomControls basés sur des propriétés de dépendance développés dans WPF peuvent également être réutilisés efficacement, facilitant la migration de contrôles complexes.

Le système de routage des événements implémente les mécanismes avancés de gestion des événements de WPF. Il prend en charge la propagation (bubbling) et l'inversion (tunneling) des événements, avec la gestion des événements possible via e.Handled. Cela permet une gestion systématique des événements même dans des structures de contrôles imbriqués.

L'implémentation parfaite de l'architecture CustomControl de WPF dans OpenSilver simplifie grandement la migration des applications WPF existantes. En particulier pour les applications d'entreprise avec de nombreux contrôles personnalisés complexes, la capacité de transférer la logique de contrôle vers le web avec peu de modifications constitue un avantage majeur.

## 4. Architecture MVVM

OpenSilver fournit un support complet pour l'architecture MVVM de WPF et la compatibilité avec divers frameworks MVVM. Les éléments clés du pattern Model-View-ViewModel peuvent être implémentés de manière identique dans l'environnement web, permettant aux architectures d'applications WPF existantes d'être utilisées telles quelles. Les frameworks XAML basés sur .NET Standard 2.0, comme CommunityToolkit.MVVM, peuvent être utilisés directement, permettant un développement stable de l'application à travers des outils et des patterns éprouvés.

**Caractéristiques Principales**

* Système de Liaison de Données
* Implémentation du Pattern Command
* Notification de Changement de Propriété
* Support de l'Injection de Dépendances



Le système de liaison de données implémente toutes les puissantes capacités de liaison de WPF. Il prend en charge divers modes de liaison, y compris OneWay, TwoWay et OneWayToSource, et permet des scénarios de liaison avancés tels que la conversion de valeurs via IValueConverter, MultiBinding et PriorityBinding.

Le pattern Command suit fidèlement l'implémentation de WPF. Le traitement des commandes via l'interface ICommand et la gestion de l'activation des commandes via CanExecute sont pris en charge, et des implémentations communes de patterns de commandes comme RelayCommand ou DelegateCommand peuvent être utilisées. Le traitement global des commandes via RoutedCommand et les raccourcis clavier via InputBinding sont également pris en charge.

La notification de changement de propriété est implémentée autour de l'interface INotifyPropertyChanged. Les changements de propriétés des ViewModels sont automatiquement reflétés dans l'UI, et les notifications de changement de collection via ObservableCollection sont également prises en charge. Cela permet une mise en œuvre efficace des UIs réactives.

Le découplage via l'injection de dépendances et la facilitation des tests unitaires sont des avantages majeurs du pattern MVVM. Grâce à l'intégration avec le pattern service locator, les services nécessaires aux ViewModels peuvent être efficacement injectés, permettant une séparation claire de la logique métier des ViewModels. De plus, la communication entre les ViewModels peut être implémentée via des systèmes de messagerie, permettant une conception architecturale modulaire.

Le support complet de MVVM d'OpenSilver permet une migration vers le web tout en préservant l'architecture d'application WPF existante. En particulier pour les applications d'entreprise à grande échelle, une migration stable est possible tout en maintenant l'architecture MVVM éprouvée et en tirant parti des avantages du web.


## 5. Gestion des ressources

OpenSilver prend en charge intégralement le puissant système de gestion des ressources de WPF. Une gestion flexible des ressources est possible via les systèmes **StaticResource** et **DynamicResource**, et une gestion systématique des ressources peut être mise en œuvre grâce à des structures hiérarchiques de dictionnaires de ressources.

**Fonctionnalités principales**

* Système **StaticResource/DynamicResource**
* Structure hiérarchique de dictionnaire de ressources
* Prise en charge des thèmes et de l'internationalisation
* Gestion des ressources à l'exécution

Le système de gestion des ressources d'OpenSilver suit directement la philosophie de conception de WPF. Les références de ressources optimisées à la compilation sont possibles via **StaticResource**, tandis que les ressources peuvent être modifiées dynamiquement à l'exécution via **DynamicResource**. Ce système de référence de ressources duale offre un équilibre entre performance et flexibilité.

Les dictionnaires de ressources peuvent être organisés de manière hiérarchique, des ressources globales au niveau de l'application aux ressources locales au niveau du composant. Cette structure systématique permet de mettre en œuvre efficacement des systèmes de conception modernes comme Material Design ou Fluent Design.

Grâce aux caractéristiques de **DynamicResource**, les thèmes ou les langues peuvent être modifiés dynamiquement à l'exécution. Les changements de thème, comme le passage du mode sombre au mode clair, ou les changements de langue, peuvent être appliqués en temps réel selon les paramètres de l'utilisateur, et de nouvelles ressources depuis le serveur peuvent être immédiatement reflétées.

Grâce à ce système complet de gestion des ressources, les structures de ressources des applications WPF existantes peuvent être réutilisées telles quelles. En particulier pour les applications de grande envergure avec prise en charge des thèmes ou des langues multiples, une migration efficace est possible en utilisant les structures de dictionnaires de ressources existantes et les références de ressources dynamiques.

## 6. Intégration avec la plateforme web

OpenSilver permet une interaction naturelle entre les applications XAML et la plateforme web. En particulier, le contenu web peut être parfaitement intégré dans XAML grâce à des contrôles spéciaux comme **HTMLPresenter**, et tous les éléments XAML sont conçus pour interagir efficacement avec la plateforme web.

**Fonctionnalités principales**

* Prise en charge du contrôle **HTMLPresenter**
* Interaction entre les éléments XAML et Web
* Intégration des scripts natifs
* Système de communication bidirectionnelle

OpenSilver est conçu pour ajouter naturellement des propriétés liées au web à tous les contrôles et éléments de mise en page XAML. Ainsi, les éléments XAML existants peuvent directement utiliser les fonctionnalités de la plateforme web, et la communication bidirectionnelle avec JavaScript s'effectue de manière fluide.

L'intégration des scripts natifs est mise en œuvre systématiquement. Les fonctions JavaScript peuvent être appelées directement depuis le code XAML, et inversement, les fonctionnalités des contrôles XAML peuvent être utilisées depuis JavaScript. Cette interaction flexible est particulièrement utile lorsqu'il s'agit d'intégrer des fonctionnalités web complexes dans des applications XAML.

**HTMLPresenter** permet de rendre et de contrôler parfaitement le contenu web au sein des applications XAML. En particulier, les zones de vue web implémentées avec **CefSharp** ou **WebView** dans WPF peuvent être facilement migrées et réutilisées avec **HTMLPresenter**, maintenant ainsi les structures d'intégration web des applications hybrides existantes.

Ce support systématique de l'interaction est l'un des principaux atouts d'OpenSilver. Les fonctionnalités web nécessaires lors de la migration des applications WPF peuvent être ajoutées de manière naturelle, et les puissantes fonctionnalités de la plateforme web peuvent être utilisées tout en maintenant les structures de code basées sur XAML existantes.

## 7. Différences par rapport à WPF et stratégies de migration

Bien qu'OpenSilver implémente l'architecture principale de WPF dans l'environnement web, il existe certaines différences fondamentales dues aux caractéristiques de la plateforme web. Ces différences peuvent être efficacement abordées grâce aux API web standard et à l'intégration avec les serveurs, et dans certains domaines, elles offrent même des fonctionnalités améliorées.

**Principales différences et solutions**

* Limitations d'accès au système de fichiers
* Stockage et gestion des données
* Cycle de vie de l'application
* Cadre de sécurité et d'authentification

L'accès au système de fichiers est une limitation fondamentale de la plateforme web. Bien que l'accès direct au système de fichiers via **System.IO** soit impossible côté client, les opérations liées aux fichiers peuvent être mises en œuvre via les alternatives suivantes :
- Traitement des fichiers via les API serveur : les tâches de manipulation des fichiers sont gérées en envoyant des requêtes au serveur
- Mise en œuvre du téléchargement/chargement de fichiers via l'API web standard **File API**
- Prise en charge du glisser-déposer des fichiers via l'API **HTML5 Drag & Drop**
- Fonctionnalité copier/coller via l'API **Clipboard**
Ces API web standard permettent d'effectuer des opérations sur les fichiers tout en respectant les politiques de sécurité des navigateurs.

Le stockage et la gestion des données sont restructurés pour l'environnement web. Pour pallier les limitations des bases de données locales :
- Mise en cache des données simples via **localStorage/sessionStorage**
- Stockage de données structuré via **IndexedDB**
- Mécanisme de synchronisation efficace avec les bases de données serveur
- Gestion des données hors ligne grâce aux stratégies de mise en cache des **PWA**
Ces solutions permettent une gestion stable des données dans les applications web.

Le cycle de vie de l'application est géré en fonction des caractéristiques du navigateur web :
- Gestion de l'état de l'application en fonction des onglets/fenêtres du navigateur
- Mise en œuvre de la navigation via l'API **History**
- Prise en charge du rafraîchissement du navigateur, des boutons de retour/avant
- Stratégies pour garantir la persistance de l'état de l'application
En particulier, la structure **SPA** (Single Page Application) offre une expérience utilisateur similaire à celle des applications natives.

La sécurité et l'authentification suivent les normes web, ce qui peut être un avantage :
- Utilisation des normes d'authentification modernes telles que **OAuth** et **JWT**
- Contrôle d'accès aux ressources sécurisé via les politiques **CORS**
- Sécurité renforcée grâce aux politiques de sécurité basées sur le navigateur
- Facilité de gestion centralisée de l'authentification

Ces différences représentent à la fois des contraintes de la plateforme web et de nouvelles opportunités. OpenSilver aborde efficacement ces contraintes grâce aux normes web et à l'intégration avec les serveurs, et surtout, grâce aux API web modernes, il offre une évolutivité et une accessibilité différentes de celles des applications de bureau.

## 8. Stratégie et processus de migration

OpenSilver implémente parfaitement l'architecture de conception de WPF, permettant aux projets WPF d'être convertis en projets OpenSilver presque tels quels. Les éléments principaux de WPF, comme la syntaxe de XAML, le système **Generic.xaml** et le système de dictionnaires de ressources sont implémentés de manière identique, nécessitant des changements structurels minimes dans le code existant. Tous les contrôles principaux de WPF et les systèmes de mise en page, y compris **Window**, **UserControl**, et **ContentControl**, sont fournis de manière identique, permettant la réutilisation du balisage XAML tel quel.

**Éléments principaux de la migration**

* Conversion de la structure du projet
* Stratégie alternative pour les **Triggers**
* Résolution de la dépendance à la plateforme
* Approche de transition progressive

La conversion de la structure du projet peut utiliser la structure de base de WPF telle quelle. La navigation basée sur **Window**, la modularisation des composants avec **UserControl**, et la structure des dictionnaires de ressources sont appliquées de manière identique, et le balisage XAML et les modèles de code-behind peuvent être utilisés sans modification. En particulier, le système de syntaxe de base de WPF, y compris les définitions de style et de modèle via **Generic.xaml** et la gestion des espaces de noms via **XAML using**, est maintenu.

Bien que le système **Trigger** soit une fonctionnalité clé de WPF, il n'est pas fourni dans les plateformes XAML modernes comme **Uno Platform** et **AvaloniaUI**. OpenSilver propose diverses alternatives pour cela. La fonctionnalité **Trigger** peut être efficacement mise en œuvre via des alternatives comme la gestion des états avec **VisualStateManager** (VSM), la conversion de valeur via **IValueConverter**, la sélection dynamique de modèles via **DataTemplateSelector**, et la gestion des interactions via le modèle **ICommand**.

La résolution de la dépendance à la plateforme peut être abordée de manière systématique. Les codes spécifiques à la plateforme, comme les appels à l'API Windows, l'accès au système de fichiers et l'utilisation des ressources natives, peuvent être convertis en API web standard ou en implémentations alternatives d'OpenSilver. En particulier, des éléments de mise en page comme **Grid**, **StackPanel**, **DockPanel** et des contrôles complexes comme **ItemsControl** et **DataGrid** sont implémentés de manière identique, nécessitant des modifications minimales du code UI.

## 9. Configuration de l'environnement de développement

OpenSilver prend en charge le développement sur tous les principaux systèmes d'exploitation, y compris Windows, macOS et Linux, via **Visual Studio** et **Visual Studio Code**. Il fournit un environnement

 de développement de pointe basé sur **.NET 9.0**, et particulièrement dans les environnements Windows, permet un développement et des tests directs sans hébergement web virtuel grâce au simulateur WPF.

**Environnement de développement principal**

* Prise en charge des outils multiplateformes
* Environnement de débogage intégré
* Simulation WPF
* Outils de productivité pour le développement

L'environnement de développement multiplateforme assure la liberté de choix pour les développeurs. Ils peuvent utiliser le puissant concepteur XAML de Visual Studio et IntelliSense, et un développement efficace est également possible dans un environnement léger via **Visual Studio Code**. En offrant une expérience de développement identique sur tous les principaux systèmes d'exploitation, il améliore la flexibilité pour les projets d'équipe.

L'environnement de débogage intégré fournit une expérience de développement WPF dans le développement web également. Les zones **Blazor WebAssembly** et le code **OpenSilver** peuvent être débogués, permettant un débogage complet de l'ensemble de la pile d'applications. Les développeurs WPF peuvent utiliser des fonctionnalités de débogage familières telles que les points d'arrêt, l'inspection des variables et l'analyse de la pile d'appels.

La simulation WPF améliore considérablement la productivité du développement dans les environnements Windows. Les applications peuvent être exécutées et testées directement comme des applications WPF, sans configuration de serveur web séparée, avec un support complet pour le débogage, la visualisation et le suivi des performances. Cela permet de raccourcir les cycles de développement et d'obtenir des retours immédiats.

## 10. Communauté et ressources

OpenSilver assure son évolution continue et son support grâce à une communauté open source active. Les dernières mises à jour et informations techniques détaillées peuvent être obtenues via le dépôt GitHub officiel et la documentation, et diverses expériences réelles de migration et solutions peuvent être partagées au sein de la communauté. En particulier, les dernières tendances de développement et expériences pratiques sont continuellement partagées par les techniciens, évangélistes et contributeurs clés d'OpenSilver.

**Ressources et support**

* Dépôt GitHub d'OpenSilver
* Documentation officielle d'OpenSilver
* Suivi des problèmes et forums de discussion
* Projets et démonstrations exemples

La documentation officielle fournit toutes les informations techniques nécessaires à la migration. Des documents techniques détaillés, y compris ce guide, sont fournis sur le site de documentation officiel d'OpenSilver et sont mis à jour en continu. En particulier, les nouvelles fonctionnalités et améliorations sont reflétées dans la documentation avec les nouvelles versions, permettant une référence aux informations toujours actuelles.

Grâce au dépôt GitHub (github.com/opensilver/opensilver), l'accès direct au code source du projet est possible, et la résolution des problèmes et les demandes de fonctionnalités peuvent être effectuées via le **suivi des problèmes**. En particulier, les bogues et améliorations découverts pendant la migration peuvent être directement signalés et participés au processus de résolution, contribuant à l'amélioration de la qualité du projet.

Le support de la communauté est un canal crucial pour partager les expériences réelles des utilisateurs d'OpenSilver. Les expériences de migration peuvent être partagées et des méthodes de résolution de problèmes discutées avec d'autres développeurs via des plateformes comme **GitHub Discussions** et **Stack Overflow**. Les évangélistes et contributeurs principaux d'OpenSilver participent activement pour partager des conseils techniques et les derniers cas de développement, permettant aux membres de la communauté d'obtenir des solutions vérifiées et des bonnes pratiques applicables aux projets réels.

OpenSilver propose également des services de support de migration professionnels pour les clients entreprises. La migration réussie des applications WPF à grande échelle est soutenue par l'établissement de stratégies de migration personnalisées, la consultation technique et un support direct au développement adapté aux besoins spécifiques de chaque entreprise. En particulier, pour les applications d'entreprise avec une logique métier complexe ou de nombreux contrôles personnalisés, une migration stable et efficace est possible grâce au support professionnel de l'équipe OpenSilver.
