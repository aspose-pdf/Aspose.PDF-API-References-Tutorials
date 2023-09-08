---
title: Ajouter un retrait aux lignes suivantes dans un fichier PDF
linktitle: Ajouter un retrait aux lignes suivantes dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter un retrait aux lignes suivantes au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-text/add-subsequent-lines-indent/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de retrait de lignes suivantes au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter un retrait aux lignes suivantes, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Étape 6 : Créer un TextFragment avec le retrait des lignes suivantes
 Instancier un`TextFragment` objet et fournir le texte souhaité. Dans le code fourni, le texte est affecté à la variable`text` . Ensuite, initialisez`TextFormattingOptions` pour le`TextFragment`et préciser le`SubsequentLinesIndent` valeur.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Étape 7 : ajouter le TextFragment à la page
 Ajouter le`TextFragment` s'opposer à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(text);
```

## Étape 8 : répétez les étapes 6 et 7 pour les lignes supplémentaires
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

## Étape 9 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet. Spécifiez le chemin du fichier de sortie.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exemple de code source pour ajouter un retrait de lignes suivantes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet document
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initilisez TextFormattingOptions pour le fragment de texte et spécifiez la valeur SuccessLinesIndent
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
Vous avez réussi à ajouter le retrait des lignes suivantes au texte à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l'objet de ce didacticiel ?

R : Ce didacticiel fournit un guide complet sur la manière d'ajouter des retraits de lignes ultérieures au texte d'un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Il comprend des exemples de code source C# pour illustrer les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous avez l'intention d'ajouter le retrait des lignes suivantes, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 R : À l'étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Q : Comment ajouter une page au document ?

 R : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Q : Comment puis-je ajouter un retrait aux lignes suivantes au texte ?

 R : À l'étape 6, vous allez créer un`TextFragment` objet et attribuez-lui le texte souhaité. Ensuite, vous initialiserez`TextFormattingOptions` pour le`TextFragment`et préciser le`SubsequentLinesIndent` valeur:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Q : Comment ajouter le TextFragment au document PDF ?

 R : À l'étape 7, vous ajouterez le`TextFragment` objet (`text`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(text);
```

#### Q : Puis-je répéter le processus pour des lignes supplémentaires ?

 R : Oui, à l'étape 8, vous pouvez répéter le processus pour des lignes supplémentaires avec le même retrait en créant un nouveau`TextFragment` objets et en les ajoutant à la collection de paragraphes de la page.

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 R : Après avoir ajouté le texte avec les lignes suivantes en retrait, utilisez le`Save` méthode du`Document` objet pour enregistrer le document PDF :

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris avec succès comment améliorer la lisibilité du texte dans un document PDF en ajoutant un retrait aux lignes suivantes à l'aide d'Aspose.PDF pour .NET. Cette technique peut être utile pour différents types de documents et de rapports.