---
title: Mettre à jour les liens
linktitle: Mettre à jour les liens
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à mettre à jour les liens dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-links-and-actions/update-links/
---

Apprenez à mettre à jour les liens dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

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

## Étape 3 : Modifier le lien

Obtenez l'annotation du lien à modifier à l'aide du code suivant :

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Vous pouvez régler le`[1]` index pour sélectionner une page ou une annotation spécifique.

Ensuite, modifiez le lien en changeant la destination :

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

Le premier paramètre représente le sujet du document, le second est le numéro de la page de destination. Le cinquième argument est le facteur de zoom lors de l'affichage de la page respective. Lorsqu'il est réglé sur 2, la page sera affichée avec un zoom de 200 %.

## Étape 4 : Enregistrez le document avec le lien mis à jour

Enregistrez le document avec le lien mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que les liens ont été mis à jour avec succès et précisez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour les liens de mise à jour à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Obtenir la première annotation de lien de la première page du document
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Lien de modification : changer la destination du lien
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Spécifiez la destination de l'objet lien
	// Le premier paramètre est l'objet du document, le second est le numéro de la page de destination.
	// L'argument 5ht est le facteur de zoom lors de l'affichage de la page respective. Lors de l'utilisation de 2, la page sera affichée en zoom 200%
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Enregistrez le document avec le lien mis à jour
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous savez maintenant comment mettre à jour les liens dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser les liens dans vos documents PDF et créer des expériences interactives pour les utilisateurs.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.