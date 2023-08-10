---
title: Expandir marcadores en archivo PDF
linktitle: Expandir marcadores en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Expanda fácilmente los marcadores en un archivo PDF para mejorar la navegación con Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-bookmarks/expand-bookmarks/
---
Al expandir los marcadores en un archivo PDF, se mostrarán todos los marcadores abiertos de forma predeterminada. Con Aspose.PDF para .NET, puede ampliar fácilmente los marcadores siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF cuyos marcadores desea expandir. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF cuyos marcadores queremos expandir usando el siguiente código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: Establecer el modo de visualización de página

En este paso, configuraremos el modo de visualización de la página para que muestre los marcadores de forma predeterminada. usamos el`PageMode` propiedad de la`doc` objeto para establecer el modo de página deseado. Aquí está el código correspondiente:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Paso 5: busque marcadores y amplíelos

 Ahora recorreremos cada elemento de marcador en la colección de marcadores del documento y estableceremos el estado abierto de cada elemento en`true` para expandirlos por defecto. Aquí está el código correspondiente:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Paso 6: Guarde el archivo actualizado

 Finalmente, guardamos el archivo PDF actualizado usando el`Save` metodo de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Expandir marcadores usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "input.pdf");
// Establecer el modo de vista de página, es decir, mostrar miniaturas, pantalla completa, mostrar panel de archivos adjuntos
doc.PageMode = PageMode.UseOutlines;
// Recorra cada elemento de Ouline en la colección de esquemas del archivo PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Establecer el estado abierto para el elemento del esquema
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Guardar salida
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para desarrollar marcadores con Aspose.PDF para .NET. Puede usar este código para mostrar todos los marcadores predeterminados en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.

### Preguntas frecuentes sobre la expansión de marcadores en un archivo PDF

#### P: ¿Qué son los marcadores en un archivo PDF?

R: Los marcadores en un archivo PDF son ayudas de navegación que permiten a los usuarios saltar rápidamente a secciones o páginas específicas dentro del documento. Proporcionan una manera conveniente de acceder a diferentes partes de un documento.

#### P: ¿Por qué querría expandir los marcadores en un archivo PDF?

R: La expansión de marcadores puede mejorar la experiencia del usuario al mostrar todos los marcadores en un estado expandido de forma predeterminada. Esto brinda a los usuarios una visión general clara de la estructura del documento y les permite navegar fácilmente a las diferentes secciones.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto de C#?

R: Para importar la biblioteca necesaria para su proyecto de C#, use la siguiente directiva de importación:

```csharp
using Aspose.Pdf;
```

Esta directiva le permite utilizar las clases y métodos proporcionados por Aspose.PDF para .NET.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: En el código fuente provisto, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta real a la carpeta que contiene el archivo PDF con el que desea trabajar. Esto garantiza que el código pueda localizar el archivo PDF de destino.

#### P: ¿Cómo abro un documento PDF para expandir sus marcadores?

R: Para abrir un documento PDF para expandir los marcadores, use el siguiente código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Reemplazar`"input.pdf"` con el nombre real del archivo.

#### P: ¿Cómo configuro el modo de visualización de la página para que muestre los marcadores de forma predeterminada?

R: Para configurar el modo de visualización de la página para que muestre los marcadores de forma predeterminada, use el`PageMode` propiedad de la`doc` objeto:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### P: ¿Cómo amplío todos los marcadores en el documento PDF?

 R: Para expandir todos los marcadores, recorra cada elemento de marcador en la colección de esquemas del documento y configure el`Open` propiedad a`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### P: ¿Qué sucede si un marcador tiene marcadores secundarios anidados?

R: Si un marcador tiene marcadores secundarios anidados, expandir el marcador principal también expandirá sus marcadores secundarios, brindando una vista completa de la estructura del documento.

#### P: ¿Cómo guardo el archivo PDF actualizado después de expandir los marcadores?

R: Para guardar el archivo PDF actualizado después de expandir los marcadores, use el siguiente código:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### P: ¿Puedo personalizar la apariencia de los marcadores expandidos?

R: Si bien este tutorial se enfoca en expandir los marcadores de forma predeterminada, puede personalizar la apariencia de los marcadores usando otras características y propiedades de Aspose.PDF.