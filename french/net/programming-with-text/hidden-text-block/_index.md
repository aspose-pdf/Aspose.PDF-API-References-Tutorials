---
title: Bloc de texte masqué
linktitle: Bloc de texte masqué
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer des blocs de texte masqués dans un PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 230
url: /fr/net/programming-with-text/hidden-text-block/
---

Dans ce didacticiel, nous expliquerons comment créer un bloc de texte masqué à l'aide de la bibliothèque Aspose.PDF pour .NET. Un bloc de texte masqué est un texte flottant qui devient visible lorsque le curseur de la souris survole une zone spécifique. Nous allons suivre le processus étape par étape de création du bloc de texte masqué à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un exemple de document

Dans cette étape, nous créons un exemple de document PDF et y ajoutons un fragment de texte. Le fragment de texte servira de déclencheur pour afficher le bloc de texte masqué.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Étape 3 : Ouvrez le document

 Maintenant, nous ouvrons le document créé précédemment en utilisant le`Document` classe.

```csharp
Document document = new Document(outputFile);
```

## Étape 4 : Trouver le fragment de texte

 Nous utilisons un`TextFragmentAbsorber` objet pour trouver le fragment de texte qui déclenchera l'affichage du bloc de texte caché. Dans ce cas, nous recherchons le texte exact "Déplacez le curseur de la souris ici pour afficher le texte flottant".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Étape 5 : Créez le champ de texte masqué

 Nous créons un`TextBoxField` objet pour représenter le champ de texte masqué. Ce champ contiendra le texte qui devient visible lorsque le curseur de la souris survole le texte du déclencheur.

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

## Étape 6 : Ajouter le champ de texte masqué au document

Nous ajoutons le champ de texte masqué à la collection de formulaires du document.

```csharp
document.Form.Add(floatingField);
```

## Étape 7 : Créer le bouton invisible

Nous créons un champ de bouton invisible qui sera positionné au-dessus du fragment de texte du déclencheur. Ce champ de bouton aura des actions associées aux événements d'entrée et de sortie de la souris.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Étape 8 : Enregistrer le document

Enfin, nous enregistrons le document modifié avec le bloc de texte masqué.

```csharp
document. Save(outputFile);
```

### Exemple de code source pour le bloc de texte masqué à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Créer un exemple de document avec du texte
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Ouvrir un document avec du texte
Document document = new Document(outputFile);
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accepter l'absorbeur pour les pages du document
document.Pages.Accept(absorber);
// Obtenir le premier fragment de texte extrait
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Créer un champ de texte masqué pour le texte flottant dans le rectangle spécifié de la page
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Définir le texte à afficher comme valeur de champ
floatingField.Value = "This is the \"floating text field\".";
// Nous vous recommandons de créer un champ "en lecture seule" pour ce scénario
floatingField.ReadOnly = true;
// Définir le drapeau "caché" pour rendre le champ invisible à l'ouverture du document
floatingField.Flags |= AnnotationFlags.Hidden;
// Définir un nom de champ unique n'est pas nécessaire mais autorisé
floatingField.PartialName = "FloatingField_1";
// Le réglage des caractéristiques d'apparence du champ n'est pas nécessaire mais le rend meilleur
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
//(Vous pouvez également faire référence au champ flottant par le nom si vous l'avez spécifié ci-dessus.)
// Ajouter des actions sur l'entrée/la sortie de la souris dans le champ du bouton invisible
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Ajouter un champ de bouton au document
document.Form.Add(buttonField);
// Enregistrer le document
document.Save(outputFile);
```

## Conclusion

Dans ce didacticiel, vous avez appris à créer un bloc de texte masqué à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape, vous pouvez générer un document PDF avec un champ de texte masqué qui devient visible lorsque le curseur de la souris survole une zone spécifique. Vous pouvez personnaliser l'apparence et le comportement du bloc de texte masqué en fonction de vos besoins.