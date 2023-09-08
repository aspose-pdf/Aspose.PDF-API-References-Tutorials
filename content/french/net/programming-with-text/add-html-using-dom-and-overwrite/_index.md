---
title: Ajouter du HTML à l'aide de l'écrasement DOM et PDF
linktitle: Ajouter du HTML à l'aide de DOM et écraser
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter du contenu HTML à l'aide de l'écrasement DOM et PDF dans Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de contenu HTML à l'aide de DOM (Document Object Model) dans Aspose.PDF pour .NET. De plus, vous apprendrez à écraser les styles du contenu HTML. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter le contenu HTML, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire du document et le chemin du fichier de sortie
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 6 : Créez un HtmlFragment avec le contenu HTML
 Instancier un`HtmlFragment` objet et fournir le contenu HTML souhaité. Dans le code fourni, le contenu HTML est affecté à la variable`title`. Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Étape 7 : écraser les styles du contenu HTML
 Pour écraser les styles du contenu HTML, vous pouvez modifier le`TextState` propriétés du`HtmlFragment` objet. Dans le code fourni, la famille de polices est modifiée en "Arial" et la taille de police est définie sur 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Étape 8 : Définir les informations sur la marge
Ajustez les marges inférieure et supérieure du fragment HTML si nécessaire. Dans le code fourni, la marge inférieure est définie sur 10 et la marge supérieure est définie sur 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Étape 9 : ajouter le HtmlFragment à la page
 Ajouter le`HtmlFragment` s'opposer à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(title);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour ajouter du HTML à l'aide de DOM et écraser à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page à la collection de pages d'un fichier PDF
Page page = doc.Pages.Add();
// Instancier HtmlFragment avec des réseaux HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La famille de polices de « Verdana » sera réinitialisée à « Arial »
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
Vous avez ajouté avec succès du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET et écrasé les styles du contenu HTML. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l'objet de ce didacticiel ?

R : Ce didacticiel est conçu pour vous guider tout au long du processus d'ajout de contenu HTML à un document PDF à l'aide du modèle objet de document (DOM) dans Aspose.PDF pour .NET. De plus, vous apprendrez à écraser les styles du contenu HTML, vous permettant ainsi de personnaliser son apparence. Le didacticiel fournit des extraits de code source C# pour illustrer les étapes requises.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter du contenu HTML, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment puis-je spécifier le répertoire du document et le chemin du fichier de sortie ?

 R : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 R : À l'étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Document doc = new Document();
```

#### Q : Comment ajouter une page au document ?

 R : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection:

```csharp
Page page = doc.Pages.Add();
```

#### Q : Comment puis-je définir du contenu HTML à l'aide du DOM ?

 R : À l'étape 6, vous allez créer un`HtmlFragment` objet et attribuez-lui le contenu HTML souhaité. Le contenu HTML est affecté à la variable`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q : Comment puis-je écraser les styles du contenu HTML ?

 R : À l'étape 7, vous écraserez les styles du contenu HTML en modifiant le`TextState` propriétés du`HtmlFragment` objet. Par exemple, vous pouvez modifier la famille de polices en « Arial » et définir la taille de police sur 20 :

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q : Puis-je ajuster la marge du contenu HTML ?

R : Oui, à l'étape 8, vous pouvez ajuster les marges inférieure et supérieure du fragment HTML selon vos besoins :

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q : Comment ajouter le HtmlFragment au document PDF ?

 R : À l'étape 9, vous ajouterez le`HtmlFragment` objet (`title`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(title);
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 R : Après avoir ajouté le contenu HTML et personnalisé ses styles, utilisez le`Save` méthode du`Document` objet pour enregistrer le document PDF :

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris avec succès comment incorporer du contenu HTML à l'aide du modèle objet de document (DOM) dans Aspose.PDF pour .NET. De plus, vous avez la possibilité d'écraser les styles pour personnaliser l'apparence du contenu HTML dans le document PDF résultant.