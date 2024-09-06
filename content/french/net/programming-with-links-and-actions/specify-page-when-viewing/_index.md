---
title: Spécifier la page lors de la visualisation
linktitle: Spécifier la page lors de la visualisation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment spécifier une page lors de l’affichage d’un PDF à l’aide d’Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Découvrez comment spécifier une page lors de l'affichage d'un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configuration de l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Étape 3 : Spécification de la page cible

Obtenez l’instance de la page cible à l’aide du code suivant :

```csharp
Page page2 = doc.Pages[2];
```

 Vous pouvez ajuster l'index`[2]` pour sélectionner la page souhaitée.

## Étape 4 : Configuration du paramètre de zoom

Créez une variable pour définir le facteur de zoom de la page cible :

```csharp
double zoom = 1;
```

Vous pouvez ajuster la valeur du zoom selon vos besoins.

## Étape 5 : Créer l’action de navigation

Créez une instance de l’action de navigation en utilisant la page cible spécifiée :

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Étape 6 : Définition de la destination

Définissez la destination pour accéder à la page cible à l'aide des coordonnées et du zoom :

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Étape 7 : Configuration de l’action d’ouverture du document

Définissez l'action d'ouverture du document avec l'action de navigation créée :

```csharp
doc. OpenAction = action;
```

## Étape 8 : Enregistrez le document mis à jour

 Enregistrez le document mis à jour à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Exemple de code source pour spécifier la page lors de l'affichage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obtenir l'instance de la deuxième page du document
Page page2 = doc.Pages[2];
// Créez la variable pour définir le facteur de zoom de la page cible
double zoom = 1;
// Créer une instance GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Aller à la page 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Définir l'action d'ouverture du document
doc.OpenAction = action;
// Enregistrer le document mis à jour
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusion

Félicitations ! Vous savez désormais comment spécifier une page lors de la visualisation d'un PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser l'expérience de visualisation de l'utilisateur dans vos documents PDF.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.

### FAQ 

#### Q : Quel est le but de spécifier une page cible lors de la visualisation d’un fichier PDF ?

R : La spécification d'une page cible vous permet de contrôler la page d'un document PDF qui s'affiche lorsque le fichier est ouvert. Cela peut améliorer l'expérience utilisateur en le dirigeant vers une page spécifique qui l'intéresse.

#### Q : Comment la spécification d’une page cible peut-elle être utile dans les documents PDF ?

R : La spécification d’une page cible est utile lorsque vous souhaitez guider les utilisateurs vers une section ou un contenu particulier dans un document PDF sans leur demander de parcourir manuellement les pages.

#### Q : Comment Aspose.PDF pour .NET facilite-t-il la spécification d’une page cible à afficher ?

R : Aspose.PDF pour .NET fournit des API qui vous permettent de définir la vue initiale d’un document PDF, y compris la page cible, le niveau de zoom et d’autres propriétés d’affichage.

#### Q : Puis-je spécifier n’importe quelle page comme page cible ?

R : Oui, vous pouvez spécifier n'importe quelle page du document PDF comme page cible à afficher. Utilisez simplement l'index approprié pour sélectionner la page souhaitée.

#### Q : Quelle est l’importance du facteur de zoom lors de la spécification d’une page cible ?

R : Le facteur de zoom détermine le niveau d'agrandissement appliqué à la page cible lorsque le document PDF est ouvert. Il contrôle la quantité de contenu affichée dans la fenêtre d'affichage.

#### Q : Puis-je définir différents facteurs de zoom pour différentes pages cibles ?

 : Oui, vous pouvez définir différents facteurs de zoom pour différentes pages cibles en créant des`GoToAction` instances et configurer leurs destinations en conséquence.

#### Q : Existe-t-il des limites à la spécification d’une page cible ?

R : La spécification d'une page cible se limite au contrôle de la vue initiale lors de l'ouverture du PDF. Elle n'affecte pas les interactions de l'utilisateur ni la navigation une fois le PDF affiché.

#### Q : Puis-je utiliser cette fonctionnalité pour créer des présentations dans un document PDF ?

R : Oui, vous pouvez utiliser cette fonctionnalité pour créer des expériences de type présentation dans un document PDF, en guidant les utilisateurs à travers différentes sections ou sujets.

#### Q : Puis-je personnaliser d’autres aspects de la vue initiale, comme la mise en page ?

R : Oui, Aspose.PDF pour .NET fournit des propriétés permettant de personnaliser d’autres aspects de la vue initiale, notamment la mise en page, le mode de page, etc.

#### Q : Comment puis-je tester si la page cible et le facteur de zoom spécifiés fonctionnent comme prévu ?

: Après avoir appliqué le code fourni pour spécifier la page cible et le facteur de zoom, ouvrez le fichier PDF modifié et vérifiez qu'il s'ouvre avec la page et le niveau de zoom corrects.