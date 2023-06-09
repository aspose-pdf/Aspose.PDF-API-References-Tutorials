---
title: Définir le lien de destination
linktitle: Définir le lien de destination
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir un lien de destination dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-links-and-actions/set-destination-link/
---

Apprenez à définir un lien de destination dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

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

## Étape 3 : Modifier le lien de destination

Obtenez l'annotation du lien à modifier à l'aide du code suivant :

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Vous pouvez régler le`[1]` index pour sélectionner une page ou une annotation spécifique.

Ensuite, modifiez le lien en changeant l'action du lien et en définissant la cible en tant qu'adresse Web :

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Étape 4 : Enregistrez le document avec le lien mis à jour

Enregistrez le document avec le lien mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que le lien de destination a été configuré avec succès et indiquez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour définir le lien de destination à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Obtenir la première annotation de lien de la première page du document
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Lien de modification : modifier l'action du lien et définir la cible comme adresse Web
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Enregistrez le document avec le lien mis à jour
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous savez maintenant comment définir un lien de destination dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser les liens dans vos documents PDF et créer des expériences interactives pour les utilisateurs.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.