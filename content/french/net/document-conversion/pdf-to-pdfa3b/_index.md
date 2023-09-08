---
title: PDF en PDFA3b
linktitle: PDF en PDFA3b
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir un PDF en PDF/A-3b à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/document-conversion/pdf-to-pdfa3b/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier PDF au format PDF/A-3b à l'aide d'Aspose.PDF pour .NET. PDF/A-3b est une norme ISO pour l'intégration de fichiers et de données dans un document PDF. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers PDF au format PDF/A-3b.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Ouverture du document PDF source
Dans cette étape, nous ouvrirons le fichier PDF source à l'aide d'Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF source
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Convertir en PDF/A-3b
Après avoir ouvert le fichier PDF, nous pouvons procéder à la conversion au format PDF/A-3b. Utilisez le code suivant :

```csharp
// Convertir au format PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Le code ci-dessus convertit le fichier PDF au format PDF/A-3b et supprime toutes les erreurs de conversion.

## Étape 3 : Enregistrement du fichier PDF/A-3b résultant
Une fois la conversion terminée, nous devons enregistrer le fichier PDF/A-3b résultant. Voici la dernière étape :

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Enregistrez le document de sortie
pdfDocument.Save(dataDir);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier PDF/A-3b de sortie.

### Exemple de code source pour PDF vers PDFA3b à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier PDF au format PDF/A-3b à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant pouvoir convertir des fichiers PDF au format PDF/A-3b. Cette fonctionnalité est utile lorsque vous souhaitez intégrer des fichiers et des données supplémentaires dans un document PDF conforme à la norme PDF/A-3b.

### FAQ

#### Q : Qu'est-ce que PDF/A-3b et en quoi diffère-t-il des autres normes PDF/A ?

R : PDF/A-3b est une norme ISO qui permet d'intégrer des fichiers et des données dans un document PDF, le rendant ainsi autonome et garantissant une conservation à long terme. Contrairement à d'autres normes PDF/A, telles que PDF/A-1 et PDF/A-2, PDF/A-3b permet l'inclusion de fichiers et de données supplémentaires dans le document PDF. Cette fonctionnalité le rend adapté à l'archivage et à l'échange de documents complexes et interactifs.

#### Q : Puis-je inclure plusieurs fichiers et données dans un document PDF/A-3b ?

: Oui, l'un des principaux avantages de PDF/A-3b est sa capacité à inclure plusieurs fichiers et données dans le document PDF. Vous pouvez intégrer différents types de fichiers, tels que du XML, des feuilles de calcul, des images ou d'autres fichiers PDF, ainsi que le contenu PDF principal. En conséquence, le document PDF/A-3b devient un package autonome contenant tous les éléments nécessaires.

#### Q : Que se passe-t-il s'il y a des erreurs pendant le processus de conversion PDF en PDF/A-3b ?

 R : Lors de la conversion d'un PDF au format PDF/A-3b à l'aide d'Aspose.PDF pour .NET, vous contrôlez la façon dont les erreurs sont traitées. Le`Convert` la méthode`ConvertErrorAction` Le paramètre détermine l’action à entreprendre en cas d’erreurs. Dans l'exemple de code fourni, le`ConvertErrorAction.Delete` est utilisé, ce qui signifie que toute erreur rencontrée lors de la conversion entraînera la suppression des pages contenant des erreurs.

#### Q : Le format PDF/A-3b est-il adapté à la conservation de documents à long terme ?

: Oui, PDF/A-3b est spécialement conçu pour la conservation à long terme des documents électroniques. En intégrant des fichiers et des données supplémentaires, il garantit que tous les composants nécessaires sont inclus dans le document PDF lui-même, réduisant ainsi le risque de perte d'informations ou de dépendances externes au fil du temps. Cette fonctionnalité le rend adapté à l’archivage des documents de manière à garantir une accessibilité et une cohérence à long terme.