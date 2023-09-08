---
title: Obtenir la ressource d'annotation
linktitle: Obtenir la ressource d'annotation
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment récupérer la ressource d'une annotation à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 90
url: /fr/net/annotations/getresourceofannotation/
---
L'exemple montre comment obtenir une ressource d'annotation avec Aspose.PDF pour .NET. Pour obtenir la ressource d'une annotation à l'aide d'Aspose.PDF pour .NET, procédez comme suit :

## Étape 1 : Définissez le chemin du répertoire où se trouve le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF contenant l'annotation dont vous souhaitez obtenir la ressource.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Étape 3 : Créez une annotation.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Étape 4 : Ajoutez l'annotation à une page du document.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Étape 5 : Enregistrez le document.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Étape 6 : Ouvrez le document modifié.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Étape 7 : Obtenez l’action de l’annotation.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Étape 7 : Obtenez le rendu de l’action.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Étape 8 : Obtenez le clip média.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Étape 9 : Obtenez la spécification du fichier.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Étape 10 : Lisez les données du média.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Étape 11 : Imprimez le nom du rendu et de l'opération de rendu.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

En suivant ces étapes, vous pouvez facilement obtenir la ressource d'une annotation dans un document PDF à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour obtenir une ressource d'annotation à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Créer une annotation
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Enregistrer le document
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Ouvrir le document
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Obtenir l'action de l'annotation
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Obtenir le rendu de l'action de rendu
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Clip média
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Les données des médias sont accessibles dans FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment obtenir la ressource d'une annotation particulière à partir d'un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement accéder et gérer les annotations, y compris les annotations de rendu, dans leurs documents PDF.

### FAQ

#### Q : Qu'est-ce qu'un rendu dans le contexte des annotations PDF ?

R : Dans le contexte des annotations PDF, un rendu est une présentation de contenu multimédia. Il permet d'intégrer du multimédia, tel que de l'audio ou de la vidéo, dans le document PDF. L'annotation de rendu spécifie le média à présenter et comment il doit être lu.

#### Q : Puis-je obtenir le nom du fichier multimédia associé à une annotation de rendu ?

 : Oui, vous pouvez obtenir le nom du fichier multimédia associé à une annotation de rendu à l'aide d'Aspose.PDF pour .NET. Le nom du fichier multimédia est accessible via le`FileSpecification` de la`MediaClip` objet.

#### Q : Aspose.PDF pour .NET peut-il extraire des fichiers multimédias à partir d'une annotation de rendu ?

R : Oui, Aspose.PDF pour .NET peut extraire les données multimédias d'une annotation de rendu, qui inclut du contenu audio ou vidéo, et les enregistrer dans un fichier distinct.

#### Q : Comment puis-je accéder aux données multimédias d'une annotation de rendu ?

 R : Les données multimédias d'une annotation de rendu sont accessibles via le`FileSpecification.Contents` propriété du`MediaClipData` objet.

#### Q : Puis-je modifier le média associé à une annotation de rendu à l'aide d'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET fournit des méthodes pour accéder et modifier les données multimédias associées à une annotation de rendu. Vous pouvez mettre à jour ou remplacer le fichier multimédia utilisé par une annotation de rendu.