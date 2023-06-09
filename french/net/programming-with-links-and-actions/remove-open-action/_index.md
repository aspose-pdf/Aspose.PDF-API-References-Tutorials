---
title: Supprimer l'action ouverte
linktitle: Supprimer l'action ouverte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer l'action d'ouverture d'un PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-links-and-actions/remove-open-action/
---

Apprenez à supprimer l'action d'ouverture d'un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Étape 3 : suppression de l'action d'ouverture

 Supprimez l'action d'ouverture du document en définissant le`OpenAction` propriété à null :

```csharp
document. OpenAction = null;
```

## Étape 4 : Enregistrer le document mis à jour

 Enregistrez le document mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Étape 5 : Affichage du résultat

Affichez un message indiquant que l'action d'ouverture a été supprimée avec succès et spécifiez l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour Supprimer l'action ouverte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Supprimer l'action d'ouverture de document
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Enregistrer le document mis à jour
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitation ! Vous savez maintenant comment supprimer l'action d'ouverture d'un PDF en utilisant Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser les propriétés et le comportement des fichiers PDF dans vos projets.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.