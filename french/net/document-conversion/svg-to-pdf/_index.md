---
title: SVG vers PDF
linktitle: SVG vers PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Conversion facile et rapide de SVG en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 280
url: /fr/net/document-conversion/svg-to-pdf/
---
Ce didacticiel vous guidera à travers les étapes de conversion d'un fichier SVG en fichier PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF offre une solution simple et efficace pour convertir des fichiers SVG en PDF tout en préservant la qualité et la mise en page du contenu. Suivez les étapes ci-dessous pour effectuer cette conversion.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du fichier SVG
La première étape consiste à charger le fichier SVG dans un`Document` objet à l'aide de l'option de chargement SVG (`SvgLoadOptions`). Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier l'objet LoadOption à l'aide de l'option de chargement SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Créer un objet Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier SVG.

## Étape 2 : Convertir en PDF
 La deuxième étape consiste à convertir le document SVG en document PDF à l'aide de la`Save` méthode de la`Document` objet. Utilisez le code suivant :

```csharp
// Enregistrez le document PDF résultant
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Assurez-vous de spécifier le chemin et le nom de fichier souhaités pour le fichier PDF résultant.

### Exemple de code source pour SVG en PDF en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet LoadOption à l'aide de l'option de chargement SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Créer un objet Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Enregistrez le document PDF résultant
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à convertir un fichier SVG en fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes ci-dessus, vous pouvez facilement effectuer cette conversion. Utilisez cette méthode pour convertir vos fichiers SVG en PDF et profitez de la flexibilité et de la qualité d'Aspose.PDF.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre diverses fonctionnalités, dont la conversion de fichiers SVG en PDF.

#### Q : Pourquoi voudrais-je convertir un fichier SVG en PDF ?

: Les fichiers SVG (Scalable Vector Graphics) sont couramment utilisés pour les graphiques vectoriels sur le Web. La conversion d'un fichier SVG au format PDF facilite le partage, l'impression et l'intégration du contenu graphique.

#### Q : Comment puis-je charger un fichier SVG et le convertir en PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Pour charger un fichier SVG, vous pouvez utiliser le`SvgLoadOptions` classe pour spécifier l'option de chargement SVG. Ensuite, créez un`Document` objet et chargez-y le fichier SVG. Enfin, utilisez le`Save` méthode de la`Document` objet pour convertir et enregistrer le SVG au format PDF.

#### Q : Puis-je personnaliser le PDF de sortie lors de la conversion ?

R : Oui, vous pouvez personnaliser le PDF de sortie pendant le processus de conversion. Aspose.PDF pour .NET fournit diverses options et propriétés pour contrôler l'apparence et la mise en page du document PDF.

#### Q : La qualité du contenu du SVG est-elle préservée dans le PDF résultant ?

R : Oui, Aspose.PDF pour .NET garantit la préservation de la qualité et de la mise en page du contenu lors de la conversion SVG en PDF, assurant une transition transparente entre les formats.