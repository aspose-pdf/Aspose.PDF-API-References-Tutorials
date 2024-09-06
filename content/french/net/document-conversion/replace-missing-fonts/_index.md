---
title: Remplacer les polices manquantes
linktitle: Remplacer les polices manquantes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment remplacer les polices manquantes dans les documents PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 260
url: /fr/net/document-conversion/replace-missing-fonts/
---
## Introduction

Avez-vous déjà ouvert un document PDF et constaté que certaines polices manquaient ? Cela peut être frustrant, n'est-ce pas ? Les polices manquantes peuvent donner lieu à un document qui n'a absolument pas l'air conforme à l'intention du créateur. Heureusement, avec Aspose.PDF pour .NET, vous pouvez facilement remplacer les polices manquantes et garantir que vos documents PDF conservent l'apparence souhaitée. Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus, de manière simple et directe.

## Prérequis

Avant de commencer, vous devez mettre en place quelques éléments :

1.  Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF est installée. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
2. Visual Studio : un environnement de développement dans lequel vous pouvez écrire et tester votre code.
3. Connaissances de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre les extraits de code.

## Paquets d'importation

Pour commencer, vous devrez importer les packages nécessaires dans votre projet C#. Voici comment procéder :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, vous devez spécifier le chemin d'accès à votre répertoire de documents. C'est là que se trouve votre fichier PDF d'entrée et où le fichier de sortie sera enregistré.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Initialiser la police d'origine

Ensuite, vous devrez essayer de trouver la police d'origine qui pourrait manquer. Dans ce cas, nous recherchons « AgencyFB ».

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    //La police est manquante sur la machine de destination
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Ici, nous essayons de trouver la police. Si elle n'est pas trouvée, nous interceptons l'exception et la remplaçons par une police plus courante, « Arial ». Cela garantit que votre document reste beau même si la police d'origine n'est pas disponible.

## Étape 3 : Charger le document PDF

Chargez maintenant le document PDF que vous souhaitez traiter. Vous devrez spécifier le chemin du fichier d'entrée.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 Dans cette étape, nous créons un nouveau`FileInfo` objet pour le fichier de sortie et charger le document PDF d'entrée dans un nouveau`Document` objet.

## Étape 4 : Convertir le document PDF

Avant d'enregistrer le document, il est conseillé de le convertir dans un format PDF spécifique. Dans ce cas, nous le convertirons au format PDF/A-1B, qui est une norme pour l'archivage à long terme des documents électroniques.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Cette ligne convertit le PDF et enregistre toutes les erreurs dans un fichier XML spécifié. Si des problèmes surviennent lors de la conversion, ils seront enregistrés dans « log.xml ».

## Étape 5 : Enregistrer le document PDF mis à jour

Enfin, il est temps d'enregistrer le document PDF mis à jour avec les polices remplacées.

```csharp
pdf.Save(fileNew.FullName);
```

Cette ligne enregistre le PDF modifié dans le chemin de fichier de sortie spécifié. Et voilà, vous avez réussi à remplacer les polices manquantes dans votre document PDF !

## Conclusion

Remplacer les polices manquantes dans les documents PDF n'est pas forcément une tâche ardue. Avec Aspose.PDF pour .NET, vous pouvez facilement gérer les substitutions de polices et garantir que vos documents s'affichent comme ils le devraient. En suivant les étapes décrites dans ce didacticiel, vous pouvez maintenir l'intégrité de vos fichiers PDF, même lorsque certaines polices ne sont pas disponibles. Ainsi, la prochaine fois que vous rencontrerez un problème de police manquante, vous saurez exactement quoi faire !

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents PDF par programmation.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui, Aspose propose une version d'essai gratuite que vous pouvez utiliser pour évaluer la bibliothèque. Vous pouvez la télécharger[ici](https://releases.aspose.com/).

### Que dois-je faire si la police dont j’ai besoin n’est pas disponible ?
Vous pouvez remplacer la police manquante par une police plus courante en utilisant la fonction de substitution de police dans Aspose.PDF.

### Est-il possible de convertir des PDF vers d’autres formats ?
Absolument ! Aspose.PDF prend en charge la conversion vers différents formats, notamment PDF/A, DOCX, etc.

### Où puis-je trouver de l'aide pour Aspose.PDF ?
 Vous pouvez trouver de l'aide et poser des questions sur le forum Aspose[ici](https://forum.aspose.com/c/pdf/10).