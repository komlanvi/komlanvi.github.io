---
layout: post
author: komlanvi
title: Introduction
categories: apprendre_elixir
description: Introduction des series d'article sur l'apprentissage d'elixir.
---

# Introduction

 **Elixir** a été inventé par Jose Valim en 2011, C'est un langage de programmation basé sur la machine virtuelle du langage de programmation **erlang** appellé **BEAM**.
 Cela signifie qu'une application écrite en **elixir** après compilaiton est interprété par la machine virtuelle d'**erlang**.
 Un des avantages direct de sa dépendance à **erlang** est que l'on peut écrire du code _erlang_ directement dans le code _elixir_.

 Selon le site officiel:

> **Elixir** est un langage de programmation fonctionnel et dynamique conçu pour créer des applications évolutives et maintenables. [https://elixir-lang.org/](https://elixir-lang.org/)

<dl>
<dt>Fonctionel</dt>
<dd>Elixir est doté de toutes les propriétés qu'on peut espérer d'un langage de programmation fonctionnel: pattern matching,
 données immutables, fonctions d'ordre supérieur, le lazing loading, etc...</dd>
<dt>Dynamique</dt>
<dd>Elixir n'impose pas la spécification du type des variables dans le code. Elle permet également de modifier dynamiquement des structures
 de données au moment du runtime, etc...</dd>
<dt>Evolutive</dt>
<dd>Le code elixir est éxécuter dans des léger processus, isolés et qui communiquent
 entre eux à travers des messages. Cette isolation facilite la programmation concurrentiel.</dd>
<dt>Maintenable (Fault-tolerance)</dt>
<dd>Une application en éxécution, tot ou tard aura un comportement non voulu du à un quelconque problème:
 erreur de réseau, ressource externe indisponible, etc... Pour lutter contre les pertes d'informations due à ces problème, en elixir il y a
 ce qu'on appelle les superisors dont l'objectif est de restaurer une application entrée dans un état incertain en se
 basant sur une configuration.</dd>
</dl>
