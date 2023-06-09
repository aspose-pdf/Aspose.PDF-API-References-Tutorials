---
title: CGM en PDF
linktitle: CGM en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement des fichiers CGM en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/document-conversion/cgm-to-pdf/
---

Dans ce tutoriel, nous vous guiderons étape par étape pour convertir CGM en PDF en utilisant Aspose.PDF pour .NET. Nous expliquerons le code source C # fourni et fournirons des instructions étape par étape pour vous aider à suivre facilement.

## Introduction

La conversion d'un fichier CGM en PDF vous permet de partager et de visualiser vos dessins techniques de manière universelle. Avec Aspose.PDF pour .NET, vous pouvez facilement effectuer cette conversion et obtenir des fichiers PDF de haute qualité.

## Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour qu'il fonctionne avec Aspose.PDF pour .NET. Suivez les étapes ci-dessous :

1. Installez Visual Studio ou un autre IDE compatible avec le développement C#.
2. Créez un nouveau projet C#.
3. Installez le package Aspose.PDF pour .NET via NuGet pour ajouter les dépendances nécessaires.

## Convertir le fichier CGM en PDF

Pour convertir un fichier CGM en PDF, suivez ces étapes :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier un objet LoadOption à l'aide de CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instancier un objet Document
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Enregistrez le document PDF résultant
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 Dans le code ci-dessus, assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre fichier CGM à convertir. Ce code charge le fichier CGM en utilisant le`CgmLoadOptions` classe, puis crée un document PDF à l'aide de la`Document` objet. Enfin, le document PDF résultant est enregistré.

### Exemple de code source pour CGM en PDF en utilisant Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet LoadOption à l'aide de CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instancier l'objet Document
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Enregistrez le document PDF résultant
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Conclusion

Félicitation ! Vous savez maintenant comment convertir un fichier CGM en PDF en utilisant Aspose.PDF pour .NET. Nous avons parcouru toutes les étapes du processus, de l'initialisation des options de chargement CGM à l'enregistrement du document PDF résultant. Utilisez les exemples de code fournis pour intégrer cette fonctionnalité dans vos propres projets. Expérimentez avec Aspose.PDF pour .NET et découvrez les possibilités étendues qu'il offre pour manipuler les fichiers PDF.
