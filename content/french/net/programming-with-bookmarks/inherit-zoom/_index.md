---
title: Hériter du zoom dans un fichier PDF
linktitle: Hériter du zoom dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Héritez facilement du zoom des favoris dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-bookmarks/inherit-zoom/
---
L'héritage du zoom dans un fichier PDF vous permet de spécifier un niveau de zoom par défaut pour les signets. Avec Aspose.PDF pour .NET, vous pouvez facilement hériter du zoom en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez hériter du zoom. Remplacer`"YOUR DOCUMENT DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF sur lequel nous souhaitons hériter du zoom à l'aide du code suivant :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Obtenir la collection de signets

 Dans cette étape, nous obtiendrons la collection de signets ou de repères du document en utilisant le`Outlines` propriété du`doc` objet. Voici le code correspondant :

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Étape 5 : Définir le niveau de zoom

 Nous allons maintenant définir le niveau de zoom en créant un`XYZExplicitDestination` objet avec les coordonnées x, y et z spécifiées. Ici on utilise les coordonnées (100, 100, 0) avec un zoom de 2. Voici le code correspondant :

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Étape 6 : ajouter un niveau de zoom aux signets

 Dans cette étape, nous ajoutons le`XYZExplicitDestination` objet comme une action sur les signets du`item` collection. Voici le code correspondant :

```csharp
item. Action = new GoToAction(dest);
```

## Étape 7 : ajouter les signets mis à jour au document

 Enfin, nous ajoutons les signets mis à jour à la collection de signets du document en utilisant le`Add` méthode du`doc.Outlines` objet. Voici le code correspondant :

```csharp
doc. Outlines. Add(item);
```

## Étape 8 : Enregistrez le fichier mis à jour

 Enregistrons maintenant le fichier PDF mis à jour en utilisant le`Save` méthode du`doc` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour hériter du zoom à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");
// Obtenir une collection de plans/signets d'un fichier PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Définir le niveau de zoom sur 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Ajouter XYZExplicitDestination comme action pour décrire la collection de PDF
item.Action = new GoToAction(dest);
// Ajouter un élément à la collection de contours du fichier PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Enregistrer la sortie
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous disposez désormais d’un guide étape par étape pour hériter du zoom avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour spécifier un niveau de zoom par défaut pour les signets dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation de signets.

### FAQ pour hériter du zoom dans un fichier PDF

#### Q : Qu'est-ce que l'héritage du zoom dans un fichier PDF ?

R : L'héritage du zoom fait référence à la possibilité de spécifier un niveau de zoom par défaut pour les signets dans un document PDF. Cela permet une navigation cohérente et conviviale lorsque les utilisateurs interagissent avec les signets.

#### Q : Pourquoi voudrais-je hériter des niveaux de zoom pour les favoris ?

R : L'héritage des niveaux de zoom garantit aux utilisateurs une expérience de visualisation cohérente lorsqu'ils naviguent dans les signets d'un document PDF. Cela peut être particulièrement utile lorsque vous souhaitez fournir une vue spécifique pour différentes sections d'un document.

#### Q : Comment importer les bibliothèques nécessaires pour mon projet C# ?

R : Pour importer les bibliothèques requises pour votre projet C#, incluez les directives d'importation suivantes :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ces directives vous permettent d'accéder aux classes et méthodes nécessaires pour travailler avec des documents et des signets PDF.

#### Q : Comment puis-je spécifier le chemin d'accès au dossier de documents ?

 R : Dans le code source fourni, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le dossier contenant le fichier PDF pour lequel vous souhaitez hériter des niveaux de zoom.

#### Q : Comment puis-je ouvrir un document PDF pour hériter des niveaux de zoom ?

R : Pour ouvrir un document PDF afin d'hériter des niveaux de zoom, utilisez le code suivant :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Remplacer`"input.pdf"` avec le nom réel du fichier.

#### Q : Comment définir le niveau de zoom des favoris ?

 R : Pour définir le niveau de zoom, créez un`XYZExplicitDestination` objet avec les coordonnées et le facteur de zoom souhaités. Voici un exemple :

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Cela définit le niveau de zoom sur 2 aux coordonnées (100, 100).

#### Q : Comment ajouter le niveau de zoom aux favoris ?

 R : Ajoutez le`XYZExplicitDestination` objet en tant qu'action sur la collection de signets :

```csharp
item.Action = new GoToAction(dest);
```

 Où`item` est un`OutlineItemCollection` représentant un signet.

#### Q : Comment puis-je enregistrer le fichier PDF mis à jour ?

 R : Enregistrez le fichier PDF mis à jour à l'aide du`Save` méthode du`doc` objet:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Q : Puis-je personnaliser les niveaux de zoom pour différents signets ?

 R : Oui, vous pouvez personnaliser les niveaux de zoom pour différents signets en créant plusieurs`XYZExplicitDestination` objets avec des coordonnées et des facteurs de zoom différents.

#### Q : Y a-t-il une limite au nombre de favoris auxquels je peux appliquer l'héritage du zoom ?

R : Il n'y a généralement pas de limite stricte au nombre de signets auxquels vous pouvez appliquer l'héritage de zoom. Toutefois, les documents très volumineux comportant un nombre excessif de signets peuvent nécessiter une gestion efficace de la mémoire.

#### Q : Comment puis-je confirmer que l'héritage du zoom a été appliqué ?

R : Ouvrez le fichier PDF généré pour vérifier que les niveaux de zoom spécifiés ont été hérités par les signets.