---
title: Ajouter du HTML à l'aide de DOM et écraser
linktitle: Ajouter du HTML à l'aide de DOM et écraser
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Ce didacticiel vous guidera tout au long du processus d'ajout de contenu HTML à l'aide de DOM (Document Object Model) dans Aspose.PDF pour .NET. De plus, vous apprendrez à écraser les styles du contenu HTML. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter le contenu HTML, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définissez le répertoire du document et le chemin du fichier de sortie
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide de la`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 6 : Créer un HtmlFragment avec le contenu HTML
Instancier un`HtmlFragment` objet et fournissez le contenu HTML souhaité. Dans le code fourni, le contenu HTML est affecté à la variable`title`. Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Étape 7 : remplacer les styles du contenu HTML
 Pour écraser les styles du contenu HTML, vous pouvez modifier le`TextState` propriétés de la`HtmlFragment` objet. Dans le code fourni, la famille de polices est remplacée par "Arial" et la taille de police est définie sur 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Étape 8 : Définir les informations de marge
Ajustez les marges inférieure et supérieure du fragment HTML si nécessaire. Dans le code fourni, la marge inférieure est définie sur 10 et la marge supérieure est définie sur 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Étape 9 : Ajouter le HtmlFragment à la page
 Ajouter le`HtmlFragment` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(title);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Add HTMLUsing DOMAnd Overwrite using Aspose.PDF for .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Instancier HtmlFragment avec des contenus HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famille de polices de 'Verdana' sera réinitialisée à 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Définir les informations sur la marge inférieure
title.Margin.Bottom = 10;
// Définir les informations sur la marge supérieure
title.Margin.Top = 400;
// Ajouter un fragment HTML à la collection de paragraphes de la page
page.Paragraphs.Add(title);
// Enregistrer le fichier PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
```

## Conclusion
Vous avez ajouté avec succès du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET et remplacé les styles du contenu HTML. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.