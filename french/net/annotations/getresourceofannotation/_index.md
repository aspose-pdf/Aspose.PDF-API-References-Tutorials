---
title: Obtenir la ressource d'annotation
linktitle: Obtenir la ressource d'annotation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à récupérer la ressource d'une annotation à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 90
url: /fr/net/annotations/getresourceofannotation/
---

L'exemple montre comment obtenir une ressource d'annotation avec Aspose.PDF pour .NET. Pour obtenir la ressource d'une annotation à l'aide d'Aspose.PDF pour .NET, suivez ces étapes :

## Définissez le chemin du répertoire où se trouve le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Ouvrez le document PDF contenant l'annotation dont vous souhaitez obtenir la ressource.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Créez une annotation.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Ajoutez l'annotation à une page du document.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Enregistrez le document.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Ouvrez le document modifié.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Obtenez l'action de l'annotation.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Obtenez le rendu de l'action.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Obtenez le clip média.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Obtenez la spécification du fichier.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Lire les données des médias.

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

## Imprimez le nom du rendu et l'opération de rendu.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

En suivant ces étapes, vous pouvez facilement obtenir la ressource d'une annotation dans un document PDF en utilisant Aspose.PDF pour .NET.

### Exemple de code source pour Get Resource Of Annotation en utilisant Aspose.PDF pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
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
	// Clip multimédia
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