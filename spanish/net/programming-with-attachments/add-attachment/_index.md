---
title: Añadir un adjunto
linktitle: Añadir un adjunto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar archivos adjuntos a sus archivos PDF usando Aspose.PDF para .NET. Guía paso a paso para un fácil manejo.
type: docs
weight: 10
url: /es/net/programming-with-attachments/add-attachment/
---

En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para agregar un archivo adjunto a un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde se encuentra el archivo PDF al que desea agregar el archivo adjunto. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: Abra el documento PDF existente

Abrimos el documento PDF existente usando la ruta especificada.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Paso 3: configurar el nuevo archivo para agregarlo como archivo adjunto

Configuramos el nuevo archivo que queremos añadir como archivo adjunto. En este ejemplo, agregamos un archivo de texto con el nombre "prueba.txt" y una descripción "Archivo de texto de ejemplo".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Paso 4: agregar el archivo adjunto a la colección de archivos adjuntos del documento

Agregamos el archivo adjunto a la colección de archivos adjuntos del documento.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Paso 5: Guardar el nuevo archivo de salida

Finalmente, guardamos el nuevo archivo PDF resultante con el nombre "AddAttachment_out.pdf" en el directorio especificado.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Ejemplo de código fuente para Agregar archivo adjunto usando Aspose.PDF para .NET
 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Configurar un nuevo archivo para agregarlo como archivo adjunto
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Agregar archivo adjunto a la colección de archivos adjuntos del documento
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Guardar nueva salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Conclusión

En este tutorial, explicamos cómo agregar un archivo adjunto a un archivo PDF utilizando Aspose.PDF para .NET. Ahora puede usar este conocimiento para agregar archivos adicionales como archivos adjuntos a sus documentos PDF.
