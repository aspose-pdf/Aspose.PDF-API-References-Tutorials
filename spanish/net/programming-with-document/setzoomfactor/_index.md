---
title: Establecer factor de zoom
linktitle: Establecer factor de zoom
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar el factor de zoom para archivos PDF usando Aspose.PDF para .NET con nuestra guía paso a paso.
type: docs
weight: 340
url: /es/net/programming-with-document/setzoomfactor/
---
Aspose.PDF para .NET es una potente API que permite a los desarrolladores trabajar con documentos PDF en sus aplicaciones .NET. Una de las características que proporciona es la capacidad de establecer el factor de zoom de un documento PDF. En esta guía paso a paso, explicaremos cómo usar Aspose.PDF para .NET para establecer el factor de zoom de un documento PDF usando el código fuente de C# provisto.

## Paso 1: establezca la ruta al directorio del documento

 El primer paso es establecer la ruta al directorio donde se encuentra el documento PDF. Esto se puede hacer configurando el`dataDir` variable a la ruta del directorio. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta del directorio real donde se encuentra su documento PDF.

## Paso 2: crear una instancia de un nuevo objeto de documento

Para trabajar con un documento PDF usando Aspose.PDF para .NET, necesitamos crear un nuevo`Document` objeto y cargue el archivo PDF en él. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Este código creará un nuevo`Document` objeto y cargue el archivo PDF llamado "SetZoomFactor.pdf" desde el`dataDir` directorio en él.

## Paso 3: establezca el factor de zoom

 Una vez el`Document` se crea el objeto, podemos establecer el factor de zoom del documento PDF. En el siguiente código, establecemos el factor de zoom en 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Este código establece el factor de zoom al 50% al crear un nuevo`GoToAction` objeto y pasando un`XYZExplicitDestination` objeto con un factor de zoom del 50% en él. El`OpenAction` propiedad de la`Document` el objeto se establece en este`GoToAction` objeto.

## Paso 4: Guarde el documento PDF

 Finalmente, podemos guardar el documento PDF modificado en un archivo nuevo. En el siguiente código, guardamos el documento PDF en un nuevo archivo llamado "Zoomed_pdf_out.pdf" en el`dataDir` directorio.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

## Conclusión

Aspose.PDF para .NET proporciona una manera simple y eficiente de establecer el factor de zoom de un documento PDF usando código C#. Siguiendo los pasos anteriores, puede modificar fácilmente el factor de zoom de cualquier documento PDF en su aplicación .NET.

### Ejemplo de código fuente para establecer el factor de zoom usando Aspose.PDF para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instanciar un nuevo objeto de documento
	Document doc = new Document(dataDir + "SetZoomFactor.pdf");

	GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
	doc.OpenAction = action;
	dataDir = dataDir + "Zoomed_pdf_out.pdf";
	// Guardar el documento
	doc.Save(dataDir);

```
