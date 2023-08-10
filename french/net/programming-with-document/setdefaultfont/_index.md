---
title: Définir la police par défaut dans le fichier PDF
linktitle: Définir la police par défaut dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir la police par défaut dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 280
url: /fr/net/programming-with-document/setdefaultfont/
---
Si vous travaillez avec des documents PDF dans .NET, vous pouvez rencontrer des problèmes où la police utilisée dans le PDF n'est pas disponible sur le système sur lequel il est affiché ou imprimé. Cela peut avoir pour conséquence que le texte s'affiche de manière incorrecte ou pas du tout. Aspose.PDF pour .NET fournit une solution à ce problème en vous permettant de définir une police par défaut pour le document. Dans cet exemple, comment définir la police par défaut à l'aide de Aspose.PDF pour .NET.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document PDF

 Nous commencerons par charger un document PDF existant qui a des polices manquantes. Dans cet exemple, nous supposerons que le document PDF se trouve dans le répertoire spécifié par le`dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // le code va ici
}
```

## Étape 3 : Définir la police par défaut

 Ensuite, nous définirons la police par défaut du document PDF à l'aide de la`PdfSaveOptions` classe. Dans cet exemple, nous allons définir la police par défaut sur "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Étape 4 : Enregistrer le document mis à jour

Enfin, nous enregistrerons le document mis à jour dans un nouveau fichier. Dans cet exemple, nous allons enregistrer le document mis à jour dans un fichier nommé "output_out.pdf" dans le même répertoire que le fichier d'entrée.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Exemple de code source pour définir la police par défaut à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
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

La définition d'une police par défaut dans les documents PDF à l'aide d'Aspose.PDF pour .NET est un moyen simple et efficace de garantir que le texte s'affiche correctement, même si les polices d'origine ne sont pas disponibles. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement définir la police par défaut et créer des PDF qui offrent une expérience de visualisation cohérente et fiable dans différents environnements. Cette fonctionnalité est particulièrement utile dans les scénarios où les fichiers PDF seront affichés ou imprimés sur divers systèmes pouvant avoir différents jeux de polices installés.

### FAQ pour définir la police par défaut dans le fichier PDF

#### Q : Pourquoi la définition d'une police par défaut est-elle importante dans les documents PDF ?

R : La définition d'une police par défaut dans les documents PDF est importante car elle garantit que le texte s'affichera correctement même si les polices d'origine ne sont pas disponibles sur le système sur lequel le PDF est affiché ou imprimé. Cela permet d'éviter des problèmes tels que du texte manquant ou brouillé, garantissant une expérience de visionnage cohérente et fiable.

#### Q : Puis-je choisir n'importe quelle police comme police par défaut en utilisant Aspose.PDF pour .NET ?

 R : Oui, vous pouvez choisir n'importe quelle police disponible sur le système comme police par défaut à l'aide d'Aspose.PDF pour .NET. Indiquez simplement le nom de la police dans le`DefaultFontName` propriété de la`PdfSaveOptions` classe.

#### Q : Que se passe-t-il si la police par défaut spécifiée n'est pas disponible sur le système ?

R : Si la police par défaut spécifiée n'est pas disponible sur le système, le visualiseur PDF utilisera une police de secours pour afficher le texte. Il est conseillé de choisir une police couramment disponible comme Arial ou Times New Roman pour assurer la compatibilité entre les différents systèmes.