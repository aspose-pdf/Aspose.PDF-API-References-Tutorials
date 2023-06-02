---
title: Obtener dimensiones SVG
linktitle: Obtener dimensiones SVG
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para obtener dimensiones SVG usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/document-conversion/get-svg-dimensions/
---

## Introducción
En este tutorial, lo guiaremos a través del proceso de obtener las dimensiones de un archivo SVG usando Aspose.PDF para .NET. SVG (Gráficos vectoriales escalables) es un formato de imagen basado en XML que se utiliza para representar gráficos vectoriales. Siguiendo los pasos a continuación, podrá obtener las dimensiones de un archivo SVG y guardarlas como PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargando el archivo SVG
En este paso, cargaremos el archivo SVG usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo SVG.

## Paso 2: ajuste del tamaño de página
Ahora que hemos cargado el archivo SVG, podemos ajustar el tamaño de la página para acomodar el contenido SVG. Usa el siguiente código:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

El código anterior establece los márgenes de la página en cero, lo que permite que el tamaño de la página se ajuste según el contenido SVG.

## Paso 3: Guardar el PDF resultante
Después de ajustar el tamaño de la página, ahora podemos guardar el documento PDF resultante. Aquí está el último paso:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo PDF de salida.
  
### Ejemplo de código fuente para Obtener dimensiones SVG usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso para obtener las dimensiones de un archivo SVG usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder obtener las dimensiones de un archivo SVG y guardarlas en formato PDF. Esta característica puede ser útil cuando necesita medir las dimensiones de un gráfico vectorial.

