---
title: Taquets de tabulation personnalisés dans le fichier PDF
linktitle: Taquets de tabulation personnalisés dans le fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment créer des taquets de tabulation personnalisés dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-text/custom-tab-stops/
---

Ce didacticiel vous guidera tout au long du processus de création de taquets de tabulation personnalisés dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez créer des taquets de tabulation personnalisés, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Créer une nouvelle instance de document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document _pdfdocument = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide du`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Étape 6 : Créer des taquets de tabulation personnalisés
 Créer un`TabStops` objet et ajoutez-y des taquets de tabulation personnalisés. Définissez le type d'alignement et le type de repère pour chaque taquet de tabulation.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Étape 7 : Créer des fragments de texte avec des taquets de tabulation
 Créer`TextFragment` objets et transmettez-leur les taquets de tabulation personnalisés. Utilisez les caractères spéciaux`#$TAB` pour indiquer les taquets de tabulation dans le texte.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Étape 8 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour les taquets de tabulation personnalisés utilisant Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez créé avec succès un document PDF avec des taquets de tabulation personnalisés à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l'objet de ce didacticiel ?

R : Ce didacticiel a pour objectif de vous guider tout au long du processus de création de taquets de tabulation personnalisés dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous souhaitez créer des taquets de tabulation personnalisés, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Dans le code, recherchez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer une nouvelle instance de document ?

 R : À l'étape 4, vous allez instancier un nouveau`Document` objet en utilisant le code fourni.

#### Q : Comment ajouter une page au document ?

 R : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection.

#### Q : Comment puis-je créer des taquets de tabulation personnalisés ?

 R : À l'étape 6, vous allez créer un`TabStops` objet et ajoutez-y des taquets de tabulation personnalisés. Vous définirez également l’alignement et les types de repères pour chaque taquet de tabulation.

#### Q : Comment créer des fragments de texte avec des taquets de tabulation ?

 R : À l'étape 7, vous allez créer`TextFragment` objets et transmettez-leur les taquets de tabulation personnalisés. Vous utiliserez les caractères spéciaux`#$TAB` pour indiquer les taquets de tabulation dans le texte.

#### Q : Comment puis-je enregistrer le document PDF ?

 R : À l'étape 8, vous enregistrerez le document PDF à l'aide du`Save` méthode du`Document` objet.

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris à créer un document PDF avec des taquets de tabulation personnalisés à l'aide d'Aspose.PDF pour .NET. Cela peut être utile pour organiser et aligner le texte de manière structurée.