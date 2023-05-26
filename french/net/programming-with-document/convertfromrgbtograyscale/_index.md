---
title: Convertir de RVB en niveaux de gris
linktitle: Convertir de RVB en niveaux de gris
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à convertir des PDF de RVB en niveaux de gris à l'aide d'Aspose.PDF pour .NET. Améliorez la qualité d'impression et réduisez la taille du fichier.
type: docs
weight: 60
url: /fr/net/programming-with-document/convertfromrgbtograyscale/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un document PDF de l'espace colorimétrique RVB en niveaux de gris à l'aide de Aspose.PDF pour .NET. Cette conversion peut être utile à diverses fins, telles que la réduction de la taille du fichier ou la préparation de documents pour l'impression. Suivez le guide étape par étape ci-dessous :

## Étape 1 : Chargez le fichier PDF source

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Votre code ici...
}
```

## Étape 2 : Définir la stratégie de conversion

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Étape 3 : Convertir chaque page en niveaux de gris

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Étape 4 : Enregistrez le fichier résultant

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

Toutes nos félicitations! Vous avez converti avec succès le document PDF de RVB en niveaux de gris à l'aide de Aspose.PDF pour .NET.

### Exemple de code source pour Convertir de RVB en niveaux de gris à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le fichier PDF source
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Désormais, vous pouvez facilement convertir vos documents PDF de RVB en niveaux de gris à l'aide d'Aspose.PDF pour .NET.

