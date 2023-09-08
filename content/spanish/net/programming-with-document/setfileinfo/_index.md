---
title: Establecer información de archivo en archivo PDF
linktitle: Establecer información de archivo en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a usar Aspose.PDF para .NET para configurar información de archivo en un archivo PDF con esta guía paso a paso.
type: docs
weight: 310
url: /es/net/programming-with-document/setfileinfo/
---
Si está trabajando en un proyecto que requiere administrar archivos PDF usando Aspose.PDF para .NET, una de las características que quizás desee utilizar es la capacidad de configurar información de archivo para un documento PDF. La información del archivo incluye varios detalles como el autor, la fecha de creación, las palabras clave, la fecha de modificación, el tema y el título. Esta guía lo guiará a través del proceso de configuración de la información del archivo para un documento PDF usando el código fuente C# con Aspose.PDF para .NET.

## Guía paso a paso para configurar la información del archivo usando Aspose.PDF para .NET

1. Cree un nuevo proyecto de C# en su IDE de Visual Studio.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.
3. Cree un nuevo objeto de documento PDF proporcionando la ruta al archivo PDF cuya información desea modificar.

## Paso 1: establezca la ruta al directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento PDF

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Paso 3: utilice el objeto DocumentInfo para acceder a la información del archivo del documento PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Paso 4: establezca los valores de información del archivo deseados utilizando las propiedades del objeto DocumentInfo.

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

Ha configurado correctamente la información del archivo para un documento PDF utilizando Aspose.PDF para .NET.

### Código fuente de ejemplo para establecer información de archivo usando Aspose.PDF para .NET


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

En conclusión, Aspose.PDF para .NET proporciona una forma sencilla y eficaz de configurar la información de los archivos para documentos PDF. Siguiendo los pasos mencionados anteriormente, puede configurar fácilmente los valores de información de archivo deseados para sus documentos PDF utilizando el código fuente C#.

### Preguntas frecuentes para configurar información de archivo en un archivo PDF

#### P: ¿Puedo configurar propiedades de información de archivos adicionales que no se mencionan en el ejemplo?

 R: Sí, puede configurar propiedades de información de archivo adicionales usando el`DocumentInfo` objeto en Aspose.PDF para .NET. El`DocumentInfo`La clase proporciona varias propiedades que le permiten configurar información adicional, como el productor, la versión y las propiedades personalizadas.

#### P: ¿Es posible recuperar la información del archivo de un documento PDF existente?

 R: Sí, puede recuperar la información del archivo de un documento PDF existente usando Aspose.PDF para .NET. Para hacer esto, puedes usar el`DocumentInfo` objeto para acceder a las propiedades de información del archivo y leer la información almacenada en el documento PDF.

#### P: ¿La configuración de la información del archivo modifica el documento PDF original?

R: No, configurar la información del archivo usando Aspose.PDF para .NET no modifica el documento PDF original. En cambio, crea un nuevo documento PDF con la información del archivo actualizada. El documento PDF original permanece sin cambios.