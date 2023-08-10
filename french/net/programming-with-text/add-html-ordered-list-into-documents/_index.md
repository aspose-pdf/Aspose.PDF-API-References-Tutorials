---
title: Ajouter une liste ordonnée HTML dans les documents
linktitle: Ajouter une liste ordonnée HTML dans les documents
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une liste ordonnée HTML à un document à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-text/add-html-ordered-list-into-documents/
---

Dans ce didacticiel, vous apprendrez à utiliser la bibliothèque Aspose.PDF pour .NET pour ajouter une liste ordonnée HTML dans un document. Le code fourni montre les étapes nécessaires pour accomplir cette tâche.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter la liste ordonnée HTML, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définissez le répertoire du document et le chemin du fichier de sortie
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

 Ensuite, localisez la ligne qui dit`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` et remplacer`"AddHTMLOrderedListIntoDocuments_out.pdf"` avec le nom souhaité pour votre fichier PDF de sortie.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Créer un objet HtmlFragment avec le contenu HTML
Instancier un`HtmlFragment` objet avec le contenu HTML que vous souhaitez ajouter au document. Dans le code fourni, le contenu HTML est affecté à la variable`t`. Vous pouvez modifier le contenu HTML selon vos besoins.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Étape 6 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide de la`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 7 : Ajouter le HtmlFragment à la page
 Ajouter le`HtmlFragment` objecter à la page en utilisant le`Add` méthode de la`Paragraphs` collection.

```csharp
page.Paragraphs.Add(t);
```

## Étape 8 : Enregistrez le document PDF
 Enregistrez le fichier PDF obtenu à l'aide de la`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
doc.Save(outFile);
```

### Exemple de code source pour ajouter une liste ordonnée HTML dans des documents à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Chemin d'accès au document de sortie.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instancier l'objet Document
Document doc = new Document();
// Instanciez l'objet HtmlFragment avec le fragment HTML correspondant
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Ajouter une page dans la collection de pages
Page page = doc.Pages.Add();
// Ajouter HtmlFragment à l'intérieur de la page
page.Paragraphs.Add(t);
// Enregistrer le fichier PDF résultant
doc.Save(outFile);
```

## Conclusion
Vous avez ajouté avec succès une liste ordonnée HTML dans un document à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé dans le chemin du fichier de sortie spécifié.

N'oubliez pas de personnaliser le contenu HTML et d'ajuster le code en fonction de vos besoins spécifiques.