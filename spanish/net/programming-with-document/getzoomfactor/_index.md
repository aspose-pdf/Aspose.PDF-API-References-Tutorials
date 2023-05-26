---
title: Obtener factor de zoom
linktitle: Obtener factor de zoom
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener el factor de zoom de un archivo PDF con esta guía paso a paso.
type: docs
weight: 210
url: /es/net/programming-with-document/getzoomfactor/
---
Aspose.PDF para .NET es una biblioteca de manipulación de PDF que proporciona muchas funciones para realizar diversas operaciones en documentos PDF. Una de estas funciones es la capacidad de obtener el factor de zoom de un archivo PDF. En este tutorial, explicaremos cómo usar Aspose.PDF para .NET para obtener el factor de zoom de un archivo PDF usando el código fuente de C#.


## Paso 1: crear una instancia del nuevo objeto de documento

 El primer paso para obtener el factor de zoom de un archivo PDF utilizando Aspose.PDF para .NET es crear una instancia de un nuevo`Document` objeto. El`Document` El objeto representa un documento PDF que se puede cargar desde un archivo o una secuencia.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar un nuevo objeto de documento
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 En el código anterior, hemos creado un`Document` objeto pasando la ruta del archivo PDF al constructor del`Document` clase. Debe reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real del directorio donde se encuentra su archivo PDF.

## Paso 2: Crear objeto GoToAction

 El siguiente paso es crear un`GoToAction` objeto. A`GoToAction` objeto representa una acción que va a un destino específico en un documento PDF. En nuestro caso, queremos obtener el factor de zoom del archivo PDF, por lo que usaremos el`OpenAction` propiedad de la`Document` objeto para obtener el`GoToAction` objeto.

```csharp
// Crear objeto GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 En el código anterior, hemos creado un`GoToAction` objeto lanzando el`OpenAction` propiedad de la`Document` oponerse a`GoToAction`.

## Paso 3: obtenga el factor de zoom del archivo PDF

El tercer paso es obtener el factor de zoom del archivo PDF. Podemos obtener el factor de zoom del archivo PDF accediendo a la`Destination` propiedad de la`GoToAction` objeto y luego lanzarlo a`XYZExplicitDestination` . El`XYZExplicitDestination` class representa un destino en un documento PDF que especifica las coordenadas y el factor de zoom al que ir.

```csharp
// Obtenga el factor de zoom del archivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
```

 En el código anterior, hemos accedido al`Destination` propiedad de la`GoToAction` objeto y luego lanzarlo a`XYZExplicitDestination` . Después de eso, hemos accedido a la`Zoom` propiedad de la`XYZExplicitDestination` objeto para obtener el factor de zoom del archivo PDF.

## Paso 4: salida del factor de zoom

 El paso final es generar el factor de zoom del archivo PDF. Podemos usar el`System.Console.WriteLine`

```csharp
// Obtenga el factor de zoom del archivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
```        

### Código fuente de ejemplo para Obtener factor de zoom usando Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para Obtener factor de zoom usando Aspose.PDF para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instanciar un nuevo objeto de documento
	Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

	// Crear objeto GoToAction
	GoToAction action = doc.OpenAction as GoToAction;
	
	// Obtenga el factor de zoom del archivo PDF
	System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
	
```
