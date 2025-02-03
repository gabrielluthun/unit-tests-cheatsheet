# Cheatsheet Tests Unitaires

## Table des matières
- [1. Introduction](#1-introduction)
- [2. Découverte du vocabulaire des tests](#2-découverte-du-vocabulaire-des-tests)

## 1. Introduction
### 1.1 Qu'est-ce qu'un test unitaire ?
Test unitaire = test qui **vérifie** le **comportement** d'une unité de code.
*(Unité de code = fonction, méthode, classe, etc.)*

Ni plus, ni moins.

### 1.2 Pourquoi écrire des tests unitaires ?

- **Réduction des erreurs** : ces tests permettent de détecter les erreurs avant que celles-ci ne soient commises.
- **Réduction des coûts** : effet boule de neige de la réduction des erreurs.

## 2. Découverte du vocabulaire des tests
- **Test Fixture** : morceau de code qui permet de **configurer** un test, ce qui permet de réutiliser le **même** jeu de données pour **plusieurs** tests.
- **Test Suite** : **ensemble** de tests.
- **Test Case** : **un** test unitaire.
- **System Under Test (SUT)** : représente la partie du code que l'on veut **tester**. *(classe, méthode, ensemble de classes...)*
- **Test Runner** : outil qui permet d'exécuter les tests.
- **Assertions** : vérifications de sécurité que l'on souhaite faire sur le SUT.
- **Mock** : objet simulant le comportement d'un objet réel.
- **Stub** : remplacement d'une interface par un objet simulant le comportement d'un objet réel. (exemple : simuler un paiement réussi)
- **Spies** : observateur enregistrant des appels de fonctions sans modifier leur comportement.