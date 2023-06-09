---
title: Mettre à jour la couleur du texte du lien
linktitle: Mettre à jour la couleur du texte du lien
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à mettre à jour la couleur du texte des liens dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 130
url: /fr/net/programming-with-links-and-actions/update-link-text-color/
---

Apprenez à mettre à jour la couleur du texte des liens dans un fichier PDF en utilisant Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Étape 3 : Naviguer dans les annotations de lien

Parcourez toutes les annotations de lien sur la deuxième page du document en utilisant le code suivant :

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // Rechercher le texte sous l'annotation
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // Changer la couleur du texte.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## Étape 4 : Enregistrer le document avec le texte du lien mis à jour

 Enregistrez le document avec le texte du lien mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que la couleur du texte d'annotation du lien a été mise à jour avec succès et spécifiez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour la mise à jour de la couleur du texte du lien à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// Rechercher le texte sous l'annotation
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// Changer la couleur du texte.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// Enregistrez le document avec le lien mis à jour
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous savez maintenant comment mettre à jour la couleur du texte des liens dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser l'apparence de vos liens dans les documents PDF.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.