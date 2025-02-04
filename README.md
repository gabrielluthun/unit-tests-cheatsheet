# Cheatsheet Tests Unitaires

## Table des matières
- [1. Introduction](#1-introduction)
- [2. Les types de tests](#2-les-types-de-tests)
- [3. Les bonnes pratiques des tests](#3-les-bonnes-pratiques-des-tests)

---


## 1. Introduction
### 1.1 Qu'est-ce qu'un test unitaire ?
Test unitaire = test qui **vérifie** le **comportement** d'une unité de code.
*(Unité de code = fonction, méthode, classe, etc.)*

Ni plus, ni moins.

### 1.2 Pourquoi écrire des tests unitaires ?

- **Réduction des erreurs** : ces tests permettent de détecter les erreurs avant que celles-ci ne soient commises.
- **Réduction des coûts** : effet boule de neige de la réduction des erreurs.

## 1.3 Vocabulaire des tests
- **Test Fixture** : morceau de code qui permet de **configurer** un test, ce qui permet de réutiliser le **même** jeu de données pour **plusieurs** tests.
- **Test Suite** : **ensemble** de tests.
- **Test Case** : **un** test unitaire.
- **System Under Test (SUT)** : représente la partie du code que l'on veut **tester**. *(classe, méthode, ensemble de classes...)*
- **Test Runner** : outil qui permet d'exécuter les tests.
- **Assertions** : vérifications de sécurité que l'on souhaite faire sur le SUT.
- **Mock** : objet simulant le comportement d'un objet réel.
- **Stub** : remplacement d'une interface par un objet simulant le comportement d'un objet réel. (exemple : simuler un paiement réussi)
- **Spies** : observateur enregistrant des appels de fonctions sans modifier leur comportement.

---

## 2. Les types de tests
### 2.1 Principes FIRST
**Fast (Rapide)** : les tests doivent être rapides à exécuter (quelques millisecondes)
- **Isolated (Isolé)** : chaque test doit être indépendant
- **Repeatable (Répétable)** : les tests doivent être constants, quel que soit l'environnement
- **Self-validating (Auto-validant)** : les tests doivent valider leur succès ou leur échec sans intervention humaine
- **Timely (Opportun)** : les tests doivent être écrits en parallèle ou juste après le développement du code testé

### 2.2 Les tests unitaires
Tests **unitaires** = tests qui vérifient le **comportement** d'une **unité** de code.

**Objectifs** : garantir que **chaque unité** de code fonctionne comme prévu


Cas d'usage : 
- **Valider** les fonctions critiques
- **Identifier** les régressions lors de modifications 
- **Favoriser** un code modulaire et propre

### 2.3 Les tests d'intégration
Tests **d'intégration** = vérifient la **communication** entre les unités.    
Implique plusieurs modules / composants.

Cas d'usage :
- **Valider** les fonctions critiques
- **Identifier** les régressions lors de modifications 
- **Favoriser** un code modulaire et propre


### 2.4 Les tests E2E (End-to-End)
Tests **E2E** = tests qui simulent le système dans son ensemble    
Vise à valider que toutes les parties du système fonctionnent ensemble, depuis l'interface utilisateur jusqu'aux bases de données (et autres services)

Cas d'usage : 
- Tester un parcours utilisateur complet, un peu comme un achat en ligne
- Valider l'expérience utilisateur sur différents navigateurs/appareils
- Garantit la cohérence fonctionelle, notamment après des MàJ majeures

### 2.5 Les 3 tests en résumé
- **Unitaires** : vérifient le comportement d'une unité de code et garantissent la fiabilité des composants
- **D'intégration** : assurent le bon fonctionnement des interactions entre modules/composants
- **E2E** : vérifient le système du point de vue utilisateur

---

## 3. Les bonnes pratiques des tests
### 3.1 Convention de nommage
Améliore la lisibilité et la compréhension des tests

Un **nom** doit **décrire** :
- Méthode **testée**
- L'état / Scénario **testé**
- Comportement **attendu**

Exemple en Java :
```java
@Test
public void IsPrime_WhenNumberIsPrime_ReturnsTrue() {
    // ...
}
```

-> Permet de savoir rapidement l'objectif du test

### 3.2 Structure des tests : Arrange, Act, Assert (AAA)
Modèle **AAA** : Organisation de Tests

**A**rrange : Préparez les objets nécessaires au test
**A**ct : Exécutez le test
**A**ssert : Vérifiez le résultat

Exemple en C# :
```csharp
// Arrange
var primeUtils = new PrimeUtils();
int number = 5;
bool expected = true;

// Act
var actual = primeUtils.IsPrime(number);

// Assert
Assert.Equal(expected, actual);
```

### 3.3 Tests isolés et indépendants

- Utiliser des **mocks** pour simuler les dépendances externes
- **Isoler** les tests pour éviter les **effets de bord** et qu'ils soient **indépendants**

### 3.4 Couverture de code

- **Couverture de code** = mesure de la quantité de code testé par rapport au code total
- **Objectif** = s'en fixer un **réaliste** (80-90%), ne pas chercher à atteindre 100%
- **Couverture de test** = mesure de la quantité 
#### Outils de couverture de code

- **JaCoCo** : outil de couverture de code pour Java
- **Cobertura** : outil de couverture de code pour Java
- **NCover** : outil de couverture de code pour .NET
- **Istanbul** : outil de couverture de code pour JavaScript

### 3.5 Documentation des tests

- Essentielle pour faciliter la compréhension des tests
#### Bonnes pratiques de documentation de tests
- **Nommage** : suivre les conventions de nommage comme indiqué [ici](#31-convention-de-nommage)
- **Commentaires** : ajouter des commentaires  pertinents pour expliquer les tests complexes, ou si l'objectif n'est pas clair
- **Rapports automatisés** : Utiliser des outils de rapports pour faciliter la compréhension des tests (Allure, JUnit, SonarQube, etc.)
- **Centraliser la documentation** : placer la documentation dans un fichier séparé ou un dossier (README.md, etc.)