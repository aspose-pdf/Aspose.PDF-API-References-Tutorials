---
title: Obtener recurso de anotación
linktitle: Obtener recurso de anotación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a recuperar el recurso de una anotación usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 90
url: /es/net/annotations/getresourceofannotation/
---

El ejemplo muestra cómo obtener recursos de anotación con Aspose.PDF para .NET. Para obtener el recurso de una anotación usando Aspose.PDF para .NET, siga estos pasos:

## Establezca la ruta del directorio donde se encuentra el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Abra el documento PDF que contiene la anotación cuyo recurso desea obtener.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Crea una anotación.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Agregue la anotación a una página del documento.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Guarde el documento.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Abra el documento modificado.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Obtener la acción de la anotación.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Obtener la interpretación de la acción.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Obtenga el clip multimedia.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Obtenga la especificación del archivo.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Leer los datos de los medios.

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

## Imprima el nombre de la copia y la operación de copia.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Siguiendo estos pasos, puede obtener fácilmente el recurso de una anotación en un documento PDF utilizando Aspose.PDF para .NET.

### Ejemplo de código fuente para Obtener recurso de anotación usando Aspose.PDF para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Abrir documento
	Document doc = new Document(dataDir + "AddAnnotation.pdf");
	//Crear anotación
	ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
	doc.Pages[1].Annotations.Add(sa);
	// Guardar documento
	doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
	// Abrir documento
	Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
	//Obtener acción de la anotación
	RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
	//Obtener la representación de la acción de representación
	Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
	// Clip multimedia
	MediaClip clip = (rendition as MediaRendition).MediaClip;
	FileSpecification data = (clip as MediaClipData).Data;
	MemoryStream ms = new MemoryStream();
	byte[] buffer = new byte[1024];
	int read = 0;
	//Se puede acceder a los datos de los medios en FileSpecification.Contents
	Stream source = data.Contents;
	while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
	{
	ms.Write(buffer, 0, read);
	}
	Console.WriteLine(rendition.Name);
	Console.WriteLine(action.RenditionOperation);

```