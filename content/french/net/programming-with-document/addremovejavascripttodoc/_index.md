---
title: Ajouter et supprimer Javascript au document PDF
linktitle: Ajouter et supprimer Javascript au document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter et supprimer du JavaScript dans un document PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec didacticiels de code pour la création de scripts au niveau du document.
type: docs
weight: 30
url: /fr/net/programming-with-document/addremovejavascripttodoc/
---
## Introduction

Dans ce guide, nous vous expliquerons comment utiliser Aspose.PDF pour .NET pour insérer du JavaScript dans un fichier PDF et comment le supprimer si nécessaire. À la fin de ce didacticiel, vous comprendrez clairement comment manipuler du JavaScript dans les PDF sans effort.

## Prérequis

Avant de plonger dans le code, vous devez configurer quelques éléments :

1.  Aspose.PDF pour .NET : vous aurez besoin de la bibliothèque Aspose.PDF pour .NET installée dans votre projet. Si vous ne l'avez pas encore, récupérez la bibliothèque à partir du[Page de téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/).
2. IDE ou éditeur de texte : vous pouvez utiliser n’importe quel IDE compatible .NET comme Visual Studio.
3. Connaissances de base en C# : ce didacticiel suppose que vous êtes à l'aise avec C# et familiarisé avec la manipulation de PDF.
4. Licence : Assurez-vous d'appliquer une licence valide pour éviter les limitations. Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).

## Paquets d'importation

Pour commencer à utiliser Aspose.PDF pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Voici comment procéder :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Ces deux espaces de noms sont essentiels.`Aspose.Pdf` vous permet de travailler avec des documents PDF, tandis que`System.Collections` sera utilisé pour gérer les clés JavaScript.

Décomposons l'ensemble du processus d'ajout et de suppression de JavaScript d'un PDF en étapes faciles à suivre.

## Étape 1 : Initialiser un nouveau document PDF

La première chose à faire est de créer un nouveau document PDF. Ce document servira de toile vierge pour l'ajout de JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Ici, nous initialisons un nouveau`Document` objet et y ajouter une page vierge. Considérez cela comme la base de votre PDF.

## Étape 2 : ajouter du JavaScript au PDF

Maintenant que nous avons un document, il est temps d'y ajouter du JavaScript. JavaScript dans les PDF peut être utilisé pour ajouter des comportements personnalisés, tels que des alertes ou la validation de formulaire.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

Dans cet extrait de code, nous ajoutons deux fonctions JavaScript (`func1` et`func2` ) au PDF. Ces fonctions peuvent effectuer diverses tâches, selon vos besoins. Ici, nous appelons simplement une fonction d'espace réservé appelée`hello()`.

## Étape 3 : Enregistrer le PDF avec JavaScript

Une fois que vous avez ajouté le JavaScript souhaité, il est temps d'enregistrer le PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Cela enregistrera le document avec JavaScript sous le nom`AddJavascript.pdf` dans le répertoire spécifié (`dataDir`).

## Étape 4 : charger et afficher JavaScript dans le PDF existant

Supposons que vous ayez besoin de vérifier ou de modifier les fonctions JavaScript dans un fichier PDF existant. La première étape consiste à charger le fichier PDF et à accéder aux clés JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Nous chargeons l'existant`AddJavascript.pdf` et stocker les clés JavaScript dans une liste.`Keys` la propriété renvoie les noms de toutes les fonctions JavaScript attachées au document.

## Étape 5 : Afficher les fonctions JavaScript

Ensuite, nous pouvons parcourir les fonctions JavaScript pour voir ce qui est disponible dans le document.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Cela imprimera chaque nom de fonction JavaScript et son code correspondant sur la console. Cela est utile si vous souhaitez vérifier quelles fonctions sont actuellement présentes dans le document.

## Étape 6 : Supprimer JavaScript du PDF

 Maintenant, disons que vous souhaitez supprimer une fonction JavaScript spécifique, comme`func1`Voici comment procéder :

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 Le`Remove` La méthode prend le nom de la fonction JavaScript comme argument et le supprime du document.

## Étape 7 : Vérifier la suppression de JavaScript

 Après avoir supprimé le JavaScript, vous pouvez réimprimer les fonctions restantes pour confirmer que`func1` a été supprimé avec succès.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Cette dernière partie du code garantit que tout est en place et que les fonctions JavaScript sont mises à jour correctement.

## Conclusion

Félicitations ! Vous venez d'apprendre à ajouter et supprimer du JavaScript d'un document PDF à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité puissante peut être utilisée pour diverses tâches, de l'ajout de messages dynamiques à l'exécution de calculs ou de validations personnalisés. En manipulant du JavaScript dans un PDF, vous pouvez améliorer considérablement l'expérience utilisateur.

## FAQ

### Puis-je ajouter plusieurs fonctions JavaScript à un seul PDF ?
 Absolument ! Vous pouvez ajouter autant de fonctions JavaScript que vous le souhaitez à l'aide de`doc.JavaScript` collection.

### Que se passe-t-il si j’essaie de supprimer une fonction JavaScript inexistante ?
 Si la fonction n'existe pas, la`Remove` La méthode ne générera pas d’erreur, mais elle ne supprimera rien non plus.

### Est-il possible d'exécuter JavaScript dès l'ouverture du PDF ?
Oui ! Vous pouvez configurer JavaScript pour qu'il s'exécute sur certains déclencheurs, comme l'ouverture du document ou le clic sur un bouton.

### Puis-je modifier le JavaScript après l'avoir ajouté au PDF ?
Oui, vous pouvez charger un PDF existant, accéder à son JavaScript, modifier le code et enregistrer à nouveau le document.

### La suppression de JavaScript affecte-t-elle le reste du contenu PDF ?
Non, la suppression de JavaScript n'affecte que le script. Le contenu du PDF reste inchangé.