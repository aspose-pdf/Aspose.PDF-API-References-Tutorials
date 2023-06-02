---
title: Establecer información de archivo
linktitle: Establecer información de archivo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para configurar la información del archivo en sus documentos PDF con esta guía paso a paso.
type: docs
weight: 310
url: /es/net/programming-with-document/setfileinfo/
---
Si está trabajando en un proyecto que requiere la administración de archivos PDF con Aspose.PDF para .NET, una de las funciones que puede utilizar es la capacidad de configurar la información de archivo para un documento PDF. La información del archivo incluye varios detalles, como el autor, la fecha de creación, las palabras clave, la fecha de modificación, el tema y el título. Esta guía lo guiará a través del proceso de configuración de la información del archivo para un documento PDF utilizando el código fuente de C# con Aspose.PDF para .NET.

## Guía paso a paso para configurar la información del archivo usando Aspose.PDF para .NET

1. Cree un nuevo proyecto de C# en su IDE de Visual Studio.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.
3. Cree un nuevo objeto de documento PDF proporcionando la ruta al archivo PDF para el que desea modificar la información del archivo.

## Paso 1: establezca la ruta al directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Paso 3: use el objeto DocumentInfo para acceder a la información del archivo del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Paso 4: establezca los valores de información de archivo deseados utilizando las propiedades del objeto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Paso 5: guarde el documento PDF actualizado en la ubicación especificada.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Paso 6: Verifique que la información del archivo se haya actualizado correctamente.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Ha configurado con éxito la información del archivo para un documento PDF utilizando Aspose.PDF para .NET.

### Ejemplo de código fuente para Establecer información de archivo usando Aspose.PDF para .NET


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Especificar la información del documento
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Guardar documento de salida
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusión

En conclusión, Aspose.PDF para .NET proporciona una forma simple y efectiva de configurar la información de archivo para documentos PDF. Siguiendo los pasos mencionados anteriormente, puede configurar fácilmente los valores de información de archivo deseados para sus documentos PDF utilizando el código fuente de C#.