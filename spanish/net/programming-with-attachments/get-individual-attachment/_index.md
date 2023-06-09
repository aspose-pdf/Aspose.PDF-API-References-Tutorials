---
title: Obtener archivo adjunto individual
linktitle: Obtener archivo adjunto individual
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a obtener un archivo adjunto individual en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-attachments/get-individual-attachment/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para obtener un adjunto individual de un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde se encuentra el archivo PDF desde el que desea obtener el archivo adjunto individual. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: Abra el documento PDF existente

Abrimos el documento PDF existente usando la ruta especificada.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Paso 3: Obtención de un archivo adjunto específico

Recuperamos un archivo adjunto específico de la colección de archivos adjuntos del documento. En este ejemplo, obtenemos el primer adjunto usando el índice 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Paso 4: obtenga las propiedades del archivo

Mostramos las propiedades de los archivos adjuntos, como el nombre, la descripción, el tipo MIME, el hash de control, la fecha de creación, la fecha de modificación y el tamaño.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Comprobar si los parámetros del objeto contienen información adicional
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Paso 5: recupere el archivo adjunto y guárdelo en un archivo

Recuperamos el contenido del archivo adjunto y lo guardamos en un archivo de texto. En este ejemplo, el archivo se guarda con el nombre "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Ejemplo de código fuente para Obtener datos adjuntos individuales mediante Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Obtener un archivo incrustado particular
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Obtener las propiedades del archivo
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Comprobar si el objeto de parámetro contiene los parámetros
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
// Obtener el archivo adjunto y escribir en un archivo o transmisión
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusión

En este tutorial, explicamos cómo obtener un archivo adjunto individual de un archivo PDF usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para extraer y guardar archivos adjuntos de sus archivos PDF.
