---
title: Extraire des paragraphes dans un fichier PDF
linktitle: Extraire des paragraphes dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire des paragraphes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-text/extract-paragraphs/
---
Ce didacticiel vous guidera tout au long du processus d'extraction de paragraphes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez extraire les paragraphes, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Ouvrir le document PDF
 Ouvrez un document PDF existant à l'aide de la`Document`constructeur et en passant le chemin vers le fichier PDF d'entrée.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 5 : Extraire les paragraphes
 Instancier le`ParagraphAbsorber` classe et utilise son`Visit` méthode pour extraire des paragraphes du document.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Étape 6 : Parcourir les paragraphes
Parcourez les paragraphes extraits pour accéder au contenu du texte. Utilisez des boucles imbriquées pour parcourir les sections et les lignes de chaque paragraphe.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Exemple de code source pour extraire des paragraphes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir un fichier PDF existant
Document doc = new Document(dataDir + "input.pdf");
// Instancier ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Conclusion
Vous avez extrait avec succès des paragraphes d'un document PDF à l'aide d'Aspose.PDF pour .NET. Les paragraphes extraits ont été affichés dans la fenêtre de la console.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel a pour objectif de vous guider dans le processus d'extraction de paragraphes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# qui l'accompagne fournit des étapes pratiques pour réaliser cette tâche.

#### Q : Quels espaces de noms dois-je importer ?

R : Dans le fichier de code dans lequel vous souhaitez extraire les paragraphes, incluez les directives using suivantes au début du fichier :

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` dans le code et remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment ouvrir un document PDF existant ?

 A : À l'étape 4, vous ouvrirez un document PDF existant à l'aide de l'`Document` constructeur et fournissant le chemin vers le fichier PDF d'entrée.

#### Q : Comment extraire des paragraphes du document ?

 A : L’étape 5 consiste à créer une instance de`ParagraphAbsorber` classe et son utilisation`Visit` méthode pour extraire des paragraphes du document PDF.

#### Q : Comment parcourir les paragraphes extraits ?

A : L'étape 6 vous guide dans la lecture en boucle des paragraphes extraits. Les boucles imbriquées permettent de parcourir les sections et les lignes de chaque paragraphe, pour finalement accéder au contenu du texte et l'afficher.

#### Q : Quel est le point clé à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à extraire des paragraphes d'un document PDF à l'aide d'Aspose.PDF pour .NET. Les paragraphes extraits ont été affichés dans la fenêtre de la console, vous offrant ainsi un aperçu précieux de la structure du contenu du document.