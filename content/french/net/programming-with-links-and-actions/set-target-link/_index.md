---
title: Définir le lien cible dans le fichier PDF
linktitle: Définir le lien cible dans le fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment définir un lien cible dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-links-and-actions/set-target-link/
---
Découvrez comment définir un lien cible dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configuration de l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF en utilisant le code suivant :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Étape 3 : Modification du lien cible

Récupérez l'annotation du lien à modifier à l'aide du code suivant :

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Vous pouvez ajuster le`[1]` index pour sélectionner une page ou une annotation spécifique.

Ensuite, mettez à jour la destination sans mettre à jour le fichier :

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Et si vous souhaitez également mettre à jour le fichier :

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Étape 4 : Enregistrez le document avec le lien mis à jour

 Enregistrez le document avec le lien mis à jour en utilisant le`Save` méthode:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que le lien cible a été configuré avec succès et précisez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Exemple de code source pour définir le lien cible à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin d'accès au répertoire des documents.
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

### FAQ pour définir le lien cible dans un fichier PDF

#### Q : Qu'est-ce qu'un lien cible dans un fichier PDF ?

R : Un lien cible dans un fichier PDF est un lien cliquable qui dirige le lecteur vers une destination spécifique dans le même document ou vers un autre fichier PDF.

#### Q : Pourquoi voudrais-je définir un lien cible dans un fichier PDF ?

R : La définition de liens cibles vous permet de créer une expérience de navigation transparente dans un document PDF ou de créer des liens vers des sections ou des pages spécifiques dans d'autres fichiers PDF.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à définir les liens cibles ?

R : Aspose.PDF pour .NET fournit des API pour manipuler divers aspects des fichiers PDF, notamment la création et la modification de liens. Ce didacticiel montre comment définir un lien cible à l'aide du code C#.

#### Q : Puis-je définir des liens cibles pour accéder à des pages spécifiques du même document ?

R : Oui, Aspose.PDF pour .NET vous permet de définir des liens cibles pour accéder à des pages spécifiques du même document.

#### Q : Puis-je définir des liens cibles pour accéder à des pages spécifiques dans un autre fichier PDF ?

R : Oui, vous pouvez définir des liens cibles pour accéder à des pages spécifiques d'un autre fichier PDF à l'aide d'Aspose.PDF pour .NET.

#### Q : Existe-t-il des limites à la définition de liens cibles ?

R : Les liens cibles ne peuvent naviguer que dans le même document ou vers des pages spécifiques d'autres fichiers PDF. Ils ne peuvent pas créer de lien direct vers un contenu spécifique dans d’autres documents.

#### Q : Comment puis-je personnaliser l’apparence d’un lien cible ?

: L'apparence d'un lien cible, comme sa couleur et son style, peut être personnalisée à l'aide des propriétés fournies par Aspose.PDF pour .NET.

#### Q : Puis-je définir plusieurs liens cibles dans le même document PDF ?

R : Oui, vous pouvez définir plusieurs liens cibles dans le même document PDF. Répétez simplement le processus pour chaque lien que vous souhaitez créer.

#### Q : Puis-je définir un lien cible à l’aide d’une forme ou d’un texte spécifique ?

R : Oui, vous pouvez attacher un lien cible à des formes ou du texte spécifiques dans le document PDF à l'aide des propriétés et méthodes appropriées fournies par Aspose.PDF pour .NET.

#### Q : Comment puis-je tester si le lien cible fonctionne comme prévu ?

R : Après avoir défini le lien cible à l'aide du code fourni, ouvrez le PDF modifié et cliquez sur le lien pour vous assurer qu'il dirige vers la destination souhaitée.

#### Q : Puis-je définir des liens cibles dans des PDF protégés par mot de passe ?

R : Oui, vous pouvez définir des liens cibles dans des PDF protégés par mot de passe à condition de fournir les informations d'identification appropriées pour accéder au document et le modifier.