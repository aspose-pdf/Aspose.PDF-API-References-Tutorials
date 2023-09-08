---
title: Obtener recurso de anotación
linktitle: Obtener recurso de anotación
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo recuperar el recurso de una anotación usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 90
url: /es/net/annotations/getresourceofannotation/
---
El ejemplo muestra cómo obtener recursos de anotación con Aspose.PDF para .NET. Para obtener el recurso de una anotación usando Aspose.PDF para .NET, siga estos pasos:

## Paso 1: establezca la ruta del directorio donde se encuentra el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abra el documento PDF que contiene la anotación cuyo recurso desea obtener.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Paso 3: crea una anotación.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Paso 4: agregue la anotación a una página del documento.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Paso 5: guarde el documento.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Paso 6: abre el documento modificado.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Paso 7: obtenga la acción de la anotación.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Paso 7: obtenga la representación de la acción.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Paso 8: obtenga el clip multimedia.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Paso 9: obtenga la especificación del archivo.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Paso 10: Leer los datos de los medios.

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

## Paso 11: imprima el nombre de la representación y la operación de representación.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Siguiendo estos pasos, puede obtener fácilmente el recurso de una anotación en un documento PDF usando Aspose.PDF para .NET.

### Código fuente de ejemplo para Obtener recurso de anotación usando Aspose.PDF para .NET:

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
//Obtener acción de la anotación.
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

## Conclusión

En este tutorial, exploramos cómo obtener el recurso de una anotación particular de un documento PDF usando Aspose.PDF para .NET. Siguiendo la guía paso a paso y utilizando el código fuente C# proporcionado, los desarrolladores pueden acceder y administrar fácilmente las anotaciones, incluidas las anotaciones de representación, en sus documentos PDF.

### Preguntas frecuentes

#### P: ¿Qué es una interpretación en el contexto de las anotaciones de PDF?

R: En el contexto de las anotaciones en PDF, una interpretación es una presentación de contenido multimedia. Permite incrustar multimedia, como audio o vídeo, dentro del documento PDF. La anotación de interpretación especifica los medios que se presentarán y cómo se deben reproducir.

#### P: ¿Puedo obtener el nombre del archivo multimedia asociado con una anotación de representación?

R: Sí, puede obtener el nombre del archivo multimedia asociado con una anotación de representación utilizando Aspose.PDF para .NET. Se puede acceder al nombre del archivo multimedia a través del`FileSpecification` del`MediaClip` objeto.

#### P: ¿Puede Aspose.PDF para .NET extraer archivos multimedia de una anotación de representación?

R: Sí, Aspose.PDF para .NET puede extraer los datos multimedia de una anotación de representación, que incluye contenido de audio o video, y guardarlos como un archivo separado.

#### P: ¿Cómo puedo acceder a los datos multimedia de una anotación de interpretación?

 R: Se puede acceder a los datos multimedia de una anotación de interpretación a través del`FileSpecification.Contents` propiedad de la`MediaClipData` objeto.

#### P: ¿Puedo modificar los medios asociados con una anotación de representación usando Aspose.PDF para .NET?

R: Aspose.PDF para .NET proporciona métodos para acceder y modificar los datos multimedia asociados con una anotación de representación. Puede actualizar o reemplazar el archivo multimedia utilizado por una anotación de representación.