---
title: Dessiner XForm sur la page
linktitle: Dessiner XForm sur la page
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour dessiner un formulaire XForm sur une page PDF à l'aide d'Aspose.PDF pour .NET. Ajoutez et positionnez le formulaire sur la page.
type: docs
weight: 10
url: /fr/net/programming-with-operators/draw-xform-on-page/
---
Dans ce didacticiel, nous vous fournirons un guide étape par étape sur la façon de dessiner un XForm sur une page à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, manipuler et convertir des documents PDF par programme. À l'aide des opérateurs fournis par Aspose.PDF, vous pouvez ajouter et positionner un formulaire XForm sur une page PDF existante.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio installé avec le framework .NET.
2. La bibliothèque Aspose.PDF pour .NET.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Vous pouvez télécharger la bibliothèque depuis le site officiel d'Aspose et l'installer sur votre ordinateur.

## Étape 2 : Importez les espaces de noms nécessaires

Dans votre fichier de code C#, importez les espaces de noms requis pour accéder aux classes et méthodes fournies par Aspose.PDF :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Étape 3 : Définition des chemins de fichiers

Définissez les chemins d'accès aux fichiers pour l'image d'arrière-plan, le fichier PDF d'entrée et le fichier PDF de sortie :

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Assurez-vous de spécifier les chemins de fichiers réels sur votre ordinateur.

## Étape 4 : Chargement du fichier PDF d'entrée

Utilisez le code suivant pour charger le fichier PDF d'entrée :

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Le code suivant utilise les opérateurs GSave/GRestore
// Le code utilise l'opérateur ContatenateMatrix pour positionner le XForm
// Le code utilise l'opérateur Do pour dessiner le XForm sur la page
// Les opérateurs GSave/GRestore enveloppent le contenu existant
// ceci est fait pour obtenir l'état graphique initial à la fin du contenu existant
// sinon, des transformations indésirables pourraient se produire à la fin de la chaîne des opérateurs existants.
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Ajouter l'opérateur GSave pour réinitialiser correctement l'état graphique après de nouvelles commandes
pageContents. Add(new GSave());

// Créer le XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Définir la largeur et la hauteur de l'image
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Charger l'image dans un flux
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Ajouter l'image à la collection d'images de ressources XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Utilisation de l'opérateur Do : cet opérateur dessine l'image
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Positionnez le XForm aux coordonnées x=100 et y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Dessinez le XForm avec l'opérateur Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Positionnez le XForm aux coordonnées x=100 et y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Dessinez le XForm avec l'opérateur Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Restaurer l'état graphique avec GRestore après GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Assurez-vous de spécifier les chemins de fichiers réels et d'ajuster le numéro de page et les positions XForm si nécessaire.

### Exemple de code source pour Draw XForm On Page à l'aide d'Aspose.PDF pour .NET
 
```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// L'échantillon démontre
	// Utilisation des opérateurs GSave/GRestore
	// Utilisation de l'opérateur ContatenateMatrix pour positionner xForm
	// Utiliser l'opérateur pour dessiner xForm sur la page
	// Encapsuler le contenu existant avec la paire d'opérateurs GSave/GRestore
	// il s'agit d'obtenir l'état graphique initial au niveau du contenu existant
	// sinon il pourrait subsister des transformations indésirables à la fin de la chaîne des opérateurs existants
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Ajoutez un opérateur de sauvegarde de l'état graphique pour effacer correctement l'état graphique après de nouvelles commandes
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Créer un xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Définir la largeur et la hauteur de l'image
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Charger l'image dans le flux
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Ajouter une image à la collection Images des ressources XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Utilisation de l'opérateur Do : cet opérateur dessine une image
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Placer le formulaire aux coordonnées x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Dessiner un formulaire avec l'opérateur Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Placer le formulaire aux coordonnées x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Dessiner un formulaire avec l'opérateur Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Restaurer l'état graphique avec GRestore après le GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusion

Dans ce didacticiel, vous avez appris à dessiner un formulaire XForm sur une page PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites, vous pourrez ajouter et positionner un formulaire XForm sur une page existante, donnant ainsi plus de flexibilité à vos documents PDF.

### FAQ pour dessiner XForm sur la page

#### Q : Qu'est-ce qu'un XForm dans Aspose.PDF ?

R : Un XForm est un objet graphique réutilisable dans un document PDF. Il vous permet de définir et de dessiner des graphiques, des images ou du texte complexes pouvant être réutilisés plusieurs fois sur différentes pages.

#### Q : Comment importer les espaces de noms nécessaires pour Aspose.PDF ?

 R : Dans votre fichier de code C#, utilisez le`using` directive pour importer les espaces de noms requis pour accéder aux classes et méthodes fournies par Aspose.PDF :
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q : Quel est le but des opérateurs GSave et GRestore ?

 R : Le`GSave` et`GRestore`Les opérateurs dans Aspose.PDF sont utilisés pour enregistrer et restaurer l'état graphique. Ils permettent de garantir que les transformations et les paramètres appliqués à une section du contenu n'affectent pas les sections suivantes.

#### Q : Comment définir un XForm à l'aide d'Aspose.PDF ?

 R : Pour créer un XForm, utilisez le`XForm.CreateNewForm` méthode et ajoutez-le au`Resources.Forms` collection d’une page spécifique. Vous pouvez ensuite ajouter du contenu au XForm`Contents` propriété.

#### Q : Comment puis-je dessiner une image dans un XForm ?

 R : Chargez l'image dans un flux et ajoutez-la au`Resources.Images` collection du XForm. Utilisez le`Do` opérateur dans le XForm`Contents` pour dessiner l'image.

#### Q : Comment positionner un XForm sur une page PDF ?

 R : Pour positionner un XForm sur une page, utilisez le`ConcatenateMatrix` opérateur dans la page`Contents`. Ajustez les paramètres de la matrice pour spécifier la traduction (position) et la mise à l'échelle du XForm.

#### Q : Puis-je dessiner plusieurs XForms sur la même page ?

 R : Oui, vous pouvez dessiner plusieurs XForms sur la même page en ajustant la`ConcatenateMatrix`paramètres pour positionner chaque XForm à différentes coordonnées.

#### Q : Puis-je modifier le contenu d'un XForm après sa création ?

 R : Oui, vous pouvez modifier le contenu d'un XForm après sa création en ajoutant des opérateurs supplémentaires à son contenu.`Contents` propriété.

#### Q : Que se passe-t-il si j'omets les opérateurs GSave et GRestore ?

R : L'omission des opérateurs GSave et GRestore peut entraîner l'application de transformations ou de paramètres indésirables au contenu ultérieur. Leur utilisation permet de maintenir un état graphique propre.

#### Q : Puis-je réutiliser XForms sur différentes pages du document PDF ?

 R : Oui, vous pouvez réutiliser des XForms sur plusieurs pages en ajoutant le même XForm au`Resources.Forms` collection de différentes pages.

#### Q : Y a-t-il une limite au nombre de XForms que je peux créer ?

R : Bien qu'il n'y ait pas de limite stricte au nombre de XForms que vous pouvez créer, gardez à l'esprit qu'un trop grand nombre de XForms peut avoir un impact sur les performances et l'utilisation de la mémoire. Utilisez-les judicieusement.

#### Q : Puis-je faire pivoter un XForm ou appliquer d'autres transformations ?

 R : Oui, vous pouvez utiliser le`ConcatenateMatrix`opérateur pour appliquer des transformations telles que la rotation, la mise à l’échelle et la translation à un XForm.
