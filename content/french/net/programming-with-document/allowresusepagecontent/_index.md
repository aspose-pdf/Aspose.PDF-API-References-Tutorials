---
title: Autoriser la réutilisation du contenu de la page
linktitle: Autoriser la réutilisation du contenu de la page
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment optimiser les PDF en activant la fonctionnalité « Autoriser la réutilisation du contenu de la page » à l'aide d'Aspose.PDF pour .NET. Réduisez la taille du fichier et améliorez les performances.
type: docs
weight: 50
url: /fr/net/programming-with-document/allowresusepagecontent/
---
Dans ce didacticiel, nous expliquerons comment activer la fonctionnalité « Autoriser la réutilisation du contenu de la page » à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité optimise le document PDF en réutilisant le contenu de la page, en réduisant la taille du fichier et en améliorant les performances. Suivez le guide étape par étape ci-dessous :

## Étape 1 : Charger le document PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 2 : définissez l'option AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Étape 3 : Optimiser le document PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 4 : Enregistrez le document mis à jour

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Étape 5 : Vérifiez la réduction de la taille du fichier

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Toutes nos félicitations! Vous avez autorisé avec succès la réutilisation du contenu de la page dans votre document PDF.

### Exemple de code source pour autoriser la réutilisation du contenu de la page à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Définir l’option AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Enregistrer le document mis à jour
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Vous pouvez désormais optimiser efficacement vos documents PDF en permettant la réutilisation du contenu des pages.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment activer la fonctionnalité « Autoriser la réutilisation du contenu de la page » à l'aide d'Aspose.PDF pour .NET. En suivant le guide étape par étape fourni et en utilisant le code source C#, vous pouvez optimiser efficacement vos documents PDF en permettant la réutilisation du contenu des pages. Cette optimisation se traduit par des fichiers PDF plus petits, ce qui peut entraîner des temps de chargement plus rapides et de meilleures performances lors du traitement de documents PDF volumineux. Aspose.PDF pour .NET fournit une solution robuste et conviviale pour l'optimisation PDF, vous permettant de créer facilement des fichiers PDF efficaces et de haute qualité.

### FAQ

#### Q : Quel est le but d'activer la fonctionnalité « Autoriser la réutilisation du contenu de la page » dans un document PDF ?

R : L'activation de la fonctionnalité « Autoriser la réutilisation du contenu de la page » dans un document PDF optimise le fichier en réutilisant le contenu de la page, ce qui réduit la taille du fichier et améliore les performances globales. Cette optimisation se traduit par des fichiers PDF plus petits sans compromettre la qualité du contenu.

#### Q : Comment fonctionne la fonctionnalité « Autoriser la réutilisation du contenu de la page » ?

R : Lorsque la fonctionnalité « Autoriser la réutilisation du contenu de la page » est activée, les objets de page identiques dans le document PDF sont partagés et réutilisés, au lieu d'être dupliqués pour chaque occurrence. Ce partage du contenu de la page réduit considérablement la taille globale du fichier.

#### Q : Puis-je annuler l'optimisation et restaurer le document d'origine ?

R : Non, une fois l'optimisation avec "Autoriser la réutilisation du contenu de la page" effectuée et le document PDF enregistré, les modifications sont permanentes. Il est conseillé de conserver une sauvegarde du document original avant d'effectuer toute optimisation.

#### Q : L'activation de cette fonctionnalité affectera-t-elle l'apparence visuelle ou le contenu du document PDF ?

R : L'activation de la fonctionnalité « Autoriser la réutilisation du contenu de la page » n'affecte pas l'apparence visuelle ou le contenu du document PDF. Il optimise uniquement la structure interne du fichier pour réduire la redondance et améliorer l'efficacité.

#### Q : Aspose.PDF pour .NET est-il une solution fiable pour l'optimisation et la manipulation de PDF ?

R : Oui, Aspose.PDF pour .NET est une bibliothèque fiable et riche en fonctionnalités pour l'optimisation et la manipulation de PDF. Il offre de nombreuses options pour optimiser les fichiers PDF, notamment en réduisant la taille du fichier, en supprimant les ressources inutilisées et en améliorant les performances globales.