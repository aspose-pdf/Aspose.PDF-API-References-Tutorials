---
title: Ajouter du HTML à l'aide de DOM
linktitle: Ajouter du HTML à l'aide de DOM
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-text/add-html-using-dom/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de contenu HTML à l'aide de DOM (Document Object Model) dans Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

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
```

## Étape 3 : Définir le répertoire du document et le chemin du fichier de sortie
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

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
 Instancier un`HtmlFragment` objet et fournir le contenu HTML souhaité. Dans le code fourni, le contenu HTML est affecté à la variable`titel`. Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Étape 7 : Définir les informations sur la marge
Ajustez les marges inférieure et supérieure du fragment HTML si nécessaire. Dans le code fourni, la marge inférieure est définie sur 10 et la marge supérieure est définie sur 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Étape 8 : ajouter le HtmlFragment à la page
 Ajouter le`HtmlFragment` s'opposer à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Étape 9 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
doc.Save(dataDir);
```

## Étape 10 : Afficher le message de réussite
Affichez un message de réussite ainsi que le chemin où le fichier PDF a été enregistré.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour ajouter du HTML à l'aide de DOM à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page à la collection de pages d'un fichier PDF
Page page = doc.Pages.Add();
// Instancier HtmlFragment avec des réseaux HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Définir les informations sur la marge inférieure
titel.Margin.Bottom = 10;
// Définir les informations sur la marge supérieure
titel.Margin.Top = 200;
// Ajouter un fragment HTML à la collection de paragraphes de la page
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez ajouté avec succès du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l'objectif de ce tutoriel ?

R : Ce didacticiel vise à fournir un guide étape par étape sur la façon d'ajouter du contenu HTML à un document PDF à l'aide du modèle d'objet de document (DOM) dans Aspose.PDF pour .NET. Il comprend des extraits de code source C# pour vous aider à comprendre et à mettre en œuvre le processus.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous prévoyez d'ajouter du contenu HTML, importez l'espace de noms suivant au début du fichier :

```csharp
using Aspose.Pdf;
```

#### Q : Comment puis-je spécifier le répertoire du document et le chemin du fichier de sortie ?

 R : Dans le code, recherchez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 R : À l'étape 4, instanciez un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

#### Q : Comment ajouter une page au document ?

 R : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection:

```csharp
Page page = doc.Pages.Add();
```

#### Q : Comment puis-je définir du contenu HTML à l'aide du DOM ?

 R : À l'étape 6, vous allez créer un`HtmlFragment` objet et attribuez-lui le contenu HTML souhaité. Le contenu HTML est affecté à la variable`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Q : Puis-je ajuster la marge du contenu HTML ?

R : Oui, à l'étape 7, vous pouvez ajuster les marges inférieure et supérieure du fragment HTML selon vos besoins :

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Q : Comment ajouter le HTMLFragment au document PDF ?

 R : À l'étape 8, vous ajouterez le`HtmlFragment` objet (`titel`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 R : Après avoir ajouté le contenu HTML et ajusté les marges, utilisez le`Save` méthode du`Document` objet pour enregistrer le document PDF :

```csharp
doc.Save(dataDir);
```

#### Q : Existe-t-il un moyen de vérifier si le processus a réussi ?

R : Bien sûr, à l'étape 10, un message de réussite s'affiche avec le chemin où le fichier PDF a été enregistré :

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris à utiliser le modèle objet de document (DOM) dans Aspose.PDF pour .NET pour ajouter du contenu HTML à un document PDF. Ces connaissances vous permettent d'améliorer vos capacités de génération de PDF.