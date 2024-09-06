---
title: Supprimer l'action ouverte
linktitle: Supprimer l'action ouverte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment supprimer l’action d’ouverture d’un PDF à l’aide d’Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-links-and-actions/remove-open-action/
---
Découvrez comment supprimer l’action d’ouverture d’un fichier PDF à l’aide d’Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configuration de l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Étape 3 : Suppression de l’action ouverte

 Supprimez l'action d'ouverture du document en définissant le`OpenAction` propriété à null :

```csharp
document. OpenAction = null;
```

## Étape 4 : Enregistrez le document mis à jour

 Enregistrez le document mis à jour à l'aide de la`Save` méthode:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Étape 5 : Affichage du résultat

Afficher un message indiquant que l'action d'ouverture a été supprimée avec succès et spécifier l'emplacement du fichier enregistré :

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour l'action Supprimer l'ouverture à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Supprimer l'action d'ouverture du document
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Enregistrer le document mis à jour
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitations ! Vous savez désormais comment supprimer l'action d'ouverture d'un PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser les propriétés et le comportement des fichiers PDF dans vos projets.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.

### FAQ 

#### Q : Qu'est-ce que « l'action d'ouverture » dans un fichier PDF ?

R : L'« action d'ouverture » dans un fichier PDF est une instruction qui spécifie ce qui doit se produire lorsque le PDF est ouvert. Il peut s'agir d'actions telles que la navigation vers une page ou un emplacement spécifique dans le document, le lancement d'une application externe ou l'affichage d'une vue spécifique.

#### Q : Pourquoi voudrais-je supprimer l’action d’ouverture d’un fichier PDF ?

R : La suppression de l’action d’ouverture peut améliorer la sécurité, l’expérience utilisateur et le contrôle de la présentation du PDF à l’ouverture. Par exemple, vous souhaiterez peut-être empêcher la navigation automatique ou désactiver certaines actions lors de l’ouverture du document.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à supprimer l’action d’ouverture ?

R : Aspose.PDF pour .NET fournit des API permettant de manipuler divers aspects des fichiers PDF. Ce didacticiel montre comment supprimer l'action d'ouverture à l'aide du code C#.

#### Q : Existe-t-il des risques potentiels ou des considérations à prendre en compte lors du retrait de l’action ouverte ?

R : La suppression de l'action d'ouverture peut modifier le comportement par défaut du PDF. Assurez-vous donc qu'il correspond à l'expérience utilisateur souhaitée. Testez soigneusement le PDF modifié pour confirmer que la suppression n'affecte pas les autres fonctionnalités.

#### Q : Puis-je personnaliser l’action d’ouverture pour effectuer d’autres actions ?

R : Oui, Aspose.PDF pour .NET vous permet de personnaliser l’action d’ouverture en la définissant sur différents types d’actions, telles que la navigation vers une page spécifique ou l’exécution de JavaScript.

#### Q : Puis-je supprimer les actions ouvertes des PDF protégés par mot de passe ?
R : Oui, vous pouvez supprimer les actions ouvertes des PDF protégés par mot de passe à condition de fournir les informations d’identification appropriées pour accéder au document et le modifier.

#### Q : La suppression de l'action ouverte est-elle réversible ?

: Non, une fois l’action d’ouverture supprimée et le PDF enregistré, l’action d’ouverture d’origine ne peut pas être restaurée à partir du PDF modifié.

#### Q : Comment puis-je vérifier que l’action ouverte a été supprimée avec succès ?

R : Après avoir supprimé l’action d’ouverture à l’aide du code fourni, ouvrez le PDF modifié et confirmez qu’aucune action spécifique ne se produit lors de l’ouverture.

#### Q : Puis-je supprimer les actions ouvertes de plusieurs fichiers PDF simultanément ?

R : Oui, vous pouvez utiliser la même approche pour supprimer les actions ouvertes de plusieurs fichiers PDF dans un scénario de traitement par lots.