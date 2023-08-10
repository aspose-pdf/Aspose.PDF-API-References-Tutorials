---
title: Définir le lien cible dans le fichier PDF
linktitle: Définir le lien cible dans le fichier PDF
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

### FAQ pour définir le lien cible dans le fichier PDF

#### Q : Qu'est-ce qu'un lien cible dans un fichier PDF ?

R : Un lien cible dans un fichier PDF est un lien cliquable qui dirige le lecteur vers une destination spécifique dans le même document ou vers un autre fichier PDF.

#### Q : Pourquoi voudrais-je définir un lien cible dans un fichier PDF ?

R : La définition de liens cibles vous permet de créer une expérience de navigation transparente dans un document PDF ou de créer des liens vers des sections ou des pages spécifiques dans d'autres fichiers PDF.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à définir des liens cibles ?

R : Aspose.PDF pour .NET fournit des API pour manipuler divers aspects des fichiers PDF, y compris la création et la modification de liens. Ce didacticiel montre comment définir un lien cible à l'aide de code C#.

#### Q : Puis-je définir des liens cibles pour naviguer vers des pages spécifiques dans le même document ?

R : Oui, Aspose.PDF pour .NET vous permet de définir des liens cibles pour naviguer vers des pages spécifiques dans le même document.

#### Q : Puis-je définir des liens cibles pour naviguer vers des pages spécifiques dans un autre fichier PDF ?

R : Oui, vous pouvez définir des liens cibles pour accéder à des pages spécifiques d'un autre fichier PDF à l'aide d'Aspose.PDF pour .NET.

#### Q : Existe-t-il des limites à la définition de liens cibles ?

R : Les liens cibles ne peuvent naviguer que dans le même document ou vers des pages spécifiques dans d'autres fichiers PDF. Ils ne peuvent pas établir de lien direct vers un contenu spécifique dans d'autres documents.

#### Q : Comment puis-je personnaliser l'apparence d'un lien cible ?

: L'apparence d'un lien cible, comme sa couleur et son style, peut être personnalisée à l'aide des propriétés fournies par Aspose.PDF pour .NET.

#### Q : Puis-je définir plusieurs liens cibles dans le même document PDF ?

R : Oui, vous pouvez définir plusieurs liens cibles dans le même document PDF. Répétez simplement le processus pour chaque lien que vous souhaitez créer.

#### Q : Puis-je définir un lien cible à l'aide d'une forme ou d'un texte spécifique ?

R : Oui, vous pouvez joindre un lien cible à des formes ou à du texte spécifiques dans le document PDF en utilisant les propriétés et méthodes appropriées fournies par Aspose.PDF pour .NET.

#### Q : Comment puis-je tester si le lien cible fonctionne comme prévu ?

R : Après avoir défini le lien cible à l'aide du code fourni, ouvrez le PDF modifié et cliquez sur le lien pour vous assurer qu'il navigue vers la destination souhaitée.

#### Q : Puis-je définir des liens cibles dans des PDF protégés par mot de passe ?

R : Oui, vous pouvez définir des liens cibles dans des fichiers PDF protégés par mot de passe tant que vous fournissez les informations d'identification appropriées pour accéder et modifier le document.