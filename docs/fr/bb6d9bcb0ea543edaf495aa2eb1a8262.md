# Guide du développeur OpenSilver : Migration WPF

Ce guide est conçu pour les développeurs WPF souhaitant migrer leurs applications vers OpenSilver. OpenSilver est un framework puissant qui permet la transformation d'applications basées sur XAML en environnements web modernes, implémentant parfaitement l'architecture de base et les paradigmes de développement de WPF dans un contexte web. Il maintient notamment la prise en charge de l'architecture basée sur CustomControl de WPF tout en permettant des applications web hautes performances grâce à la technologie WebAssembly.

## Table des matières

1. Aperçu
2. Architecture de base
3. Contrôles personnalisés
4. Architecture MVVM
5. Gestion des ressources
6. Intégration de la plateforme Web
7. Différences avec WPF et stratégies de migration
8. Stratégie et processus de migration
9. Configuration de l'environnement de développement
10. Communauté et ressources

## 1. Aperçu

OpenSilver, qui a commencé comme une alternative moderne à Silverlight, a réussi à migrer de nombreuses applications héritées vers des environnements web à travers le monde. C'est une solution puissante qui permet aux applications basées sur XAML et .NET de fonctionner dans les navigateurs web modernes. Les applications de diverses plateformes, notamment WPF, Xamarin, UWP, WinUI 3, .NET MAUI, Uno Platform et AvaloniaUI, peuvent être migrées vers le web tout en maintenant une haute compatibilité.

**Différenciateurs clés**

* Performance native basée sur WebAssembly
* Implémentation de l'architecture CustomControl de WPF
* Intégration flexible des technologies XAML et Web
* Support de la méthodologie de développement entreprise
* Implémentation d'animations niveau WPF

En exploitant la technologie WebAssembly, OpenSilver offre des performances similaires au natif, gérant efficacement la logique métier complexe et le traitement des données. Cet avantage est particulièrement évident dans les applications d'entreprise à grande échelle.

L'architecture CustomControl de WPF a été parfaitement implémentée dans l'environnement web. Toutes les fonctionnalités, y compris la personnalisation des ControlTemplate, les parties de modèles et les états visuels, sont entièrement prises en charge, permettant une implémentation identique des structures UI complexes et des interactions.

L'intégration entre XAML et les technologies web est très flexible. Les éléments HTML peuvent être naturellement combinés avec les contrôles XAML, et les interactions avec les styles CSS et JavaScript sont transparentes. Les puissants systèmes de mise en page de WPF comme Grid, StackPanel et DockPanel peuvent être utilisés tels quels.

Les modèles et méthodologies de développement d'applications d'entreprise essentiels tels que le modèle MVVM, l'injection de dépendances, la distribution de projets et la modularisation des contrôles sont entièrement pris en charge. Cela assure la maintenabilité et l'évolutivité des projets à grande échelle.

## 2. Architecture de base

OpenSilver implémente l'architecture de base de WPF dans l'environnement web. Utilisant la technologie WebAssembly, il fournit des performances quasi natives et permet aux développeurs d'utiliser l'environnement de débogage de Visual Studio, offrant une expérience de développement familière aux développeurs WPF.

**Caractéristiques architecturales**

* Structure de projet WPF native
* Système de routage SPA
* Modèle d'architecture MVVM
* Framework d'injection de dépendances
* Structure de distribution de projet
* Modularisation et injection de vues

OpenSilver maintient la structure de projet existante et l'approche de développement de WPF tout en fournissant les avantages du développement web moderne. Les développeurs peuvent utiliser les définitions d'interface utilisateur basées sur XAML et les modèles de code-behind de manière identique, minimisant la courbe d'apprentissage pour les développeurs WPF existants. La cohérence de l'application est maintenue grâce à l'injection de dépendances basée sur Window et aux structures de services.

Le système de routage SPA intègre naturellement la structure basée sur Window avec le routage URL de Blazor. Cela permet aux développeurs d'utiliser les caractéristiques de navigation URL basées sur le web tout en maintenant les modèles de développement WPF.

Le modèle MVVM suit fidèlement l'implémentation de WPF, avec une prise en charge complète de la liaison de données, des commandes et des notifications de changement. Tous les frameworks et bibliothèques XAML basés sur .NET Standard 2.0, tels que CommunityToolkit.MVVM, peuvent être utilisés, permettant une implémentation d'architecture stable indépendante de la plateforme.

L'injection de dépendances fournit une structure qui réduit le couplage entre les modules et facilite les tests unitaires. Elle supporte la découverte et l'injection de services basées sur la réflexion, avec une intégration flexible avec le modèle de localisateur de services.

La structure du projet est optimisée même pour le développement d'applications à grande échelle. La logique métier peut être implémentée de manière indépendante de la plateforme grâce à des projets partagés, et le chargement dynamique et l'intégration des modules sont pris en charge.

La modularisation et l'injection de vues permettent une conception architecturale flexible. Les composants peuvent être modularisés grâce à la réflexion d'assemblage et à l'injection de vues basée sur le modèle singleton, et une interface utilisateur/UX cohérente peut être implémentée grâce à des systèmes de conception basés sur des modèles. Cela permet une migration efficace tout en maintenant les approches de développement tendance de WPF.