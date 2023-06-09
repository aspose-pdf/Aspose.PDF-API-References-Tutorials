---
title: Reemplazar fuentes faltantes
linktitle: Reemplazar fuentes faltantes
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para reemplazar las fuentes que faltan en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 260
url: /es/net/document-conversion/replace-missing-fonts/
---

En este tutorial, lo guiaremos a través del proceso de reemplazo de fuentes que faltan en un archivo PDF usando Aspose.PDF para .NET. Cuando abre un archivo PDF en una máquina donde falta una fuente específica, puede haber problemas de visualización de fuentes. En tales casos, es posible sustituir la fuente que falta con otra fuente disponible en la máquina. Siguiendo los pasos a continuación, podrá reemplazar las fuentes que faltan en un archivo PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: encontrar la fuente que falta
El primer paso es encontrar la fuente que falta en el archivo PDF. Usa el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Encuentra la fuente original
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Falta la fuente en la máquina de destino
     // Agregar sustitución de fuente simple
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: Reemplace la fuente que falta
A continuación, reemplazaremos la fuente que falta con otra fuente disponible. Usa el siguiente código:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Convierta el archivo PDF a formato PDF/A con eliminación de errores
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Guarde el archivo PDF resultante
pdf.Save(fileNew.FullName);
```

 Asegúrese de reemplazar`"input.pdf"` con la ruta real a su archivo PDF original y`"newfile_out.pdf"` con el nombre deseado para el archivo PDF resultante.

## Paso 3: Guardar el archivo PDF resultante
Finalmente, guardaremos el archivo PDF resultante con la fuente reemplazada. Usa el siguiente código:

```csharp
// Guarde el archivo PDF resultante
pdf.Save(fileNew.FullName);
```

Asegúrese de haber establecido la ruta de destino correcta para el archivo PDF resultante.

### Ejemplo de código fuente para Reemplazar fuentes faltantes usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Falta la fuente en la máquina de destino
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso para reemplazar las fuentes que faltan en un archivo PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, podrá reemplazar con éxito las fuentes que faltan en su archivo PDF.