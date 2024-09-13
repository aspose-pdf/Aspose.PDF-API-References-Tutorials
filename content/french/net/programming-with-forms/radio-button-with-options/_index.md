---
title: Bouton radio avec options
linktitle: Bouton radio avec options
second_title: Référence de l'API Aspose.PDF pour .NET
description: Libérez le potentiel des PDF interactifs en ajoutant des boutons radio à l'aide d'Aspose.PDF pour .NET. Créez facilement des formulaires attrayants et améliorez l'expérience utilisateur.
type: docs
weight: 230
url: /fr/net/programming-with-forms/radio-button-with-options/
---
## Introduction

La création de documents PDF interactifs peut améliorer considérablement l'engagement des utilisateurs et rationaliser la collecte de données. Parmi les différents éléments que vous pouvez intégrer, les boutons radio se distinguent comme une méthode conviviale de présentation d'options à choix multiples. Grâce à Aspose.PDF pour .NET, vous pouvez facilement ajouter des boutons radio dans vos formulaires PDF, ce qui permet aux utilisateurs de sélectionner facilement leurs préférences. Que vous travailliez sur des enquêtes, des formulaires de commentaires ou des applications, ce guide vous aidera à exploiter la puissance d'Aspose.PDF pour implémenter efficacement des boutons radio.

## Prérequis

Avant de commencer, vous devez configurer quelques éléments pour garantir un parcours fluide lors de la création de notre PDF avec des boutons radio :

1.  Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF est installée dans votre projet. Si vous ne l'avez pas encore, vous pouvez facilement la télécharger à partir du[page de sortie](https://releases.aspose.com/pdf/net/).
2. .NET Framework : une compréhension de base du .NET Framework vous aidera à résoudre tous les problèmes que vous rencontrerez en cours de route.
3. Environnement de développement : vous aurez besoin d'un IDE adapté à .NET (comme Visual Studio) où vous pourrez écrire et tester votre code.
4. Familiarité avec C# : Bien que vous n’ayez pas besoin d’être un pro, avoir une compréhension de la programmation C# rendra certainement ce processus plus facile et plus agréable.
5. Connaissances de base de la structure PDF : comprendre la structure des PDF peut vous aider à résoudre des problèmes ou à personnaliser davantage vos formulaires.

Une fois que vous avez réglé tout cela, vous êtes prêt à libérer votre créativité dans le monde des PDF !

## Paquets d'importation

Pour commencer à utiliser les boutons radio dans Aspose.PDF, vous devez d'abord importer les packages essentiels dans votre projet C#. Voici comment procéder :

### Ouvrez votre éditeur de code

Ouvrez votre environnement de développement (comme Visual Studio) et créez un nouveau projet C# si vous ne l’avez pas déjà fait. 

### Ajoutez la référence Aspose.PDF

Cliquez avec le bouton droit de la souris sur votre projet dans l'Explorateur de solutions, sélectionnez Ajouter > Référence, puis dans la section Assemblages, recherchez Aspose.PDF. Si vous avez correctement installé la bibliothèque, elle devrait apparaître dans la liste. Cochez-la simplement et cliquez sur OK.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Votre projet est désormais prêt à exploiter la puissance d’Aspose !

Une fois tout configuré, créons un document PDF rempli de boutons radio étape par étape !

## Étape 1 : Configurer le document

Commençons par créer un nouveau document PDF et ajoutons-y une page. Ce sera la toile sur laquelle nous peindrons nos options de bouton radio.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

 Dans cet extrait, nous établissons un nouveau`Document` objet et ajout d'un`Page` pour notre contenu. Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin où vous souhaitez enregistrer votre PDF.

## Étape 2 : Créer un tableau pour la mise en page

Ensuite, nous avons besoin d'une disposition pour nos boutons radio. L'utilisation d'un tableau permet de les positionner plus facilement.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; // Définir les largeurs des colonnes
page.Paragraphs.Add(table);
```

 Ici, nous avons créé un`Table`objet et spécifié les largeurs de nos trois colonnes. Cela crée une mise en page ordonnée pour nos options.

## Étape 3 : ajouter des lignes au tableau

Nous allons maintenant ajouter une ligne à notre tableau et des cellules qui contiendront les boutons radio.

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

Nous créons une nouvelle ligne et trois cellules dans la ligne. Chaque cellule hébergera une option de bouton radio.

## Étape 4 : ajouter un champ de bouton radio

C'est ici que le plaisir commence : ajoutons le champ de bouton radio à notre PDF !

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

 Nous instancions un`RadioButtonField`, définissez son nom, puis ajoutez-le au formulaire du document. Ce champ permettra aux utilisateurs de faire leur sélection.

## Étape 5 : Configurer les options des boutons radio

Il est temps de créer les options pour les boutons radio ! Nous allons ajouter trois options parmi lesquelles les utilisateurs pourront choisir.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

 Ici, nous créons trois`RadioButtonOptionField` des instances pour chacun de nos choix et leur attribuer des noms. Faire preuve de créativité avec ces noms peut aider à mieux guider les utilisateurs sur ce qu'ils doivent choisir.

## Étape 6 : Définir les dimensions des options

Ensuite, définissons la taille des options des boutons radio pour les rendre visuellement attrayantes.

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

Avec ce code, nous définissons les dimensions de chaque bouton radio. Vous pouvez ajuster ces valeurs si vous souhaitez des options plus grandes ou plus petites.

## Étape 7 : ajouter des options au champ du bouton radio

Maintenant que les options sont créées, nous devons les ajouter au champ du bouton radio.

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

Ce code ajoute non seulement les options, mais les lie également à notre champ de bouton radio, donnant aux utilisateurs la possibilité de sélectionner l'une des options.

## Étape 8 : styliser les options

Pour que nos options se démarquent, nous allons les styliser. Nous pouvons ajouter des bordures et définir des couleurs.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

 Répétez ce style pour`opt2` et`opt3`, en ajustant les légendes en conséquence. Cela garantit que chaque option a un aspect professionnel et attrayant.

## Étape 9 : Ajouter des options aux cellules

Ensuite, nous devons placer ces boutons radio dans les cellules correspondantes de notre tableau.

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

Cette ligne ajoute les options de style aux cellules que nous avons créées précédemment, en les organisant soigneusement dans notre tableau.

## Étape 10 : Enregistrer le document PDF

Enfin, il est temps de sauvegarder votre travail ! Cette étape enregistre tout ce que nous avons fait dans un fichier PDF.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

Avec ce code, votre document sera enregistré dans le répertoire spécifié. Vous pouvez maintenant ouvrir ce fichier PDF pour voir vos boutons radio en action. Félicitations pour la mise en œuvre de votre premier PDF interactif !

## Conclusion

Maîtriser la création d'éléments interactifs tels que des boutons radio avec Aspose.PDF pour .NET ouvre un tout nouveau champ de possibilités pour vos documents PDF. En suivant ce guide, vous devriez maintenant être équipé pour intégrer sans effort des boutons radio dans vos projets, améliorant ainsi l'expérience utilisateur et les processus de collecte de données. Qu'il s'agisse d'une enquête simple ou d'un formulaire complexe, la possibilité de créer des PDF interactifs sur mesure est à portée de main.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer et de manipuler des documents PDF par programmation.

### Comment installer Aspose.PDF pour .NET ?
 Vous pouvez télécharger la bibliothèque à partir du[Page de sortie d'Aspose](https://releases.aspose.com/pdf/net/) et ajoutez-le à votre projet.

### Puis-je créer des boutons radio dans des fichiers PDF à l’aide d’autres langages de programmation ?
Oui, Aspose.PDF est également disponible pour Java et d'autres langages pour des fonctionnalités similaires.

### Existe-t-il un essai gratuit pour Aspose.PDF ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.PDF en téléchargeant un[version d'essai gratuite](https://releases.aspose.com/).

### Où puis-je obtenir de l'aide pour Aspose.PDF ?
 Pour obtenir de l'aide, vous pouvez visiter le[Forum d'assistance Aspose](https://forum.aspose.com/c/pdf/10) pour obtenir l’aide d’experts et de membres de la communauté.