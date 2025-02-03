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

OpenSilver fournit un système de gestion des ressources complet, identique à celui de WPF, permettant de gérer efficacement les styles, les modèles, les couleurs, les polices et d'autres ressources liées à l'interface utilisateur. Il prend en charge les dictionnaires de ressources, les styles, les modèles, ainsi que les ressources dynamiques, ce qui permet une transition transparente lors de la migration.

### Caractéristiques clés

- **Support des dictionnaires de ressources** : Les styles, modèles et autres ressources peuvent être organisés dans des dictionnaires de ressources et référencés à travers toute l'application.
- **Styles et modèles** : Prend en charge les styles, le ControlTemplate et le DataTemplate de WPF, permettant de personnaliser facilement l'interface utilisateur.
- **Ressources dynamiques** : OpenSilver permet de modifier les styles et ressources de l'interface utilisateur au moment de l'exécution via DynamicResource.
- **Support des thèmes** : OpenSilver prend également en charge le changement de thème, de la même manière que dans WPF, ce qui permet de passer d'un thème visuel à un autre en fonction de conditions ou des préférences des utilisateurs.

### Exemple

```xml
<ResourceDictionary>
  <Style TargetType="Button">
    <Setter Property="Background" Value="Blue" />
  </Style>
</ResourceDictionary>
```

Avec ce code, les développeurs peuvent utiliser les dictionnaires de ressources comme dans WPF, définir des styles dans toute l'application et les référencer dans les éléments de l'interface utilisateur.

## 6. Intégration avec la plateforme Web

OpenSilver ne se contente pas de reproduire les fonctionnalités de WPF, il exploite également les avantages de la plateforme Web. Grâce à WebAssembly, OpenSilver permet aux applications WPF de bénéficier de performances natives tout en s'exécutant dans le navigateur.

OpenSilver facilite l'intégration de JavaScript, CSS et éléments HTML dans les applications XAML. Vous pouvez utiliser JavaScript pour interagir avec les contrôles OpenSilver, ou insérer des éléments HTML dans une application OpenSilver. Cela rend l'intégration entre les technologies Web et les applications XAML transparente, permettant une flexibilité maximale pour les développeurs.

### Exemple d'intégration JavaScript

OpenSilver permet aux développeurs d'utiliser JavaScript pour interagir avec les contrôles XAML. Par exemple, vous pouvez modifier dynamiquement les propriétés d'un bouton OpenSilver depuis JavaScript, ou réagir à des événements utilisateurs.

```javascript
// Modifier la couleur de fond d'un bouton OpenSilver depuis JavaScript
let button = document.getElementById('myButton');
button.backgroundColor = 'Red';
```

De plus, vous pouvez intégrer des éléments HTML directement dans votre application OpenSilver et interagir avec eux via XAML et JavaScript.

```xaml
<Button Content="Cliquez-moi" Click="Button_Click">
  <Button.Template>
    <ControlTemplate TargetType="Button">
      <StackPanel>
        <TextBlock Text="Ceci est un bouton personnalisé" />
        <html:div id="htmlContainer">Contenu HTML</html:div>
      </StackPanel>
    </ControlTemplate>
  </Button.Template>
</Button>
```

## 7. Différences avec WPF et stratégies de migration

Bien qu'OpenSilver conserve de nombreuses fonctionnalités fondamentales de WPF, c'est une nouvelle plateforme qui présente certaines différences. Lors de la migration, il est essentiel de comprendre ces différences et de mettre en place une stratégie adéquate.

### Différences principales

- **Performances et limitations de la plateforme** : Bien qu'OpenSilver offre des performances proches de celles d'une application native grâce à WebAssembly, il peut y avoir des limitations par rapport aux applications de bureau en raison des contraintes des navigateurs web.
- **Compatibilité des contrôles** : Certains contrôles WPF peuvent ne pas être entièrement transférables sur OpenSilver. Par exemple, les contrôles WinForms ou l'accès direct au matériel ne sont pas compatibles.
- **Différences entre navigateurs** : Les différents navigateurs peuvent avoir des comportements différents concernant le support de WebAssembly, ce qui peut entraîner des écarts de comportement entre les navigateurs.

### Stratégies de migration

1. **Commencer par les contrôles simples** : Il est conseillé de commencer par migrer les contrôles de base et courants de votre application, puis de tester leur comportement pour s'assurer qu'ils fonctionnent correctement dans OpenSilver.
2. **Migration progressive** : Pour les applications complexes, une migration progressive est recommandée. Commencez par migrer les composants de l'interface utilisateur, puis migrez la logique métier et les services en arrière-plan.
3. **Utiliser des bibliothèques communes** : Les bibliothèques XAML qui sont compatibles avec .NET Standard 2.0, comme CommunityToolkit.MVVM, peuvent être utilisées dans OpenSilver sans modification, ce qui simplifie la migration des applications complexes.

## 8. Stratégie et Processus de Migration

OpenSilver implémente parfaitement l'architecture de conception de base de WPF, permettant aux projets WPF d'être convertis en projets OpenSilver quasiment tels quels. Les éléments de base de WPF, comme la syntaxe XAML, le système Generic.xaml et les dictionnaires de ressources, sont identiquement implémentés, nécessitant très peu de modifications structurelles dans le code existant. Tous les contrôles WPF de base et les systèmes de mise en page, y compris `Window`, `UserControl` et `ContentControl`, sont fournis de manière identique, permettant de réutiliser directement le code XAML.

### Éléments clés de la migration

- **Conversion de la structure du projet** : La structure de base du projet WPF peut être utilisée sans modification. La navigation basée sur `Window`, la composition avec `UserControl` et la structure des dictionnaires de ressources sont appliquées de manière identique. Les éléments de syntaxe XAML, y compris les styles et la définition des modèles via `Generic.xaml` et la gestion des espaces de noms via `XAML using`, sont également maintenus.
  
- **Stratégie alternative pour les déclencheurs (Triggers)** : Les déclencheurs (Triggers) étant une fonctionnalité clé de WPF, mais non fournie dans des plateformes XAML modernes comme Uno Platform ou AvaloniaUI, OpenSilver propose diverses alternatives pour les gérer. Les fonctionnalités de déclenchement peuvent être efficacement mises en œuvre à travers des alternatives comme la gestion d'état via `VisualStateManager` (VSM), la conversion de valeurs via `IValueConverter`, la sélection dynamique de modèles via `DataTemplateSelector`, et la gestion des interactions avec le modèle de commande `ICommand`.
  
- **Résolution des dépendances spécifiques à la plateforme** : Le code spécifique à la plateforme, comme les appels à l'API Windows, l'accès au système de fichiers et l'utilisation de ressources natives, doit être converti pour utiliser des API web standard ou des implémentations OpenSilver. Par exemple, les éléments de mise en page tels que `Grid`, `StackPanel`, `DockPanel` et des contrôles complexes comme `ItemsControl` et `DataGrid` sont implémentés de manière identique, avec peu de modifications nécessaires dans le code UI.

## 9. Configuration de l'environnement de développement

OpenSilver prend en charge le développement sur tous les systèmes d'exploitation majeurs, y compris Windows, macOS et Linux, à travers Visual Studio et Visual Studio Code. Il fournit un environnement de développement de pointe basé sur .NET 9.0 et, en particulier dans les environnements Windows, permet un développement et un test directs sans avoir besoin d'hébergement web virtuel, grâce au simulateur WPF.

### Caractéristiques principales de l'environnement de développement

- **Support des outils multiplateformes** : Les développeurs peuvent utiliser Visual Studio, avec son puissant concepteur XAML et son autocomplétion, ou un environnement plus léger avec Visual Studio Code. L'environnement de développement est uniforme à travers tous les systèmes d'exploitation majeurs, ce qui améliore la flexibilité pour les projets d'équipe.
  
- **Débogage intégré** : L'environnement de débogage intégré permet de déboguer aussi bien les zones Blazor WebAssembly que le code OpenSilver, offrant ainsi un débogage complet de l'application. Les développeurs peuvent utiliser des fonctionnalités familières du débogage WPF, telles que les points d'arrêt, l'inspection des variables et l'analyse de la pile d'appels.
  
- **Simulation WPF** : Sur les environnements Windows, la simulation WPF améliore la productivité des développeurs. Les applications peuvent être exécutées et testées directement comme des applications WPF, sans avoir besoin de configurer un serveur web distinct, et offrent un support complet pour le débogage, la visualisation et le suivi des performances.

## 10. Communauté et Ressources

OpenSilver bénéficie d'une évolution continue grâce à une communauté open source active. Les dernières mises à jour et informations techniques détaillées sont disponibles via le dépôt GitHub officiel et la documentation. Les expériences de migration réelles et des solutions peuvent être partagées à travers la communauté, permettant un échange constant de bonnes pratiques et de conseils techniques.

### Ressources et Support

- **Dépôt GitHub d'OpenSilver** : Le dépôt GitHub (github.com/opensilver/opensilver) offre un accès direct au code source du projet, où les demandes de fonctionnalités et les rapports de bugs peuvent être déposés.
  
- **Documentation officielle d'OpenSilver** : La documentation officielle fournit toutes les informations techniques nécessaires pour la migration et est continuellement mise à jour avec les nouvelles versions du projet.
  
- **Suivi des problèmes et forums de discussion** : Les discussions sur GitHub et des forums comme Stack Overflow sont des canaux cruciaux pour partager les expériences de migration et résoudre les problèmes. Les evangelistes OpenSilver et les contributeurs principaux participent activement en partageant des conseils techniques et des cas de développement récents.
  
- **Projets d'exemples et démonstrations** : De nombreux projets d'exemples et démonstrations sont mis à disposition pour aider les développeurs à se familiariser rapidement avec OpenSilver et à comprendre comment effectuer une migration en douceur.

OpenSilver offre également un support professionnel pour les entreprises, avec des services de conseil technique, de stratégie de migration personnalisée et un soutien au développement. Cela permet une migration stable et efficace des applications WPF complexes vers le Web, en particulier pour les applications d'entreprise avec une logique métier complexe ou de nombreux contrôles personnalisés.

