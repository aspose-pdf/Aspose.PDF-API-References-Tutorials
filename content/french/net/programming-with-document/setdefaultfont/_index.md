---
title: Définir la police par défaut dans le fichier PDF
linktitle: Définir la police par défaut dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir la police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 280
url: /fr/net/programming-with-document/setdefaultfont/
---
Si vous travaillez avec des documents PDF dans .NET, vous pouvez rencontrer des problèmes lorsque la police utilisée dans le PDF n'est pas disponible sur le système sur lequel il est affiché ou imprimé. Cela peut entraîner un affichage incorrect du texte ou son absence. Aspose.PDF pour .NET fournit une solution à ce problème en vous permettant de définir une police par défaut pour le document. Dans cet exemple, comment définir la police par défaut à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : définir le chemin d’accès au répertoire du document

nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous allons stocker ce chemin dans une variable appelée "dataDir".

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document PDF

 Nous allons commencer par charger un document PDF existant dont les polices sont manquantes. Dans cet exemple, nous supposerons que le document PDF se trouve dans le répertoire spécifié par le`dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // le code va ici
}
```

## Étape 3 : définir la police par défaut

 Ensuite, nous allons définir la police par défaut pour le document PDF à l'aide de la`PdfSaveOptions`classe. Dans cet exemple, nous allons définir la police par défaut sur « Arial ».

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Étape 4 : Enregistrez le document mis à jour

Enfin, nous allons enregistrer le document mis à jour dans un nouveau fichier. Dans cet exemple, nous allons enregistrer le document mis à jour dans un fichier nommé « output_out.pdf » dans le même répertoire que le fichier d'entrée.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Exemple de code source pour définir la police par défaut à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger un document PDF existant avec une police manquante
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Spécifier le nom de la police par défaut
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusion

La définition d'une police par défaut dans les documents PDF à l'aide d'Aspose.PDF pour .NET est un moyen simple et efficace de garantir que le texte s'affiche correctement, même si les polices d'origine ne sont pas disponibles. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement définir la police par défaut et créer des PDF qui offrent une expérience d'affichage cohérente et fiable dans différents environnements. Cette fonctionnalité est particulièrement utile dans les scénarios où les PDF seront visualisés ou imprimés sur différents systèmes sur lesquels différents jeux de polices peuvent être installés.

### FAQ sur la définition de la police par défaut dans un fichier PDF

#### Q : Pourquoi est-il important de définir une police par défaut dans les documents PDF ?

R : Il est important de définir une police par défaut dans les documents PDF, car cela garantit que le texte s'affichera correctement même si les polices d'origine ne sont pas disponibles sur le système sur lequel le PDF est visualisé ou imprimé. Cela permet d'éviter des problèmes tels que le texte manquant ou illisible, garantissant ainsi une expérience de visualisation cohérente et fiable.

#### Q : Puis-je choisir n’importe quelle police comme police par défaut en utilisant Aspose.PDF pour .NET ?

 R : Oui, vous pouvez choisir n'importe quelle police disponible sur le système comme police par défaut à l'aide d'Aspose.PDF pour .NET. Spécifiez simplement le nom de la police dans le champ`DefaultFontName` propriété de la`PdfSaveOptions` classe.

#### Q : Que se passe-t-il si la police par défaut spécifiée n’est pas disponible sur le système ?

R : Si la police par défaut spécifiée n'est pas disponible sur le système, le visualiseur PDF utilisera une police de secours pour afficher le texte. Il est conseillé de choisir une police couramment utilisée, comme Arial ou Times New Roman, pour garantir la compatibilité entre les différents systèmes.