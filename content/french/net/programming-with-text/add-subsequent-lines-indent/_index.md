---
title: Ajouter un retrait aux lignes suivantes dans le fichier PDF
linktitle: Ajouter un retrait aux lignes suivantes dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter un retrait de lignes ultérieures au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-text/add-subsequent-lines-indent/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de retraits de lignes ultérieures au texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter un retrait pour les lignes suivantes, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est attribuée à la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Étape 6 : créer un fragment de texte avec des lignes ultérieures en retrait
 Instancier un`TextFragment` objet et fournir le texte souhaité. Dans le code fourni, le texte est attribué à la variable`text` . Ensuite, initialisez`TextFormattingOptions` pour le`TextFragment` et précisez le`SubsequentLinesIndent` valeur.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Étape 7 : ajouter le fragment de texte à la page
 Ajoutez le`TextFragment` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(text);
```

## Étape 8 : Répétez les étapes 6 et 7 pour des lignes supplémentaires
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
 Enregistrez le document PDF à l'aide de la`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exemple de code source pour l'ajout d'un retrait de lignes ultérieures à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet de document
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Initialisez TextFormattingOptions pour le fragment de texte et spécifiez la valeur FollowingLinesIndent
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
Vous avez ajouté avec succès un retrait aux lignes suivantes du texte à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant se trouve désormais dans le chemin de fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif de ce tutoriel ?

R : Ce didacticiel fournit un guide complet sur la façon d'ajouter un retrait de lignes ultérieures au texte d'un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Il comprend des exemples de code source C# pour illustrer les étapes nécessaires à cette fin.

#### Q : Quels espaces de noms dois-je importer pour ce tutoriel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter un retrait pour les lignes suivantes, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 A : À l’étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Q : Comment ajouter une page au document ?

 A : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'`Add` méthode de la`Pages` collection:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Q : Comment puis-je ajouter un retrait aux lignes suivantes du texte ?

 A : À l'étape 6, vous allez créer un`TextFragment` objet et lui assigner le texte souhaité. Ensuite, vous initialiserez`TextFormattingOptions` pour le`TextFragment` et précisez le`SubsequentLinesIndent` valeur:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Q : Comment ajouter le TextFragment au document PDF ?

 A : À l'étape 7, vous ajouterez le`TextFragment` objet (`text`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(text);
```

#### Q : Puis-je répéter le processus pour des lignes supplémentaires ?

 : Oui, à l'étape 8, vous pouvez répéter le processus pour des lignes supplémentaires avec le même retrait en créant de nouvelles`TextFragment` objets et les ajouter à la collection de paragraphes de la page.

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 A : Après avoir ajouté le texte avec les lignes suivantes en retrait, utilisez le`Save` méthode de la`Document` objet pour enregistrer le document PDF :

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à améliorer la lisibilité du texte dans un document PDF en ajoutant un retrait aux lignes suivantes à l'aide d'Aspose.PDF pour .NET. Cette technique peut être utile pour différents types de documents et de rapports.