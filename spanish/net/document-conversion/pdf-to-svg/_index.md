---
title: PDF a SVG
linktitle: PDF a SVG
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a SVG usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/document-conversion/pdf-to-svg/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un PDF a formato SVG usando Aspose.PDF para .NET. SVG (Gráficos vectoriales escalables) es un formato de imagen vectorial que ayuda a mantener la calidad y la escala de los gráficos. Siguiendo los pasos a continuación, podrá convertir un archivo PDF a formato SVG.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
En este paso, cargaremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: instanciación de las opciones de guardado de SVG
Después de cargar el archivo PDF, instanciaremos las opciones de guardado de SVG. Usa el siguiente código:

```csharp
// Crear una instancia de un objeto SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// No comprima la imagen SVG en un archivo Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Paso 3: Guardar el archivo SVG resultante
Ahora vamos a guardar el archivo PDF convertido en formato SVG. Usa el siguiente código:

```csharp
// Guarde la salida en archivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 El código anterior guarda el PDF convertido a formato SVG con el nombre de archivo`"PDFToSVG_out.svg"`.

### Código fuente de ejemplo para PDF a SVG usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document doc = new Document(dataDir + "input.pdf");
// Crear una instancia de un objeto de SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// No comprima la imagen SVG en un archivo Zip
saveOptions.CompressOutputToZipArchive = false;
// Guarde la salida en archivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato SVG usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF a formato SVG. Esta característica es útil cuando desea mantener la calidad de los gráficos y la escala al convertir a imágenes vectoriales.