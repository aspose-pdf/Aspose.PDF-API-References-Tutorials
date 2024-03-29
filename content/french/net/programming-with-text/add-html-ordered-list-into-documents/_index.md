---
title: Ajouter une liste ordonnée HTML dans les documents
linktitle: Ajouter une liste HTML ordonnée dans des documents
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter une liste ordonnée HTML à un document à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-text/add-html-ordered-list-into-documents/
---
Dans ce didacticiel, vous apprendrez à utiliser la bibliothèque Aspose.PDF pour .NET pour ajouter une liste HTML ordonnée dans un document. Le code fourni montre les étapes nécessaires pour accomplir cette tâche.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez ajouter la liste ordonnée HTML, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire du document et le chemin du fichier de sortie
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

 Ensuite, localisez la ligne qui dit`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` et remplacer`"AddHTMLOrderedListIntoDocuments_out.pdf"` avec le nom souhaité pour votre fichier PDF de sortie.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Créez un objet HtmlFragment avec le contenu HTML
 Instancier un`HtmlFragment` objet avec le contenu HTML que vous souhaitez ajouter au document. Dans le code fourni, le contenu HTML est affecté à la variable`t`. Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Étape 6 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 7 : ajouter le HtmlFragment à la page
 Ajouter le`HtmlFragment` opposer à la page en utilisant le`Add` méthode du`Paragraphs` collection.

```csharp
page.Paragraphs.Add(t);
```

## Étape 8 : Enregistrez le document PDF
 Enregistrez le fichier PDF résultant à l'aide du`Save` méthode du`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
doc.Save(outFile);
```

### Exemple de code source pour ajouter une liste HTMLOrdered dans des documents à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Le chemin d'accès au document de sortie.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instancier l'objet Document
Document doc = new Document();
// Instancier l'objet HtmlFragment avec le fragment HTML correspondant
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Ajouter une page dans la collection de pages
Page page = doc.Pages.Add();
// Ajouter HtmlFragment à l'intérieur de la page
page.Paragraphs.Add(t);
// Enregistrer le fichier PDF résultant
doc.Save(outFile);
```

## Conclusion
Vous avez ajouté avec succès une liste triée HTML dans un document à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

N'oubliez pas de personnaliser le contenu HTML et d'ajuster le code en fonction de vos besoins spécifiques.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel vise à vous guider tout au long du processus d'ajout d'une liste ordonnée HTML dans un document à l'aide de la bibliothèque Aspose.PDF pour .NET. Il fournit des instructions étape par étape et des extraits de code pour vous aider à accomplir cette tâche.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Vous devez importer les espaces de noms suivants en haut de votre fichier de code :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment puis-je spécifier le répertoire du document et le chemin du fichier de sortie ?

 R : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents. Trouvez également la ligne`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` et remplacer`"AddHTMLOrderedListIntoDocuments_out.pdf"` avec le nom du fichier PDF de sortie souhaité.

#### Q : Puis-je personnaliser le contenu HTML ajouté au document ?

 R : Absolument ! À l'étape 5, vous allez créer un`HtmlFragment` objet nommé`t` qui contient le contenu HTML. Vous pouvez modifier le contenu HTML dans les backticks en fonction de vos besoins.

#### Q : Comment ajouter la liste ordonnée HTML à une page du document ?

 R : À l'étape 7, vous ajouterez le`HtmlFragment` objet (`t` ) à la page en utilisant le`Add` méthode du`Paragraphs`collection. Cela intégrera de manière transparente la liste ordonnée HTML dans le document.

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 R : Après avoir ajouté le contenu HTML et l'avoir organisé sur une page, vous pouvez enregistrer le document PDF à l'aide du`Save` méthode du`Document` objet. Assurez-vous de fournir le chemin d'accès correct au fichier de sortie que vous avez défini précédemment.

#### Q : Pouvez-vous fournir un résumé de l’exemple de code source pour référence ?

R : Certainement ! Voici une version résumée de l'exemple de code source fourni dans ce didacticiel :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris avec succès comment exploiter la bibliothèque Aspose.PDF pour .NET pour incorporer une liste ordonnée HTML dans un document. Ces nouvelles connaissances peuvent être appliquées pour améliorer vos processus de création et de manipulation de documents.