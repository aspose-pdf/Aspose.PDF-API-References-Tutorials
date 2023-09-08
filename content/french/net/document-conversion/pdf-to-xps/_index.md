---
title: PDF vers XPS
linktitle: PDF vers XPS
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir un PDF en XPS à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 220
url: /fr/net/document-conversion/pdf-to-xps/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier PDF au format XPS (XML Paper Spécification) à l'aide d'Aspose.PDF pour .NET. Le format XPS est un format de fichier XML utilisé pour représenter électroniquement des documents. En suivant les étapes ci-dessous, vous pourrez convertir un fichier PDF au format XPS.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du document PDF
Dans cette étape, nous allons charger le fichier PDF source à l'aide d'Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Instancier les options de sauvegarde XPS
Après avoir chargé le fichier PDF, nous instancierons les options de sauvegarde XPS. Utilisez le code suivant :

```csharp
// Instancier les options de sauvegarde XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Étape 3 : enregistrement du fichier XPS résultant
Nous allons maintenant enregistrer le fichier PDF converti au format XPS. Utilisez le code suivant :

```csharp
// Enregistrez le document XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Le code ci-dessus enregistre le fichier PDF converti au format XPS avec le nom de fichier`"PDFToXPS_out.xps"`.


### Exemple de code source pour PDF vers XPS à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger un document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instancier les options d'enregistrement XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Enregistrez le document XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format XPS à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant pouvoir convertir un fichier PDF au format XPS. Cette fonctionnalité est utile lorsque vous souhaitez afficher ou imprimer des documents PDF au format XPS.

### FAQ

#### Q : Le format XPS est-il adapté à la compatibilité multiplateforme ?

R : Le format XPS, étant un format de fichier basé sur XML, est indépendant de la plate-forme et peut être visualisé sur différents systèmes d'exploitation et appareils. Les fichiers XPS sont pris en charge par défaut sur les plates-formes Windows, et certaines applications et visionneuses tierces peuvent être disponibles pour d'autres plates-formes.

#### Q : Aspose.PDF pour .NET peut-il gérer des fichiers PDF complexes comportant plusieurs pages et images lors de la conversion XPS ?

R : Oui, Aspose.PDF pour .NET peut gérer des fichiers PDF complexes comportant plusieurs pages et images lors de la conversion XPS. Il conserve avec précision la mise en page, les images et le contenu textuel du PDF tout en le convertissant au format XPS.

#### Q : Est-il possible de spécifier des paramètres ou des options supplémentaires pendant le processus de conversion XPS ?

 R : Oui, Aspose.PDF pour .NET propose diverses options et paramètres qui peuvent être personnalisés pendant le processus de conversion XPS. Vous pouvez contrôler la compression de l'image, l'intégration des polices et d'autres paramètres à l'aide du`XpsSaveOptions` classe.

#### Q : Les PDF protégés par mot de passe peuvent-ils être convertis au format XPS à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, Aspose.PDF pour .NET prend en charge la conversion des PDF protégés par mot de passe au format XPS. Lors du chargement d'un PDF protégé par mot de passe, vous pouvez fournir le mot de passe à l'aide du`Document` constructeur de classe ou en définissant le`Password` propriété avant de charger le PDF.