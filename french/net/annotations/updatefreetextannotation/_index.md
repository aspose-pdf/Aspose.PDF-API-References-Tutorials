---
title: Mettre à jour l'annotation de texte libre
linktitle: Mettre à jour l'annotation de texte libre
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment mettre à jour la fonctionnalité d'annotation de texte libre d'Aspose.PDF pour .NET à l'aide du code source C#.
type: docs
weight: 160
url: /fr/net/annotations/updatefreetextannotation/
---
Dans cet article, nous fournirons un guide étape par étape pour expliquer le code source C # suivant de la fonctionnalité Mettre à jour l'annotation de texte libre d'Aspose.PDF pour .NET. Nous allons parcourir chaque ligne de code et expliquer ce qu'il fait, afin que même les débutants puissent le comprendre.

Expliquons maintenant chaque ligne du code ci-dessus étape par étape :

## Étape 1 : Définir le répertoire de documents

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Dans cette ligne, nous définissons le chemin d'accès au répertoire contenant le document PDF que nous voulons mettre à jour.

## Étape 2 : Ouvrir le document PDF

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 Ici, nous ouvrons le document PDF en utilisant Aspose.PDF's`Document` classe et en spécifiant le chemin d'accès au fichier PDF d'entrée.

## Étape 3 : Mise à jour de la taille de la police et de la couleur de l'annotation de texte libre

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 Dans cette étape, nous mettons à jour la taille de la police et la couleur de la première annotation de texte libre sur la deuxième page du document PDF. Nous le faisons en accédant au`TextStyle` propriété de la`FreeTextAnnotation` objet et en définissant son`FontSize` et`Color` propriétés à 18 et Green, respectivement.

## Étape 4 : Gestion des exceptions

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 Ceci est une norme`try-catch` qui intercepte toutes les exceptions pouvant survenir lors de l'exécution du code et imprime le message d'erreur sur la console.

## Conclusion

Dans cet article, nous avons fourni un guide étape par étape pour expliquer le code source C# de la fonctionnalité Mettre à jour l'annotation de texte libre d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement mettre à jour la taille de police et la couleur des annotations de texte libre dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour la mise à jour de l'annotation de texte libre à l'aide d'Aspose.PDF pour .NET

Avant de plonger dans l'explication du code, examinons d'abord le code lui-même. Cet exemple de code montre comment mettre à jour les propriétés d'une annotation de texte libre dans un document PDF à l'aide d'Aspose.PDF pour .NET.

```csharp
try
{
    // Chemin d'accès au répertoire des documents.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Ouvrir le document
    Document doc1 = new Document(dataDir + "input.pdf");

    // Définissez la taille de la police et la couleur de l'annotation :
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```