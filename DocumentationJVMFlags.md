# Documentation Tâche 3 
## Simon Thivierge 20248484

## 1. -XX:+UseG1GC
### Type:
Garbage Collection (GC) Flag
### Description :
Ce Flag permet d'utiliser le garbage collector G1 (Garbage-First), qui est conçu pour les applications nécessitant une grande quantité de mémoire et des temps de pause réduits.
### Justification:
Le GC G1 divise le tas en régions et les gère indépendamment, ce qui peut améliorer l'efficacité des applications qui doivent gérer un volume élevé d'allocations dynamiques de mémoire. 
L'utilisation de cet indicateur permet de réduire le temps de latence lors du ramassage des ordures, ce qui est bénéfique pour les applications à haut débit comme Jsoup, 
où la gestion de la mémoire peut avoir un impact sur les performances.

## 2. -XX:+UseStringDeduplication
### Type: 
Flag de gestion de la mémoire
### Description :
Cette option permet d'activer la déduplication des chaînes de caractères, un processus par lequel les chaînes identiques en mémoire sont reconnues et fusionnées pour économiser de l'espace.
### Justification:
La déduplication des chaînes de caractères peut réduire de manière significative l'utilisation de la mémoire, 
en particulier dans les applications qui créent un grand nombre de chaînes identiques, telles que les analyseurs de texte et les scanners de sites web. 
Pour Jsoup, qui gère un contenu HTML important, ce drapeau optimise l'utilisation de la mémoire et améliore les performances globales.

## 3. -Xms512m
### Type:
Heap Size Allocation Flag
### Description :
Ce Flag fixe la taille initiale du tas de la JVM à 512 Mo. Le paramètre Xms définit la quantité initiale de mémoire allouée à la JVM au lancement du programme.
### Justification:
Établir une taille initiale du tas permet d'éviter que la JVM ne redimensionne fréquemment le tas, 
ce qui peut améliorer les performances au démarrage et fournir une allocation de mémoire plus cohérente pour Jsoup. 
Cela est particulièrement utile pour gérer des documents volumineux et des tâches d'analyse simultanées, en veillant à ce que l'application dispose de suffisamment de mémoire dès le départ.

## 4. -XX:+UnlockDiagnosticVMOptions
### Type:
Diagnostic Flag
### Description :
Ce Flag permet d'accéder à des options de diagnostic supplémentaires dans la JVM, qui sont généralement cachées dans les opérations standard de la JVM.
### Justification:
Pour les tests et l'analyse des performances, le déverrouillage des options de diagnostic permet aux développeurs d'utiliser des drapeaux et des outils supplémentaires pour le réglage de la JVM. 
Cela est particulièrement utile pour effectuer des diagnostics plus approfondis sur l'utilisation de la mémoire, le ramassage des ordures et d'autres mesures de performance pendant le test de Jsoup.

## 5. -XX:+UseAdaptiveSizePolicy
### Type:

### Description :
Ce Flag active la politique de taille adaptative, qui permet à la JVM d'ajuster la taille du tas et des autres pools de mémoire de manière dynamique en fonction des besoins de l'application.
### Justification:
Grâce à la politique de taille adaptative, la JVM peut optimiser l'allocation et l'utilisation de la mémoire en temps réel, ce qui améliore les performances des applications dont les besoins en mémoire fluctuent. 
Pour Jsoup, cet indicateur permet de garantir une utilisation efficace de la mémoire lors de charges de travail variables, telles que l'analyse de documents HTML de petite et de grande taille de manière interchangeable.
