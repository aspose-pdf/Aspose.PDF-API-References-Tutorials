---
title: Ajouter un retrait aux lignes suivantes
linktitle: Ajouter un retrait aux lignes suivantes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter un retrait de lignes suivantes au texte à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-text/add-subsequent-lines-indent/
---

Ce didacticiel vous guidera tout au long du processus d'ajout d'un retrait de lignes au texte à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter le retrait des lignes suivantes, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide de la`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Étape 6 : Créer un TextFragment avec le retrait des lignes suivantes
 Instancier un`TextFragment` objet et fournissez le texte souhaité. Dans le code fourni, le texte est affecté à la variable`text` . Ensuite, initialisez`TextFormattingOptions` pour le`TextFragment` et précisez le`SubsequentLinesIndent` valeur.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Étape 7 : Ajoutez le TextFragment à la page
 Ajouter le`TextFragment` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(text);
```

## Étape 8 : répétez les étapes 6 et 7 pour les lignes supplémentaires
Pour ajouter des lignes suivantes avec le même retrait, répétez les étapes 6 et 7 pour chaque ligne. Mettez à jour le contenu du texte si nécessaire.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Étape 9 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exemple de code source pour Ajouter un retrait des lignes suivantes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet document
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initilize TextFormattingOptions pour le fragment de texte et spécifiez la valeur de l'IndentSuivantLines
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusion
Vous avez ajouté avec succès le retrait des lignes suivantes au texte à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.