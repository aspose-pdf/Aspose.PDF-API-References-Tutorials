---
title: Définir la police par défaut dans le fichier PDF
linktitle: Définir la police par défaut dans le fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment définir la police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 280
url: /fr/net/programming-with-document/setdefaultfont/
---
Si vous travaillez avec des documents PDF dans .NET, vous pouvez rencontrer des problèmes où la police utilisée dans le PDF n'est pas disponible sur le système sur lequel il est affiché ou imprimé. Cela peut avoir pour conséquence que le texte s'affiche de manière incorrecte, voire pas du tout. Aspose.PDF pour .NET fournit une solution à ce problème en vous permettant de définir une police par défaut pour le document. Dans cet exemple, comment définir la police par défaut à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : Définir le chemin d'accès au répertoire de documents

nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document PDF

 Nous allons commencer par charger un document PDF existant comportant des polices manquantes. Dans cet exemple, nous supposerons que le document PDF se trouve dans le répertoire spécifié par le`dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // le code va ici
}
```

## Étape 3 : Définir la police par défaut

 Ensuite, nous définirons la police par défaut du document PDF à l'aide du`PdfSaveOptions` classe. Dans cet exemple, nous définirons la police par défaut sur « Arial ».

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Étape 4 : Enregistrez le document mis à jour

Enfin, nous enregistrerons le document mis à jour dans un nouveau fichier. Dans cet exemple, nous enregistrerons le document mis à jour dans un fichier nommé "output_out.pdf" dans le même répertoire que le fichier d'entrée.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Exemple de code source pour définir la police par défaut à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger un document PDF existant avec une police manquante
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Spécifier le nom de police par défaut
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusion

Définir une police par défaut dans les documents PDF à l'aide d'Aspose.PDF pour .NET est un moyen simple et efficace de garantir que le texte s'affiche correctement, même si les polices d'origine ne sont pas disponibles. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement définir la police par défaut et créer des PDF offrant une expérience de visualisation cohérente et fiable dans différents environnements. Cette fonctionnalité est particulièrement utile dans les scénarios dans lesquels les fichiers PDF seront visualisés ou imprimés sur divers systèmes sur lesquels différents jeux de polices peuvent être installés.

### FAQ pour définir la police par défaut dans un fichier PDF

#### Q : Pourquoi est-il important de définir une police par défaut dans les documents PDF ?

R : La définition d'une police par défaut dans les documents PDF est importante car elle garantit que le texte s'affichera correctement même si les polices d'origine ne sont pas disponibles sur le système sur lequel le PDF est affiché ou imprimé. Il permet d'éviter des problèmes tels que du texte manquant ou tronqué, garantissant ainsi une expérience visuelle cohérente et fiable.

#### Q : Puis-je choisir n’importe quelle police comme police par défaut à l’aide d’Aspose.PDF pour .NET ?

 R : Oui, vous pouvez choisir n'importe quelle police disponible sur le système comme police par défaut à l'aide d'Aspose.PDF pour .NET. Spécifiez simplement le nom de la police dans le champ`DefaultFontName` propriété du`PdfSaveOptions` classe.

#### Q : Que se passe-t-il si la police par défaut spécifiée n'est pas disponible sur le système ?

R : Si la police par défaut spécifiée n'est pas disponible sur le système, la visionneuse PDF utilisera une police de secours pour afficher le texte. Il est conseillé de choisir une police couramment disponible comme Arial ou Times New Roman pour garantir la compatibilité entre les différents systèmes.