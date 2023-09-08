---
title: MHT en PDF
linktitle: MHT en PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir MHT en PDF à l’aide d’Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/document-conversion/mht-to-pdf/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier MHT en PDF à l'aide d'Aspose.PDF pour .NET. MHT (MIME HTML) est un format utilisé pour enregistrer une page Web complète, y compris les images et le contenu associé. En suivant les étapes ci-dessous, vous pourrez convertir les fichiers MHT au format PDF.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Chargement du fichier MHT
Dans cette étape, nous allons charger le fichier MHT à l'aide d'Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Charger le document
Document document = new Document(dataDir + "test.mht", options);
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier MHT.

## Étape 2 : Conversion MHT en PDF
Après avoir chargé le fichier MHT, nous pouvons procéder à la conversion en PDF. Utilisez le code suivant :

```csharp
// Enregistrez la sortie sous forme de document PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Le code ci-dessus convertit le fichier MHT au format PDF et l'enregistre sous le nom de fichier.`"MHTToPDF_out.pdf"`.

### Exemple de code source pour MHT en PDF à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Charger le document
Document document = new Document(dataDir  + "test.mht", options);
// Enregistrez la sortie sous forme de document PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier MHT en PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant pouvoir convertir les fichiers MHT au format PDF. Cette fonctionnalité peut être utile lorsque vous devez convertir des pages Web entières en documents PDF.

### FAQ

#### Q : Aspose.PDF pour .NET prend-il en charge la conversion de fichiers MHT contenant des images intégrées au format PDF ?

: Oui, Aspose.PDF pour .NET prend en charge la conversion de fichiers MHT contenant des images intégrées au format PDF. La bibliothèque peut gérer le contenu complet de la page Web, y compris les images et les ressources associées, et le convertir en document PDF.

#### Q : Puis-je personnaliser la sortie PDF pendant le processus de conversion MHT en PDF ?

R : Oui, Aspose.PDF pour .NET propose diverses options pour personnaliser la sortie PDF pendant le processus de conversion MHT en PDF. Vous pouvez définir des propriétés telles que la taille de la page, l'orientation, les marges, etc. pour contrôler l'apparence du document PDF résultant.

#### Q : Aspose.PDF pour .NET conserve-t-il les hyperliens et le formatage du fichier MHT d'origine dans la sortie PDF ?

R : Oui, Aspose.PDF pour .NET conserve les hyperliens et le formatage du fichier MHT d'origine dans la sortie PDF. La bibliothèque garantit que le PDF converti conserve la même mise en page et le même contenu que le fichier MHT source.

#### Q : Puis-je convertir plusieurs fichiers MHT en documents PDF distincts à l'aide d'Aspose.PDF pour .NET ?

: Oui, vous pouvez convertir plusieurs fichiers MHT en documents PDF distincts à l'aide d'Aspose.PDF pour .NET. Chargez simplement chaque fichier MHT et enregistrez-le en tant que document PDF distinct avec un nom de fichier unique.