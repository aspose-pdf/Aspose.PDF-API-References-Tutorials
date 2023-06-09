---
title: Ajouter des calques
linktitle: Ajouter des calques
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des calques aux fichiers PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec des didacticiels de code pour créer et enregistrer des PDF multicouches.
type: docs
weight: 20
url: /fr/net/programming-with-document/addlayers/
---

Pour ajouter des calques à un fichier PDF, nous utiliserons Aspose.PDF pour .NET. Cette bibliothèque nous permet de travailler efficacement avec des fichiers PDF dans des applications .NET. Suivez les instructions étape par étape ci-dessous pour ajouter des calques à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : créer un nouveau document PDF

 Commencez par créer une nouvelle instance de`Document` classe fournie par Aspose.PDF pour .NET. Cela servira de document PDF où nous ajouterons les calques.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Étape 2 : Ajouter une page au document

Ensuite, ajoutez une page au document à l'aide de la`Add` méthode de la`Pages` collecte dans le`Document` classe.

```csharp
Page page = doc.Pages.Add();
```

## Étape 3 : créer et ajouter des calques à la page

 Créer des instances de`Layer` classe pour chaque calque que vous souhaitez ajouter au fichier PDF. Spécifiez un identifiant unique et un nom pour chaque couche.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

Dans ce didacticiel, nous avons ajouté trois calques avec des couleurs et des noms différents à la page.

## Étape 4 : Enregistrer le fichier PDF

 Enregistrez le fichier PDF modifié à l'aide de la`Save` méthode de la`Document` classe.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Ce code enregistrera le fichier PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'ajout de calques aux pages PDF à l'aide d'Aspose.PDF pour .NET

```csharp            
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Conclusion

Dans cet article, nous avons fourni un guide étape par étape pour ajouter des calques aux fichiers PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions et en utilisant les didacticiels de code fournis, vous pouvez facilement incorporer des calques dans vos documents PDF. Les couches vous permettent d'organiser et de contrôler la visibilité du contenu, offrant une expérience plus interactive et personnalisable à vos utilisateurs.