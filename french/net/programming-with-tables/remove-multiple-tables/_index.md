---
title: Supprimer plusieurs tables
linktitle: Supprimer plusieurs tables
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer plusieurs tableaux dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-tables/remove-multiple-tables/
---

Dans ce didacticiel, nous vous guiderons étape par étape pour supprimer plusieurs tableaux dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter.

## Étape 1 : Charger le document PDF existant
Tout d'abord, vous devez charger le document PDF existant à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF existant
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Étape 2 : Création de l'objet TableAbsorber pour rechercher les tables
Ensuite, nous allons créer un objet TableAbsorber pour trouver les tables dans le document PDF :

```csharp
// Créer un objet TableAbsorber pour trouver les tables
TableAbsorber absorber = new TableAbsorber();
```

## Étape 3 : Visitez la deuxième page avec l'absorbeur
Nous allons maintenant visiter la deuxième page du document PDF utilisant l'absorbeur :

```csharp
// Visitez la deuxième page avec l'absorbeur
absorb.Visit(pdfDocument.Pages[1]);
```

## Étape 4 : Obtention d'une copie de la collection de tables
Pour pouvoir supprimer les tables, nous devons obtenir une copie de la collection de tables :

```csharp
// Obtenir une copie de la collection de tables
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Étape 5 : Parcourir la copie de la collection et supprimer les tables
Parcourons maintenant la copie de la collection de tables et supprimons-les une par une :

```csharp
// Parcourir la copie de la collection et supprimer les tables
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Étape 6 : Enregistrer le document
Enfin, nous enregistrons le document PDF modifié :

```csharp
// Enregistrer le document
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Exemple de code source pour supprimer plusieurs tables à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF existant
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Créer un objet TableAbsorber pour rechercher des tables
TableAbsorber absorber = new TableAbsorber();

// Visitez la deuxième page avec absorbeur
absorber.Visit(pdfDocument.Pages[1]);

// Obtenir une copie de la collection de tables
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Parcourez la copie de la collection et supprimez les tables
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Enregistrer le document
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Conclusion
Félicitation ! Vous avez maintenant appris à supprimer plusieurs tableaux dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape vous a montré comment télécharger le document, trouver les tableaux et les supprimer. Vous pouvez maintenant appliquer ces connaissances à vos propres projets.