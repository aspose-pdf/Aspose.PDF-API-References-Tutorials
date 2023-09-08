---
title: Ajouter un signet dans un fichier PDF
linktitle: Ajouter un signet dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Ajoutez facilement un signet dans un fichier PDF pour une navigation améliorée avec Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/add-bookmark/
---
L'ajout de signets dans un fichier PDF permet une navigation simple et rapide. Avec Aspose.PDF pour .NET, vous pouvez facilement ajouter un signet dans un fichier PDF en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un signet. Remplacer`"YOUR DOCUMENT DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous souhaitons ajouter un signet en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Étape 4 : Créer un objet de signet

 Dans cette étape, nous allons créer un objet signet en utilisant`OutlineItemCollection` classe et définissez ses propriétés telles que le titre, l'attribut italique, l'attribut gras et l'action à effectuer lorsque vous cliquez dessus. Voici le code correspondant :

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Étape 5 : ajouter un signet au document

 Enfin, nous ajoutons le signet créé à la collection de signets du document en utilisant le`Add` méthode du`Outlines` propriété. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemple de code source pour Ajouter un signet à l’aide d’Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Créer un objet signet
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Définir le numéro de la page de destination
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Ajoutez un signet dans la collection de plans du document.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Enregistrer la sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous disposez désormais d'un guide étape par étape pour ajouter un signet à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour améliorer la navigation dans vos documents PDF en ajoutant des signets personnalisés.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation de signets.


### FAQ pour ajouter un signet dans un fichier PDF

#### Q : Que sont les signets dans un fichier PDF ?

R : Les signets, également appelés plans, sont des éléments interactifs qui permettent la navigation et la structure dans un document PDF. Ils permettent aux utilisateurs d'accéder rapidement à des sections ou des pages spécifiques.

#### Q : Pourquoi devrais-je ajouter des signets à un fichier PDF ?

R : L'ajout de signets à un fichier PDF améliore l'expérience utilisateur et permet aux lecteurs de naviguer plus facilement dans le contenu du document. Les signets peuvent servir de table des matières ou fournir un accès rapide aux sections importantes.

#### Q : Comment importer les bibliothèques requises pour mon projet C# ?

R : Pour importer les bibliothèques nécessaires à votre projet C#, incluez les directives d'importation suivantes :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ces directives vous permettent d'accéder aux classes et méthodes nécessaires pour travailler avec des documents et des signets PDF.

#### Q : Comment puis-je spécifier le chemin d'accès au dossier de documents ?

 R : Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code source fourni avec le chemin réel vers le dossier contenant le fichier PDF auquel vous souhaitez ajouter un signet.

#### Q : Comment puis-je ouvrir un document PDF pour ajouter des signets ?

R : Pour ouvrir un document PDF et ajouter des signets, utilisez le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Remplacer`"AddBookmark.pdf"` avec le nom réel du fichier.

#### Q : Comment créer un objet signet ?

 R : Pour créer un objet signet, utilisez l'outil`OutlineItemCollection` classe. Personnalisez ses propriétés telles que le titre, le style italique, le style gras et l'action à effectuer lorsque vous cliquez dessus.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  Q : Quel est le but du`Action` property in a bookmark?

 R : Le`Action` La propriété spécifie l'action à effectuer lorsque l'utilisateur clique sur le signet. Dans cet exemple, nous utilisons le`GoToAction`class pour accéder à une page spécifique (page 2 dans ce cas).

#### Q : Comment ajouter le signet au document ?

 R : Utilisez le`Add` méthode du`Outlines` propriété pour ajouter le signet créé à la collection de signets du document.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### Q : Puis-je ajouter plusieurs favoris en utilisant cette méthode ?

R : Oui, vous pouvez répéter les étapes 4 à 8 pour ajouter plusieurs signets au document. Personnalisez les propriétés et les actions de chaque signet selon vos besoins.

#### Q : Comment puis-je enregistrer le fichier PDF mis à jour ?

 R : Enregistrez le fichier PDF mis à jour à l'aide du`Save` méthode du`pdfDocument` objet:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Q : Comment puis-je confirmer que les favoris ont été ajoutés ?

R : Ouvrez le fichier PDF généré pour vérifier que les signets spécifiés ont été ajoutés au document.

#### Q : Y a-t-il une limite au nombre de favoris que je peux ajouter ?

R : Il n'y a généralement pas de limite stricte au nombre de signets que vous pouvez ajouter, mais tenez compte de la taille et de la complexité du document pour des performances optimales.

#### Q : Puis-je personnaliser l’apparence des favoris ?

: Oui, vous pouvez personnaliser davantage l'apparence, la couleur, le style et d'autres attributs des favoris à l'aide des fonctionnalités Aspose.PDF.