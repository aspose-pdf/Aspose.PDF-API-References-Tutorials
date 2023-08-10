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

### FAQ 

#### Q : Qu'est-ce que l'« action d'ouverture » dans un fichier PDF ?

R : L'« action d'ouverture » dans un fichier PDF est une instruction qui spécifie ce qui doit se passer lorsque le PDF est ouvert. Cela peut inclure des actions telles que la navigation vers une page ou un emplacement spécifique dans le document, le lancement d'une application externe ou l'affichage d'une vue spécifique.

#### Q : Pourquoi voudrais-je supprimer l'action d'ouverture d'un fichier PDF ?

R : La suppression de l'action d'ouverture peut améliorer la sécurité, l'expérience utilisateur et le contrôle de la présentation du PDF lors de son ouverture. Par exemple, vous pouvez empêcher la navigation automatique ou désactiver certaines actions à l'ouverture du document.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à supprimer l'action d'ouverture ?

: Aspose.PDF pour .NET fournit des API pour manipuler divers aspects des fichiers PDF. Ce didacticiel montre comment supprimer l'action d'ouverture à l'aide du code C#.

#### Q : Existe-t-il des risques ou des considérations potentiels lors de la suppression de l'action ouverte ?

R : La suppression de l'action d'ouverture peut modifier le comportement par défaut du PDF. Assurez-vous donc qu'il correspond à l'expérience utilisateur prévue. Testez soigneusement le PDF modifié pour confirmer que la suppression n'affecte pas les autres fonctionnalités.

#### Q : Puis-je personnaliser l'action d'ouverture pour effectuer d'autres actions ?

R : Oui, Aspose.PDF pour .NET vous permet de personnaliser l'action d'ouverture en la définissant sur différents types d'actions, telles que la navigation vers une page spécifique ou l'exécution de JavaScript.

#### Q : Puis-je supprimer les actions ouvertes des PDF protégés par mot de passe ?
R : Oui, vous pouvez supprimer les actions ouvertes des PDF protégés par mot de passe tant que vous fournissez les informations d'identification appropriées pour accéder et modifier le document.

#### Q : La suppression de l'action ouverte est-elle réversible ?

R : Non, une fois l'action d'ouverture supprimée et le PDF enregistré, l'action d'ouverture d'origine ne peut pas être restaurée à partir du PDF modifié.

#### Q : Comment puis-je vérifier que l'action d'ouverture a bien été supprimée ?

R : Après avoir supprimé l'action d'ouverture à l'aide du code fourni, ouvrez le PDF modifié et confirmez qu'aucune action spécifique ne se produit lors de l'ouverture.

#### Q : Puis-je supprimer des actions d'ouverture de plusieurs fichiers PDF simultanément ?

R : Oui, vous pouvez utiliser la même approche pour supprimer les actions ouvertes de plusieurs fichiers PDF dans un scénario de traitement par lots.