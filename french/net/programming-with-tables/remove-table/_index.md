---
title: Supprimer le tableau
linktitle: Supprimer le tableau
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-tables/remove-table/
---

Dans ce didacticiel, nous vous guiderons étape par étape pour supprimer un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Charger le document PDF existant
Tout d'abord, vous devez charger le document PDF existant à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF existant
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## Étape 2 : Création de l'objet TableAbsorber pour rechercher les tables
Ensuite, nous allons créer un objet TableAbsorber pour trouver les tables dans le document PDF :

```csharp
// Créer un objet TableAbsorber pour trouver les tables
TableAbsorber absorber = new TableAbsorber();
```

## Étape 3 : Visitez la première page avec l'absorbeur
Nous allons maintenant visiter la première page du document PDF utilisant l'absorbeur :

```csharp
//Visitez la première page avec l'absorbeur
absorb.Visit(pdfDocument.Pages[1]);
```

## Étape 4 : Obtenir le premier tableau de la page
Pour pouvoir supprimer le tableau, on va obtenir le premier tableau de la page :

```csharp
// Obtenir le premier tableau de la page
AbsorbedTable table = absorb.TableList[0];
```

## Étape 5 : Supprimer le tableau
Enlevons maintenant la table à l'aide de l'absorbeur :

```csharp
// supprimer le tableau
absorb.Remove(table);
```

## Étape 6 : Enregistrer le PDF
Enfin, nous enregistrons le document PDF modifié :

```csharp
// Enregistrez le PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Exemple de code source pour Supprimer la table à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF existant
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Créer un objet TableAbsorber pour rechercher des tables
TableAbsorber absorber = new TableAbsorber();

// Visitez la première page avec absorbeur
absorber.Visit(pdfDocument.Pages[1]);

// Obtenir le premier tableau de la page
AbsorbedTable table = absorber.TableList[0];

// Supprimer le tableau
absorber.Remove(table);

// Enregistrer le PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Conclusion
Félicitation ! Vous avez maintenant appris à supprimer un tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment charger le document, trouver le tableau et le supprimer. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.