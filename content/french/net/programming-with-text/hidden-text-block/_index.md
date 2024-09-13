---
title: Bloc de texte caché dans le fichier PDF
linktitle: Bloc de texte caché dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer des blocs de texte masqués dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 230
url: /fr/net/programming-with-text/hidden-text-block/
---
Dans ce tutoriel, nous allons expliquer comment créer un bloc de texte masqué dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Un bloc de texte masqué est un texte flottant qui devient visible lorsque le curseur de la souris survole une zone spécifique. Nous allons suivre le processus étape par étape de création du bloc de texte masqué à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous de disposer des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers votre répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un exemple de document

Dans cette étape, nous créons un exemple de document PDF et y ajoutons un fragment de texte. Le fragment de texte servira de déclencheur pour l'affichage du bloc de texte masqué.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Étape 3 : Ouvrir le document

 Maintenant, nous ouvrons le document précédemment créé en utilisant le`Document` classe.

```csharp
Document document = new Document(outputFile);
```

## Étape 4 : Trouver le fragment de texte

 Nous utilisons un`TextFragmentAbsorber`objet pour trouver le fragment de texte qui déclenchera l'affichage du bloc de texte caché. Dans ce cas, nous recherchons le texte exact "Déplacez le curseur de la souris ici pour afficher le texte flottant".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Étape 5 : Créer le champ de texte masqué

 Nous créons un`TextBoxField` objet représentant le champ de texte masqué. Ce champ contiendra le texte qui devient visible lorsque le curseur de la souris survole le texte déclencheur.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Étape 6 : ajouter le champ de texte masqué au document

Nous ajoutons le champ de texte caché à la collection de formulaires du document.

```csharp
document.Form.Add(floatingField);
```

## Étape 7 : Créer le bouton invisible

Nous créons un champ de bouton invisible qui sera positionné au-dessus du fragment de texte déclencheur. Ce champ de bouton comportera des actions associées aux événements d'entrée et de sortie de la souris.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Étape 8 : Enregistrer le document

Enfin, nous sauvegardons le document modifié avec le bloc de texte masqué.

```csharp
document. Save(outputFile);
```

### Exemple de code source pour le bloc de texte masqué à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Créer un exemple de document avec du texte
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Ouvrir un document avec du texte
Document document = new Document(outputFile);
//Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accepter l'absorbeur pour les pages du document
document.Pages.Accept(absorber);
// Obtenir le premier fragment de texte extrait
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Créer un champ de texte masqué pour le texte flottant dans le rectangle spécifié de la page
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Définir le texte à afficher comme valeur de champ
floatingField.Value = "This is the \"floating text field\".";
// Nous recommandons de rendre le champ « en lecture seule » pour ce scénario
floatingField.ReadOnly = true;
// Définissez l'indicateur « masqué » pour rendre le champ invisible à l'ouverture du document
floatingField.Flags |= AnnotationFlags.Hidden;
// La définition d'un nom de champ unique n'est pas nécessaire mais autorisée
floatingField.PartialName = "FloatingField_1";
// La définition des caractéristiques de l'apparence du champ n'est pas nécessaire mais l'améliore
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Ajouter un champ de texte au document
document.Form.Add(floatingField);
// Créer un bouton invisible sur la position du fragment de texte
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Créer une nouvelle action de masquage pour le champ spécifié (annotation) et l'indicateur d'invisibilité.
// (Vous pouvez également faire référence au champ flottant par le nom si vous l'avez spécifié ci-dessus.)
// Ajouter des actions sur l'entrée/sortie de la souris dans le champ du bouton invisible
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Ajouter un champ de bouton au document
document.Form.Add(buttonField);
// Enregistrer le document
document.Save(outputFile);
```

## Conclusion

Dans ce didacticiel, vous avez appris à créer un bloc de texte masqué à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape, vous pouvez générer un document PDF avec un champ de texte masqué qui devient visible lorsque le curseur de la souris survole une zone spécifique. Vous pouvez personnaliser l'apparence et le comportement du bloc de texte masqué en fonction de vos besoins.

### FAQ

#### Q : Quel est le but du didacticiel « Bloc de texte masqué dans un fichier PDF » ?

R : Le didacticiel « Bloc de texte masqué dans un fichier PDF » explique comment créer un bloc de texte masqué dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Un bloc de texte masqué est un texte flottant qui devient visible lorsque le curseur de la souris survole une zone spécifique. Ce didacticiel fournit un guide étape par étape à l'aide du code source C#.

#### Q : Pourquoi voudrais-je créer un bloc de texte masqué dans un fichier PDF ?

R : La création d’un bloc de texte masqué peut être utile pour les documents PDF interactifs dans lesquels vous souhaitez fournir des informations ou un contexte supplémentaires qui ne deviennent visibles que lorsqu’un utilisateur passe le curseur de sa souris sur une zone désignée.

#### Q : Comment configurer le répertoire de documents ?

A : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers le répertoire où vous souhaitez enregistrer le fichier PDF généré.

#### Q : Comment créer un exemple de document et y ajouter un fragment de texte ?

 R : Dans le didacticiel, vous utilisez le`Document` classe pour créer un exemple de document PDF et ajouter un fragment de texte. Ce fragment de texte sert de déclencheur pour l'affichage du bloc de texte masqué.

#### Q : Comment trouver le fragment de texte qui déclenche le bloc de texte masqué ?

 A : Le didacticiel montre comment utiliser un`TextFragmentAbsorber` objet pour trouver le fragment de texte qui déclenche l'affichage du bloc de texte masqué. Il recherche une chaîne de texte spécifique dans le document PDF.

#### Q : Comment créer et personnaliser le champ de texte masqué ?

 A : Vous créez un`TextBoxField`objet pour représenter le champ de texte masqué. Le didacticiel fournit du code pour définir diverses propriétés telles que la position, la valeur, l'apparence et le comportement du champ de texte masqué.

#### Q : Comment créer un bouton invisible associé au bloc de texte masqué ?

 A : Un champ de bouton invisible est créé à l'aide de la`ButtonField` classe. Ce champ de bouton est positionné au-dessus du fragment de texte déclencheur et comporte des actions associées aux événements d'entrée et de sortie de la souris. Ces actions contrôlent la visibilité du bloc de texte masqué.

#### Q : Puis-je personnaliser l’apparence du bloc de texte masqué et de la zone de déclenchement ?

R : Oui, vous pouvez personnaliser diverses propriétés du champ de texte masqué et du bouton invisible, notamment la police, la couleur, la taille et le positionnement.

#### Q : Comment enregistrer le document modifié avec le bloc de texte masqué ?

 A : Le didacticiel montre comment enregistrer le document modifié à l'aide de l'`Save` méthode de la`Document` classe.