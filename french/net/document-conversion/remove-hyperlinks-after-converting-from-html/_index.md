---
title: Supprimer les liens hypertexte après la conversion à partir de HTML
linktitle: Supprimer les liens hypertexte après la conversion à partir de HTML
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour supprimer les hyperliens après la conversion de HTML en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 250
url: /fr/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---

Dans ce didacticiel, nous vous expliquerons le processus de suppression des liens hypertexte d'un fichier PDF généré à partir d'un fichier HTML à l'aide d'Aspose.PDF pour .NET. Les hyperliens sont des liens cliquables qui peuvent rediriger vers d'autres pages ou sites Web. En suivant les étapes ci-dessous, vous pourrez supprimer les hyperliens du fichier PDF résultant.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du fichier HTML et suppression des hyperliens
À cette étape, nous allons charger le fichier HTML et supprimer les hyperliens du document PDF résultant. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le fichier HTML à l'aide des options de chargement HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Parcourir les annotations de la première page du document
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Vérifier si l'annotation est un lien
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Vérifiez si l'action est de type GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Utilisez un absorbeur de fragments de texte pour trouver des fragments de texte correspondants
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Parcourez les fragments de texte correspondants et supprimez les attributs des hyperliens
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Supprimer l'annotation de la page
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier HTML.

## Étape 2 : Enregistrer le fichier PDF résultant
Enfin, nous enregistrerons le fichier PDF résultant sans les hyperliens. Utilisez le code suivant :

```csharp
// Enregistrez le fichier PDF résultant
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Le code ci-dessus enregistre le fichier PDF résultant avec le nom de fichier`"RemoveHyperlinksFromText_out.pdf"`.

### Exemple de code source pour Supprimer les liens hypertexte après la conversion de Html à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de suppression des liens hypertexte d'un fichier PDF généré à partir d'un fichier HTML à l'aide de Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous pourrez supprimer avec succès les hyperliens du fichier PDF résultant.