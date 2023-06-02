---
title: Ajouter une info-bulle au champ
linktitle: Ajouter une info-bulle au champ
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une info-bulle à un champ avec Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-forms/add-tooltip-to-field/
---

Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de manipuler des documents PDF par programmation. Dans ce didacticiel, nous allons parcourir le processus d'ajout d'une info-bulle à un champ à l'aide d'Aspose.PDF pour .NET. Nous vous fournirons un guide étape par étape pour vous aider à comprendre et à implémenter cette fonctionnalité dans votre code C#.

## Étape 1 : Configurer le projet et inclure Aspose.PDF pour .NET

Avant de commencer, assurez-vous que Aspose.PDF pour .NET est installé dans votre environnement de développement. Vous pouvez télécharger la bibliothèque depuis le site officiel et suivre les instructions d'installation fournies.

Une fois que vous avez installé Aspose.PDF pour .NET, créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré. Ajoutez une référence au fichier Aspose.PDF.dll dans votre projet pour accéder aux fonctionnalités de la bibliothèque.

## Étape 2 : Chargement du formulaire PDF source

Dans cette étape, nous allons charger le formulaire PDF source qui contient le champ auquel nous voulons ajouter une info-bulle. Tout d'abord, assurez-vous que le fichier de formulaire PDF source est disponible dans le répertoire de votre projet. Vous pouvez obtenir un exemple de formulaire PDF ou utiliser votre propre formulaire existant.

Pour charger le formulaire PDF, utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le formulaire PDF source
Document doc = new Document(dataDir + "AddTooltipToField.pdf");
```

 Assurez-vous de remplacer`"AddTooltipToField.pdf"` avec le nom de fichier réel de votre formulaire PDF source.

## Étape 3 : Ajouter une info-bulle à un champ de texte

Maintenant que nous avons chargé le formulaire PDF source, nous pouvons ajouter une info-bulle à un champ de texte spécifique. Dans cet exemple, supposons que le nom du champ de texte est "textbox1".

Pour ajouter une info-bulle au champ de texte, utilisez le code suivant :

```csharp
// Définir l'info-bulle pour le champ de texte
(doc.Form["textbox1"] as Field).AlternateName = "Text box tool tip";
```

 Remplacer`"textbox1"` par le nom réel du champ de texte auquel vous souhaitez ajouter l'info-bulle. Personnalisez également le texte de l'info-bulle en modifiant la valeur attribuée à`AlternateName`.

## Étape 4 : Enregistrer le document mis à jour

Après avoir ajouté l'info-bulle au champ, nous devons enregistrer le document mis à jour. Spécifiez le chemin du fichier de sortie où vous souhaitez enregistrer le formulaire PDF modifié.

Pour enregistrer le document mis à jour, utilisez le code suivant :

```csharp
dataDir = dataDir + "AddTooltipToField_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nTooltip added successfully.\nFile saved at " + dataDir);
```

Assurez-vous de fournir le nom et le chemin du fichier de sortie souhaité. Après avoir exécuté ce code, le formulaire PDF modifié avec l'info-bulle ajoutée sera enregistré à l'emplacement spécifié.

### Exemple de code source pour Ajouter une info-bulle au champ à l'aide de Aspose.Words pour .NET 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le formulaire PDF source
Document doc = new Document(dataDir + "AddTooltipToField.pdf");
// Définir l'info-bulle pour le champ de texte
(doc.Form["textbox1"] as Field).AlternateName = "Text box tool tip";
dataDir = dataDir + "AddTooltipToField_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nTooltip added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment ajouter une info-bulle à un champ en utilisant Aspose.PDF pour .NET. En suivant le guide étape par étape de ce didacticiel, vous pouvez améliorer vos formulaires PDF avec des info-bulles pour fournir des informations ou des conseils supplémentaires aux utilisateurs. N'oubliez pas d'explorer la documentation et les exemples fournis par Aspose.PDF pour .NET pour découvrir les fonctionnalités et fonctionnalités plus avancées offertes par la bibliothèque.