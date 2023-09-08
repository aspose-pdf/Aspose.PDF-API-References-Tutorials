---
title: Ajouter et rechercher du texte masqué dans un fichier PDF
linktitle: Ajouter et rechercher du texte masqué dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour ajouter et rechercher du texte masqué dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-text/add-and-search-hidden-text/
---
Dans ce didacticiel, nous vous expliquerons comment ajouter et rechercher du texte masqué dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Suivez ces étapes pour effectuer cette opération facilement.

## 1. Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement installé et configuré.
- Une connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez le télécharger sur le site officiel d'Aspose.

## 2. Création du document PDF avec du texte masqué

Pour commencer, utilisez le code suivant pour créer un nouveau document PDF contenant du texte masqué :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Créer un document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Définir la propriété du texte - invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Assurez-vous de fournir le chemin et le nom de fichier souhaités pour le document PDF.

## 3. Rechercher du texte dans le document

Ensuite, nous rechercherons le texte caché dans le document PDF. Utilisez le code suivant :

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Faites quelque chose avec les fragments
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Cela recherchera le texte masqué dans la deuxième page du document PDF et affichera les informations pertinentes.

### Exemple de code source pour l'ajout et la recherche de texte masqué à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Créer un document avec du texte masqué
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Définir la propriété du texte - invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Rechercher du texte dans le document
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Faire quelque chose avec des fragments
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusion

Félicitation ! Vous avez réussi à ajouter et à trouver du texte masqué dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer cette méthode à vos propres projets pour manipuler et rechercher du texte masqué dans les fichiers PDF.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque robuste qui permet aux développeurs de créer, manipuler et transformer des documents PDF au sein d'applications .NET.

#### Q : Le texte masqué peut-il être utilisé à des fins de filigrane ?

R : Absolument ! Le texte masqué peut constituer un moyen efficace de filigraner les documents PDF, ajoutant ainsi une couche de sécurité supplémentaire.

#### Q : Est-il possible de révéler le texte masqué dans un document PDF ?

: Oui, le processus de recherche et de révélation du texte masqué dans un document PDF peut être réalisé à l'aide des techniques décrites dans ce didacticiel.

#### Q : Quelles autres fonctionnalités Aspose.PDF pour .NET offre-t-il ?

R : Au-delà de la manipulation de texte caché, Aspose.PDF pour .NET offre un large éventail de fonctionnalités, notamment la génération, la conversion, le cryptage de PDF, etc.