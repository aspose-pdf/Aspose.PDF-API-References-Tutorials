---
title: Texte en PDF
linktitle: Texte en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Conversion simple et efficace de fichiers texte en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 300
url: /fr/net/document-conversion/text-to-pdf/
---
Ce didacticiel vous guidera à travers les étapes de conversion d'un fichier texte en fichier PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF offre une solution simple et efficace pour convertir du texte brut en PDF tout en préservant la mise en forme et la présentation du texte. Suivez les étapes ci-dessous pour effectuer cette conversion.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Lecture du fichier texte
 La première étape consiste à lire le contenu du fichier texte à l'aide de la`StreamReader` classe. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Lire le fichier texte
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"`avec le répertoire réel où se trouve votre fichier texte.

## Étape 2 : Création du document PDF
 La deuxième étape consiste à créer un`Document` objet qui représentera le document PDF final. Utilisez le code suivant :

```csharp
// Créer un objet Document
Document doc = new Document();
```

## Étape 3 : Ajouter du texte au document
La troisième étape consiste à ajouter le texte lu à la page du document PDF. Utilisez le code suivant :

```csharp
// Ajouter une nouvelle page au document
Page page = doc.Pages.Add();

// Créez un objet TextFragment et passez le texte lu comme argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Ajouter le paragraphe de texte à la page
page.Paragraphs.Add(text);
```

## Étape 4 : Enregistrer le fichier PDF
Enfin, enregistrez le fichier PDF résultant en spécifiant le chemin et le nom de fichier souhaités. Utilisez le code suivant :

```csharp
// Enregistrez le fichier PDF résultant
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Assurez-vous de spécifier le chemin et le nom de fichier souhaités pour le fichier PDF résultant.

### Exemple de code source pour Text to PDF en utilisant Aspose.PDF pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Lire le fichier texte source
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Instanciez un objet Document en appelant son constructeur vide
	Document doc = new Document();

	// Ajouter une nouvelle page dans la collection Pages de Document
	Page page = doc.Pages.Add();

	// Créez une instance de TextFragmet et passez le texte de l'objet lecteur à son constructeur en tant qu'argument
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Ajoutez un nouveau paragraphe de texte dans la collection de paragraphes et passez l'objet TextFragment
	page.Paragraphs.Add(text);

	// Enregistrer le fichier PDF résultant
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à convertir un fichier texte en fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes ci-dessus, vous pouvez facilement effectuer cette conversion. Utilisez cette méthode pour convertir vos fichiers texte en PDF et profitez de la flexibilité et de la qualité d'Aspose.PDF.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre diverses fonctionnalités, dont la conversion de texte brut en PDF.

#### Q : Pourquoi voudrais-je convertir un fichier texte en PDF ?

R : La conversion de fichiers texte au format PDF permet une meilleure gestion, partage et distribution des documents. Les fichiers PDF offrent un formatage cohérent sur différents appareils et systèmes d'exploitation.

#### Q : Comment puis-je charger un fichier texte et le convertir en PDF à l'aide d'Aspose.PDF pour .NET ?

 : Pour charger un fichier texte, vous pouvez utiliser le`StreamReader` classe pour lire le contenu du fichier. Ensuite, créez un`Document` objet pour représenter le document PDF. Ajouter une nouvelle page et un`TextFragment` contenant le texte du fichier texte. Enfin, enregistrez le PDF obtenu à l'aide de la`Save` méthode de la`Document` objet.

#### Q : Puis-je personnaliser l'apparence du texte dans le PDF ?

R : Oui, Aspose.PDF pour .NET fournit diverses options pour personnaliser l'apparence du texte dans le PDF résultant, telles que le style de police, la taille, la couleur et l'alignement.

#### Q : La mise en forme du texte est-elle conservée dans le PDF résultant ?

R : Oui, Aspose.PDF pour .NET préserve la mise en forme et la mise en page du texte lors de la conversion du texte en PDF, garantissant une représentation précise du contenu original.