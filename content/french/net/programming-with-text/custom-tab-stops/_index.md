---
title: Tabulations personnalisées dans un fichier PDF
linktitle: Tabulations personnalisées dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment configurer des tabulations personnalisées dans un PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel présente des instructions étape par étape pour aligner le texte de manière professionnelle.
type: docs
weight: 120
url: /fr/net/programming-with-text/custom-tab-stops/
---
## Introduction

Avez-vous déjà dû formater du texte dans un PDF et souhaité pouvoir contrôler précisément la façon dont chaque mot s'aligne ? C'est là que les taquets de tabulation sont utiles ! Tout comme dans les documents Word, vous pouvez utiliser des taquets de tabulation personnalisés pour aligner parfaitement votre texte à des points spécifiques de votre PDF. Que vous souhaitiez aligner le contenu à droite, au centre ou à gauche, Aspose.PDF pour .NET vous facilite la tâche. Dans ce didacticiel, nous vous expliquerons comment configurer des taquets de tabulation personnalisés dans votre fichier PDF à l'aide d'Aspose.PDF pour .NET. À la fin, vous serez en mesure de créer facilement un document parfaitement aligné.

## Prérequis

Avant de commencer, voici ce que vous devrez suivre :

-  Aspose.PDF pour .NET : vous devez avoir installé la bibliothèque Aspose.PDF. Vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
- Environnement de développement .NET : assurez-vous que Visual Studio ou un autre IDE est configuré pour exécuter des applications .NET.
- Compréhension de base de C# : nous allons écrire du code en C#, une certaine familiarité avec ce système est donc recommandée.
-  Licence temporaire : vous pouvez utiliser le[permis temporaire](https://purchase.aspose.com/temporary-license/)pour déverrouiller toutes les fonctionnalités d'Aspose.PDF pour .NET.

Une fois que tout est prêt, passons à l'importation des packages nécessaires et à la configuration de l'environnement.

## Paquets d'importation

Pour commencer, vous devez importer les espaces de noms Aspose.PDF. Voici comment procéder :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

 Ces deux lignes sont essentielles.`Aspose.Pdf` l'espace de noms fournit la structure du document, tandis que`Aspose.Pdf.Text` nous donne accès à des fonctionnalités spécifiques au texte comme les tabulations personnalisées.

Décomposons le processus de configuration des taquets de tabulation personnalisés dans un PDF. Nous allons parcourir chaque étape en détail pour nous assurer que vous comprenez exactement ce qui se passe.

## Étape 1 : Créer un nouveau document PDF

La première chose à faire est de créer un nouveau document PDF. Considérez-le comme votre toile. Vous ajouterez des pages, puis placerez votre texte formaté dessus.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
```

Dans cet extrait :
-  Nous créons un nouveau`Document` objet.
-  Nous ajoutons une nouvelle page au document en utilisant`Pages.Add()`C'est ici que nous allons insérer le texte avec des tabulations.

## Étape 2 : Configurer les taquets de tabulation

Maintenant que nous avons un document vierge, il est temps de définir les taquets de tabulation. Les taquets de tabulation contrôlent la manière dont le texte s'aligne à différentes positions sur la page. Par exemple, vous souhaiterez peut-être aligner du texte à droite et d'autres textes au centre ou à gauche.

```csharp
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
```

Ici, nous :
-  Initialiser un`TabStops` objet, qui contiendra nos taquets de tabulation personnalisés.
-  Ajoutez un taquet de tabulation à la marque de 100 pixels à l'aide de`ts.Add(100)`. Ceci définit où l'onglet apparaîtra.
-  Définissez le type d'alignement sur`Right`, ce qui signifie que le texte qui atteint cette tabulation s'alignera à droite.
- Définissez un type de ligne de conduite. Les lignes de conduite sont des points ou des tirets qui remplissent l'espace avant la tabulation. Dans ce cas, nous utilisons une ligne continue.

## Étape 3 : ajouter d'autres taquets de tabulation

Nous pouvons ajouter autant de tabulations que nécessaire. Dans cet exemple, nous allons ajouter une tabulation centrée et une tabulation alignée à gauche.

```csharp
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

- Le deuxième taquet de tabulation est défini à 200 pixels avec un alignement central et un tiret de ligne de conduite.
- Le troisième taquet de tabulation est placé à 300 pixels, s'aligne à gauche et utilise une ligne de conduite en pointillés.

## Étape 4 : créer du texte avec des tabulations

Maintenant que les taquets de tabulation sont configurés, il est temps de créer du texte qui les utilise. Vous pouvez considérer ces taquets de tabulation comme des guides invisibles qui vous aident à aligner votre contenu sur différentes positions.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
```

- `TextFragment` représente un morceau de texte.
- Nous utilisons des marqueurs d'onglets (`#$TAB`) pour indiquer au PDF où appliquer les taquets de tabulation.
-  Par exemple, dans`text0`, `#$TABHead1` s'alignera en fonction du premier taquet de tabulation,`#$TABHead2` s'alignera sur le deuxième, et ainsi de suite.

## Étape 5 : ajouter des segments au texte

 Parfois, vous souhaiterez peut-être diviser votre texte en plusieurs segments, chacun avec son propre taquet de tabulation. C'est là que`TextSegment` est utile.

```csharp
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
```

Dans ce cas:
-  Nous commençons par`#$TABdata21`, qui s'aligne sur le premier taquet de tabulation.
-  Nous ajoutons plus de segments comme`data22` et`data23`, chacun s'alignant sur des tabulations différentes.

## Étape 6 : ajouter du texte à la page PDF

Maintenant que nous avons créé tous nos fragments de texte, il est temps de les ajouter à la page.

```csharp
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

 Ce code ajoute chaque`TextFragment`à la page PDF, en veillant à ce que le texte soit formaté conformément aux tabulations.

## Étape 7 : Enregistrer le document PDF

Enfin, nous devons enregistrer le document dans le répertoire spécifié.

```csharp
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

- Le fichier PDF est enregistré avec les tabulations personnalisées appliquées.
- Un message s'affiche pour confirmer la création réussie du fichier.

## Conclusion

Et voilà ! En suivant ce guide, vous avez appris à créer des taquets de tabulation personnalisés dans un document PDF à l'aide d'Aspose.PDF pour .NET. Les taquets de tabulation vous permettent d'aligner le texte de manière structurée et visuellement attrayante, ce qui rend vos PDF plus professionnels. Que vous aligniez les détails d'une facture, des tableaux ou toute autre forme de données, cette fonctionnalité vous donne un contrôle total sur le placement du texte.

## FAQ

### Puis-je appliquer des tabulations à des PDF existants ?  
Oui, vous pouvez modifier les PDF existants en ajoutant des tabulations personnalisées pour aligner le texte.

### Quels sont les types de leaders disponibles ?  
Vous pouvez choisir entre des caractères pleins, en tirets, en pointillés et d'autres types de lignes de repère pour remplir l'espace avant la tabulation.

### Puis-je ajouter plusieurs types d’alignement sur une seule ligne ?  
Absolument ! Comme le montre l'exemple, vous pouvez combiner les alignements à droite, à gauche et au centre sur la même ligne.

### Existe-t-il une limite au nombre de tabulations que je peux ajouter ?  
Non, vous pouvez ajouter autant de tabulations que nécessaire pour répondre à vos exigences de conception.

### Puis-je personnaliser la position des taquets de tabulation ?  
Oui, vous pouvez définir la position exacte en pixels de chaque taquet de tabulation en fonction de votre mise en page.