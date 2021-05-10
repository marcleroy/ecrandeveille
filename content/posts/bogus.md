---
title: 'Utiliser Bogus avec les Xamarin.Forms'
date: Fri, 28 Feb 2020 22:58:29 +0000
draft: false
tags: ['Dev tools']
---

Voir ici : [Utiliser Bogus avec les Xamarin.Forms](https://www.e-naxos.com/Blog/post/Utiliser-Bogus-avec-les-XamarinForms.aspx)

Bogus est un complément indispensable pour les tests mais aussi la création dynamique de données de design. Connaissez-vous cette extension ?

## Bogus

Bogus est une bibliothèque de Brian Chavez à utiliser dans les tests automatisés pour générer automatiquement des données de test de différents types. On peut l’utiliser dans le cadre de tests NUnit ou de tout autres outils de test. On peut même s’en servir astucieusement dans le cadre d’un développement classique pour générer des données de Design aléatoires mais crédibles par exemple.

Bogus peut être intégré aux projets NUnit pour tester le code Xamarin.Forms d’où l’intérêt de bien le connaître et de s’en servir pour simplifier l’écriture des tests.

### Introduction

A titre d'exemple, supposons que la classe suivante soit impliquée dans un test unitaire :

```csharp
public class Revue
{  
  public int Id { get; set; }  
  public string Titre { get; set; }  
  public string Corps { get; set; }  
  public int Notation { get; set; }  
  public DateTimeOffset Creation { get; set; }  
  public override string ToString() { return $"{Id} '{Titre}'"; }  
}
```

Lors d'un test, une instance de **Revue** peut nécessiter des propriétés contenant des valeurs ayant un minimum de sens. Cela peut être fait manuellement, par exemple pour vérifier l'implémentation de ToString() :

```csharp
var m = new Revue { Id = 42, Titre = "La réponse à tout" };  
if (m.ToString() != "42 'La réponse à tout'") 
  throw new Exception("Données incorrectes");
```

Notez que dans le test précédent, les valeurs réelles et le titre importent peu, mais seulement le fait qu’elles soient jointes dans le cadre de l’appel ToString (). Dans cet exemple, les valeurs pour Id et Titre peuvent être considérées comme des variables / valeurs anonymes, car nous ne nous en soucions pas vraiment.

Nota : les exemples sont écrits comme du code traditionnels, dans un projet de type NUnit on utiliserait des appels à Assert() pour valider les données et non un test avec levée d’exception comme ici.
