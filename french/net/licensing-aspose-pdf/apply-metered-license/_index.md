---
title: Configurer la licence limitée
linktitle: Configurer la licence limitée
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour configurer une licence limitée avec Aspose.PDF pour .NET et bénéficier de fonctionnalités avancées.
type: docs
weight: 10
url: /fr/net/licensing-aspose-pdf/configure-metered-license/
---

Dans ce didacticiel, nous vous expliquerons étape par étape comment configurer une licence limitée avec Aspose.PDF pour .NET. La licence mesurée vous permet d'utiliser les fonctionnalités avancées d'Aspose.PDF en fonction de votre consommation réelle.

### Étape 1 : Configuration des clés de licence

Dans le code source fourni, vous devez spécifier les clés publique et privée de la licence mesurée. Remplace le "*****" avec vos propres clés. Ces clés vous seront fournies lorsque vous achetez une licence limitée auprès d'Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Étape 2 : Chargement du document

 Chargez le document PDF à partir du disque à l'aide de la`Document`classe de Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Étape 3 : obtenir le nombre de pages du document

 Utilisez le`Count` propriété de la`Pages` collection pour obtenir le nombre total de pages du document.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Exemple de code source pour Configurer une licence mesurée à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// définir des clés publiques et privées mesurées
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Accédez à la propriété setMeteredKey et transmettez les clés publiques et privées en tant que paramètres
metered.SetMeteredKey("*****", "*****");
// Chargez le document à partir du disque.
Document doc = new Document(dataDir + "input.pdf");
//Obtenir le nombre de pages du document
Console.WriteLine(doc.Pages.Count);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment configurer une licence limitée avec Aspose.PDF pour .NET. En utilisant une licence limitée, vous pouvez bénéficier des fonctionnalités avancées d'Aspose.PDF en fonction de votre utilisation réelle. Assurez-vous de fournir des clés de licence valides pour utiliser Aspose.PDF avec toutes ses fonctionnalités.
