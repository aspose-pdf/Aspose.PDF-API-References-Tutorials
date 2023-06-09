---
title: Définir le lien cible
linktitle: Définir le lien cible
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir un lien cible dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-links-and-actions/set-target-link/
---

Apprenez à définir un lien cible dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Étape 3 : Modifier le lien cible

Obtenez l'annotation du lien à modifier à l'aide du code suivant :

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Vous pouvez régler le`[1]` index pour sélectionner une page ou une annotation spécifique.

Ensuite, mettez à jour la destination sans mettre à jour le fichier :

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Et si vous souhaitez également mettre à jour le fichier :

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Étape 4 : Enregistrez le document avec le lien mis à jour

Enregistrez le document avec le lien mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que le lien cible a été configuré avec succès et indiquez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Exemple de code source pour définir le lien cible à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Destination de mise à jour de la ligne suivante, ne pas mettre à jour le fichier
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Fichier de mise à jour de la ligne suivante
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Enregistrez le document avec le lien mis à jour
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous savez maintenant comment définir un lien cible dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser les liens dans vos documents PDF et créer des expériences interactives pour les utilisateurs.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.