---
title: Ajouter du HTML à l'aide de DOM
linktitle: Ajouter du HTML à l'aide de DOM
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-text/add-html-using-dom/
---
Ce didacticiel vous guidera tout au long du processus d'ajout de contenu HTML à l'aide de DOM (Document Object Model) dans Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

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
```

## Étape 3 : définissez le répertoire du document et le chemin du fichier de sortie
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

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
 Instancier un`HtmlFragment` objet et fournir le contenu HTML souhaité. Dans le code fourni, le contenu HTML est attribué à la variable`titel`Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Étape 7 : Définir les informations de marge
Ajustez les marges inférieure et supérieure du fragment HTML si nécessaire. Dans le code fourni, la marge inférieure est définie sur 10 et la marge supérieure sur 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Étape 8 : ajouter le fragment HTML à la page
 Ajoutez le`HtmlFragment` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Étape 9 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de la`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
doc.Save(dataDir);
```

## Étape 10 : Afficher le message de réussite
Afficher un message de réussite ainsi que le chemin où le fichier PDF a été enregistré.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Ajouter du HTML à l'aide de DOM avec Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet Document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Instancier HtmlFragment avec des contenus HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Définir les informations de marge inférieure
titel.Margin.Bottom = 10;
// Définir les informations de marge supérieure
titel.Margin.Top = 200;
// Ajouter un fragment HTML à la collection de paragraphes de la page
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez ajouté avec succès du contenu HTML à l'aide de DOM dans Aspose.PDF pour .NET. Le fichier PDF résultant se trouve désormais dans le chemin de fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif de ce tutoriel ?

R : Ce didacticiel vise à fournir un guide étape par étape sur la façon d'ajouter du contenu HTML à un document PDF à l'aide du modèle d'objet de document (DOM) dans Aspose.PDF pour .NET. Il comprend des extraits de code source C# pour vous aider à comprendre et à mettre en œuvre le processus.

#### Q : Quels espaces de noms dois-je importer pour ce tutoriel ?

R : Dans le fichier de code dans lequel vous prévoyez d’ajouter du contenu HTML, importez l’espace de noms suivant au début du fichier :

```csharp
using Aspose.Pdf;
```

#### Q : Comment spécifier le répertoire du document et le chemin du fichier de sortie ?

 A : Dans le code, recherchez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 A : À l’étape 4, instanciez un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

#### Q : Comment ajouter une page au document ?

 A : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'`Add` méthode de la`Pages` collection:

```csharp
Page page = doc.Pages.Add();
```

#### Q : Comment puis-je définir du contenu HTML à l’aide du DOM ?

 A : À l'étape 6, vous allez créer un`HtmlFragment` objet et lui attribuer le contenu HTML souhaité. Le contenu HTML est attribué à la variable`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Q : Puis-je ajuster la marge du contenu HTML ?

R : Oui, à l’étape 7, vous pouvez ajuster les marges inférieure et supérieure du fragment HTML selon vos besoins :

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Q : Comment ajouter le fragment HTML au document PDF ?

 A : À l'étape 8, vous ajouterez le`HtmlFragment` objet (`titel`) à la collection de paragraphes de la page :

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 A : Après avoir ajouté le contenu HTML et ajusté les marges, utilisez le`Save` méthode de la`Document` objet pour enregistrer le document PDF :

```csharp
doc.Save(dataDir);
```

#### Q : Existe-t-il un moyen de vérifier si le processus a réussi ?

R : Bien sûr, à l’étape 10, un message de réussite s’affiche avec le chemin où le fichier PDF a été enregistré :

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Q : Quel est le point clé à retenir de ce tutoriel ?

: En suivant ce didacticiel, vous avez appris à utiliser le modèle d'objet de document (DOM) dans Aspose.PDF pour .NET pour ajouter du contenu HTML à un document PDF. Ces connaissances vous permettent d'améliorer vos capacités de génération de PDF.