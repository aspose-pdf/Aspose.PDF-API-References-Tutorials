---
title: Supprimer les polices inutilisées dans le fichier PDF
linktitle: Supprimer les polices inutilisées dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment supprimer facilement les polices inutilisées des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Améliorez les performances et réduisez la taille du fichier.
type: docs
weight: 300
url: /fr/net/programming-with-text/remove-unused-fonts/
---
## Introduction

Bonjour ! Vous en avez assez des fichiers PDF encombrés et remplis de polices qui prennent inutilement de la place ? Vous n'êtes pas seul ! La gestion de l'utilisation des polices dans les PDF peut être un véritable casse-tête, surtout lorsque vous souhaitez que vos documents soient propres et efficaces. La bonne nouvelle est qu'avec Aspose.PDF pour .NET, vous pouvez facilement supprimer les polices inutilisées des fichiers PDF, ce qui améliore les performances et réduit la taille du fichier. Dans ce didacticiel, nous vous guiderons pas à pas dans le processus afin que vous puissiez rationaliser la gestion de vos fichiers PDF.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants pour tirer le meilleur parti de ce didacticiel :

1. Visual Studio installé : vous aurez besoin d'un environnement de développement pour exécuter votre code .NET. Visual Studio (toutes versions) est un excellent choix.
2.  Aspose.PDF pour .NET : assurez-vous que cette bibliothèque est installée. Vous pouvez la télécharger[ici](https://releases.aspose.com/pdf/net/).
3. Une compréhension de base de C# : Étant donné que nous utiliserons C# pour cet exemple, une connaissance du langage sera utile.
4. Un fichier PDF : préparez un exemple de fichier PDF. Vous pouvez créer le vôtre ou utiliser n'importe quel fichier PDF existant. Assurez-vous simplement qu'il porte un nom.`ReplaceTextPage.pdf` et stocké dans votre répertoire de documents.
5.  Licence valide : Bien que vous puissiez utiliser la version d'essai gratuite, une licence valide est recommandée pour bénéficier de toutes les fonctionnalités. Si vous avez besoin d'une licence temporaire, vous pouvez l'obtenir[ici](https://purchase.aspose.com/temporary-license/).

## Paquets d'importation

Maintenant que nous avons mis en place nos prérequis, importons les packages nécessaires dans notre projet C#. Voici ce dont vous aurez besoin :

Espace de noms Aspose.PDF : il fournit toutes les fonctionnalités de base pour gérer les fichiers PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Pour les importer, ajoutez les lignes ci-dessus en haut de votre fichier C#. Cela vous donnera accès aux classes et méthodes que nous utiliserons pour manipuler vos documents PDF.

## Étape 1 : Configurez votre environnement de projet

Tout d’abord, vous devez créer une nouvelle application console dans Visual Studio. Suivez ces étapes :

- Ouvrez Visual Studio.
- Cliquez sur Fichier > Nouveau > Projet.
-  Choisissez l'application console (.NET Framework) et donnez-lui un nom (par exemple,`PdfFontCleaner`).
- Cliquez sur Créer.

Vous avez maintenant un nouveau projet sur lequel travailler !

## Étape 2 : ajouter la bibliothèque Aspose.PDF

Ensuite, vous allez ajouter la bibliothèque Aspose.PDF à votre projet. Vous pouvez le faire via NuGet :

1. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur votre projet.
2. Sélectionnez Gérer les packages NuGet.
3.  Rechercher`Aspose.PDF` et installez-le.

## Étape 3 : Charger le document PDF

Chargeons le document que vous souhaitez traiter. Voici comment procéder :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY/"; // Mettez à jour ceci selon votre chemin
// Charger le fichier PDF source
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Remplacer`"YOUR DOCUMENT DIRECTORY/"` avec le chemin réel où votre fichier PDF est stocké. Cette étape est cruciale car elle permet à Aspose d'accéder à votre document PDF. 

## Étape 4 : Configurer l'absorbeur de fragments de texte

Ensuite, nous allons configurer un processeur qui nous aidera à identifier et à supprimer les polices inutilisées du PDF. Voici le code pour le faire :

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorber);
```

 Cette ligne de code crée un`TextFragmentAbsorber` objet configuré pour supprimer les polices inutilisées. En appelant`doc.Pages.Accept(absorber)`, nous demandons à Aspose de parcourir toutes les pages du document et d'identifier les fragments de texte.

## Étape 5 : parcourir les fragments de texte et remplacer les polices

Après avoir identifié les fragments de texte, il est temps de les parcourir et de remplacer les polices inutilisées. Ajoutez ce code :

```csharp
//Parcourir tous les fragments de texte
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

 Dans cette boucle, vous changerez la police de chaque`TextFragment` à « Arial, Bold ». Vous pouvez choisir la police qui correspond à vos besoins. C'est là que la vraie magie se produit, car elle garantit que le PDF est laissé avec une police propre et bien définie.

## Étape 6 : Enregistrer le document mis à jour

Maintenant que nous avons effectué les modifications nécessaires, enregistrons le PDF mis à jour ! Ajoutez le code suivant :

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
```

 Ici, nous créons un nouveau fichier nommé`RemoveUnusedFonts_out.pdf` dans le même répertoire. Cela vous donne une sauvegarde de votre PDF d'origine, tout en vous fournissant une version simplifiée.

## Étape 7 : gérer les exceptions

Enfin, il est toujours judicieux d'intégrer une gestion des erreurs. Voici un simple bloc try-catch pour encapsuler votre code :

```csharp
try
{
    // ... (code précédent)
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30-day temporary license from https://achat.aspose.com.");
}
```

Cela détectera toutes les exceptions qui se produisent pendant le processus et fournira des messages d'erreur conviviaux. Il est essentiel d'informer vos utilisateurs des exigences, comme la nécessité d'une licence Aspose valide.

## Conclusion

Félicitations ! Vous avez appris avec succès à supprimer les polices inutilisées d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez rendre vos fichiers PDF plus simples et plus nets, en vous assurant qu'ils sont plus efficaces et conviviaux. N'oubliez pas d'explorer d'autres fonctionnalités d'Aspose.PDF pour améliorer encore vos capacités de gestion de documents !

## FAQ

### Puis-je utiliser la version gratuite d'Aspose.PDF pour cette tâche ?
Oui, vous pouvez utiliser la version d'essai gratuite, mais une licence complète est recommandée pour des performances optimales.

### Qu'advient-il des polices s'il n'y a pas de remplacement disponible ?
Si aucune police de remplacement n'est trouvée, le texte risque de ne pas s'afficher correctement, assurez-vous donc de choisir une police couramment disponible.

### Comment obtenir un permis temporaire ?
 Vous pouvez demander une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).

### La suppression des polices inutilisées affectera-t-elle l’apparence du document ?
Cela pourrait se produire, en fonction des polices supprimées et de la manière dont les fragments de texte sont remplacés ; les tests sont encouragés.

### Existe-t-il une méthode alternative pour supprimer les polices inutilisées ?
Aspose.PDF pour .NET est très efficace à cette fin, bien que d'autres bibliothèques ou outils puissent offrir des fonctionnalités similaires.