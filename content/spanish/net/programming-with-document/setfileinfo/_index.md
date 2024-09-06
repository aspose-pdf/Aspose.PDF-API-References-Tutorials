---
title: Establecer información de archivo en un archivo PDF
linktitle: Establecer información de archivo en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para configurar la información del archivo en un archivo PDF con esta guía paso a paso.
type: docs
weight: 310
url: /es/net/programming-with-document/setfileinfo/
---
Si está trabajando en un proyecto que requiere la gestión de archivos PDF con Aspose.PDF para .NET, una de las funciones que puede utilizar es la capacidad de configurar la información de archivo para un documento PDF. La información del archivo incluye varios detalles, como el autor, la fecha de creación, las palabras clave, la fecha de modificación, el tema y el título. Esta guía le guiará a través del proceso de configuración de la información de archivo para un documento PDF utilizando el código fuente de C# con Aspose.PDF para .NET.

## Guía paso a paso para configurar la información de archivos mediante Aspose.PDF para .NET

1. Cree un nuevo proyecto de C# en su IDE de Visual Studio.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.
3. Cree un nuevo objeto de documento PDF proporcionando la ruta al archivo PDF cuya información desea modificar.

## Paso 1: Establezca la ruta al directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Paso 3: Utilice el objeto DocumentInfo para acceder a la información del archivo del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Paso 4: Establezca los valores de información de archivo deseados utilizando las propiedades del objeto DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Paso 5: Guarde el documento PDF actualizado en la ubicación especificada.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Paso 6: Verifique que la información del archivo se haya actualizado correctamente.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Ha configurado correctamente la información de archivo para un documento PDF utilizando Aspose.PDF para .NET.

### Código fuente de ejemplo para configurar información de archivo utilizando Aspose.PDF para .NET


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Especificar información del documento
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

En conclusión, Aspose.PDF para .NET ofrece una forma sencilla y eficaz de configurar la información de archivo para documentos PDF. Si sigue los pasos mencionados anteriormente, podrá configurar fácilmente los valores de información de archivo deseados para sus documentos PDF mediante el código fuente de C#.

### Preguntas frecuentes sobre la configuración de la información de archivos en archivos PDF

#### P: ¿Puedo configurar propiedades de información de archivo adicionales no mencionadas en el ejemplo?

 R: Sí, puede configurar propiedades de información de archivo adicionales utilizando el`DocumentInfo` objeto en Aspose.PDF para .NET. El`DocumentInfo`La clase proporciona varias propiedades que le permiten establecer información adicional, como el productor, la versión y propiedades personalizadas.

#### P: ¿Es posible recuperar la información del archivo de un documento PDF existente?

 R: Sí, puede recuperar la información del archivo de un documento PDF existente utilizando Aspose.PDF para .NET. Para ello, puede utilizar el`DocumentInfo` objeto para acceder a las propiedades de información del archivo y leer la información almacenada en el documento PDF.

#### P: ¿La configuración de la información del archivo modifica el documento PDF original?

R: No, al configurar la información del archivo mediante Aspose.PDF para .NET no se modifica el documento PDF original. En cambio, se crea un nuevo documento PDF con la información del archivo actualizada. El documento PDF original permanece sin cambios.