---
title: Ajouter du HTML à l'aide de DOM et de PDF Overwrite
linktitle: Ajouter du HTML à l'aide de DOM et écraser
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter du contenu HTML à l'aide de DOM et de l'écrasement PDF dans Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de contenu HTML à l'aide de DOM (Document Object Model) dans Aspose.PDF pour .NET. De plus, vous apprendrez à remplacer les styles du contenu HTML. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter le contenu HTML, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : définissez le répertoire du document et le chemin du fichier de sortie
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode de la`Pages`collection. Dans le code fourni, la nouvelle page est attribuée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 6 : Créer un fragment HTML avec le contenu HTML
 Instancier un`HtmlFragment` objet et fournir le contenu HTML souhaité. Dans le code fourni, le contenu HTML est attribué à la variable`title`Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Étape 7 : Remplacer les styles du contenu HTML
 Pour écraser les styles du contenu HTML, vous pouvez modifier le`TextState` propriétés de la`HtmlFragment` objet. Dans le code fourni, la famille de polices est modifiée en « Arial » et la taille de police est définie sur 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Étape 8 : Définir les informations de marge
Ajustez les marges inférieure et supérieure du fragment HTML si nécessaire. Dans le code fourni, la marge inférieure est définie sur 10 et la marge supérieure sur 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Étape 9 : ajouter le fragment HTML à la page
 Ajoutez le`HtmlFragment` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(title);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de la`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Ajouter du HTML à l'aide de DOM et écraser à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Instancier HtmlFragment avec des contenus HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famille de polices « Verdana » sera réinitialisée sur « Arial »
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Définir les informations de marge inférieure
title.Margin.Bottom = 10;
// Définir les informations de marge supérieure
title.Margin.Top = 400;
// Ajouter un fragment HTML à la collection de paragraphes de la page
page.Paragraphs.Add(title);
// Enregistrer le fichier PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
```

## Conclusion
Vous avez ajouté avec succès du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET et remplacé les styles du contenu HTML. Le fichier PDF résultant se trouve désormais dans le chemin de fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif de ce tutoriel ?

R : Ce didacticiel est conçu pour vous guider tout au long du processus d'ajout de contenu HTML à un document PDF à l'aide du modèle d'objet de document (DOM) dans Aspose.PDF pour .NET. De plus, vous apprendrez à remplacer les styles du contenu HTML, ce qui vous permettra de personnaliser son apparence. Le didacticiel fournit des extraits de code source C# pour illustrer les étapes requises.

#### Q : Quels espaces de noms dois-je importer pour ce tutoriel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter du contenu HTML, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire du document et le chemin du fichier de sortie ?

 A : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 A : À l’étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Document doc = new Document();
```

#### Q : Comment ajouter une page au document ?

 A : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'`Add` méthode de la`Pages` collection:

```csharp
Page page = doc.Pages.Add();
```

#### Q : Comment puis-je définir du contenu HTML à l’aide du DOM ?

 A : À l'étape 6, vous allez créer un`HtmlFragment` objet et lui attribuer le contenu HTML souhaité. Le contenu HTML est attribué à la variable`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q : Comment puis-je écraser les styles du contenu HTML ?

 A : À l'étape 7, vous écraserez les styles du contenu HTML en modifiant le`TextState` propriétés de la`HtmlFragment` objet. Par exemple, vous pouvez modifier la famille de polices en « Arial » et définir la taille de police sur 20 :

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q : Puis-je ajuster la marge du contenu HTML ?

R : Oui, à l’étape 8, vous pouvez ajuster les marges inférieure et supérieure du fragment HTML selon vos besoins :

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q : Comment ajouter le fragment HTML au document PDF ?

 A : À l'étape 9, vous ajouterez le`HtmlFragment` objet (`title`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(title);
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 A : Après avoir ajouté le contenu HTML et personnalisé ses styles, utilisez le`Save` méthode de la`Document` objet pour enregistrer le document PDF :

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à intégrer du contenu HTML à l'aide du modèle d'objet de document (DOM) dans Aspose.PDF pour .NET. De plus, vous avez acquis la possibilité de remplacer les styles pour personnaliser l'apparence du contenu HTML dans le document PDF obtenu.