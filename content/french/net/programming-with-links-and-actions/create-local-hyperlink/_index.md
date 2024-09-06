---
title: Créer un lien hypertexte local dans un fichier PDF
linktitle: Créer un lien hypertexte local dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des hyperliens locaux dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-links-and-actions/create-local-hyperlink/
---
La création de liens hypertexte locaux dans un fichier PDF vous permet de créer des liens cliquables qui dirigent les utilisateurs vers d'autres pages du même document PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement créer de tels liens en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : définir le chemin d’accès au dossier des documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin réel vers votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Créer une instance de document

 Nous allons créer une instance de la`Document` classe pour représenter notre document PDF. Voici le code correspondant :

```csharp
Document doc = new Document();
```

## Étape 4 : ajouter une page et du texte avec des hyperliens

Dans cette étape, nous allons ajouter une page à notre document PDF et ajouter du texte contenant des hyperliens locaux. Nous allons définir les pages cibles pour chaque lien. Voici le code correspondant :

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Étape 5 : Enregistrez le document mis à jour

Enregistrons maintenant le fichier PDF mis à jour à l'aide de l'`Save` méthode de la`doc` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour créer un lien hypertexte local à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Créer une instance de fragment de texte
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Créer une instance de lien hypertexte local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Définir la page cible pour l'instance de lien
link.TargetPageNumber = 7;
// Définir un lien hypertexte TextFragment
text.Hyperlink = link;
// Ajouter du texte à la collection de paragraphes de la page
page.Paragraphs.Add(text);
// Créer une nouvelle instance de TextFragment
text = new TextFragment("link page number test to page 1");
// Le fragment de texte doit être ajouté sur la nouvelle page
text.IsInNewPage = true;
// Créer une autre instance d’hyperlien local
link = new LocalHyperlink();
// Définir la page cible pour le deuxième lien hypertexte
link.TargetPageNumber = 1;
// Définir le lien pour le deuxième TextFragment
text.Hyperlink = link;
// Ajouter du texte à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Félicitations ! Vous disposez désormais d'un guide étape par étape pour créer des hyperliens locaux dans un PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour créer des liens cliquables qui dirigent les utilisateurs vers d'autres pages du même document.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur les fonctionnalités avancées d'hyperlien.

### FAQ pour créer un lien hypertexte local dans un fichier PDF

#### Q : Que sont les hyperliens locaux dans un fichier PDF ?

R : Les hyperliens locaux dans un fichier PDF sont des liens cliquables qui dirigent les utilisateurs vers différentes pages du même document. Ces liens améliorent la navigation et permettent aux lecteurs d'accéder rapidement aux sections pertinentes.

#### Q : Comment les hyperliens locaux peuvent-ils être bénéfiques pour mon document PDF ?

R : Les hyperliens locaux constituent un moyen efficace de relier des contenus connexes au sein d'un même document PDF. Ils améliorent l'expérience utilisateur en permettant aux lecteurs d'accéder rapidement à des sections spécifiques sans avoir à faire défiler l'intégralité du document.

#### Q : Comment Aspose.PDF pour .NET prend-il en charge la création d’hyperliens locaux ?
R : Aspose.PDF pour .NET offre une prise en charge complète de la création d'hyperliens locaux. Le didacticiel étape par étape fourni dans ce guide montre comment ajouter des hyperliens locaux à votre document PDF à l'aide de C#.

#### Q : Puis-je personnaliser l’apparence des hyperliens locaux ?

R : Oui, vous pouvez personnaliser l'apparence des hyperliens locaux, y compris la couleur et le style du texte, pour vous assurer qu'ils correspondent à la conception de votre document et offrent une expérience visuelle cohérente.

#### Q : Est-il possible de créer plusieurs hyperliens locaux dans une seule page PDF ?

R : Absolument ! Vous pouvez créer plusieurs hyperliens locaux au sein d'une même page PDF, ce qui permet aux lecteurs d'accéder à différentes sections ou pages selon leurs besoins. Chaque hyperlien local peut être adapté à sa cible respective.

#### Q : Puis-je créer un lien vers des sections spécifiques d’une page à l’aide d’hyperliens locaux ?

R : Bien que les liens hypertexte locaux permettent généralement d'accéder à des pages entières, vous pouvez créer des ancres ou des signets dans votre document PDF pour obtenir des liens ciblés. Aspose.PDF pour .NET prend en charge diverses options de liens hypertexte.

#### Q : Comment puis-je vérifier que mes liens hypertexte locaux fonctionnent correctement ?

: En suivant le didacticiel et l'exemple de code fournis, vous pouvez créer en toute confiance des hyperliens locaux fonctionnels. Vous pouvez tester les liens en ouvrant le document PDF généré et en cliquant sur le texte hypertexte.

#### Q : Existe-t-il des limitations lors de l’utilisation d’hyperliens locaux ?

R : Les hyperliens locaux sont un moyen efficace d'améliorer la navigation dans les documents, mais il est important de veiller à ce que la structure du document reste claire et intuitive. Des hyperliens et des ancres correctement étiquetés contribuent à une expérience utilisateur positive.

#### Q : Puis-je créer des hyperliens locaux dans des tableaux ou des images ?

R : Oui, vous pouvez créer des hyperliens locaux dans divers éléments de votre document PDF, notamment des tableaux, des images et du texte. Aspose.PDF pour .NET offre la possibilité d'ajouter des hyperliens vers différents types de contenu.