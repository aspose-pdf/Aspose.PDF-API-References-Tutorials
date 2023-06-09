---
title: Eliminar todos los archivos adjuntos
linktitle: Eliminar todos los archivos adjuntos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar todos los archivos adjuntos de un archivo PDF con Aspose.PDF para .NET. Guía paso a paso para un fácil manejo.
type: docs
weight: 20
url: /es/net/programming-with-attachments/delete-all-attachments/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para eliminar todos los archivos adjuntos de un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde se encuentra el archivo PDF del que desea eliminar los archivos adjuntos. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: Abra el documento PDF existente

Abrimos el documento PDF existente usando la ruta especificada.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Paso 3: eliminar todos los archivos adjuntos

Eliminamos todos los archivos adjuntos del documento.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Paso 4: Guarde el archivo actualizado

Finalmente, guardamos el archivo PDF actualizado con el nombre "DeleteAllAttachments_out.pdf" en el directorio especificado.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Ejemplo de código fuente para Eliminar todos los archivos adjuntos con Aspose.PDF para .NET 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Eliminar todos los archivos adjuntos
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Guardar archivo actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Conclusión

En este tutorial, explicamos cómo eliminar todos los archivos adjuntos de un archivo PDF utilizando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para limpiar sus documentos PDF eliminando todos los archivos adjuntos no deseados.
