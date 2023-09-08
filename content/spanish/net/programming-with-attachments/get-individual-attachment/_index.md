---
title: Obtenga un archivo adjunto individual en un archivo PDF
linktitle: Obtenga un archivo adjunto individual en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo obtener un archivo adjunto individual en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-attachments/get-individual-attachment/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para obtener un archivo adjunto individual de un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configurar su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde se encuentra el archivo PDF del que desea obtener el archivo adjunto individual. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: abra el documento PDF existente

Abrimos el documento PDF existente usando la ruta especificada.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Paso 3: Obtener un archivo adjunto específico

Recuperamos un archivo adjunto específico de la colección de archivos adjuntos del documento. En este ejemplo, obtenemos el primer archivo adjunto usando el índice 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Paso 4: obtener propiedades del archivo

Mostramos propiedades del archivo adjunto como nombre, descripción, tipo MIME, hash de control, fecha de creación, fecha de modificación y tamaño.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Compruebe si los parámetros del objeto contienen información adicional
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Paso 5: recuperar el archivo adjunto y guardarlo en un archivo

Recuperamos el contenido del archivo adjunto y lo guardamos en un archivo de texto. En este ejemplo, el archivo se guarda con el nombre "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Código fuente de muestra para obtener un archivo adjunto individual usando Aspose.PDF para .NET 

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
//Compruebe si el objeto de parámetro contiene los parámetros
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
// Obtenga el archivo adjunto y escriba en un archivo o transmisión
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusión

En este tutorial, explicamos cómo obtener un archivo adjunto individual de un archivo PDF usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para extraer y guardar archivos adjuntos de sus archivos PDF.

### Preguntas frecuentes para obtener archivos adjuntos individuales en archivos PDF

#### P: ¿Cuál es el propósito de obtener un archivo adjunto individual de un documento PDF?

R: Obtener un archivo adjunto individual le permite extraer y guardar un archivo incrustado específico dentro de un PDF, lo que puede resultar útil para análisis o manipulación posteriores.

#### P: ¿Cómo puedo beneficiarme de este tutorial en mis tareas relacionadas con PDF?

R: Este tutorial proporciona instrucciones paso a paso y código fuente C# para recuperar y guardar un archivo adjunto particular de un documento PDF usando Aspose.PDF para .NET.

#### P: ¿A qué propiedades de los archivos adjuntos puedo acceder usando este tutorial?

R: Puede acceder a las propiedades del archivo adjunto, como nombre, descripción, tipo MIME, hash de control, fecha de creación, fecha de modificación y tamaño del archivo adjunto específico.

#### P: ¿Puedo modificar el código para obtener archivos adjuntos distintos al primero?

 R: Por supuesto, puedes ajustar el índice (p. ej.,`pdfDocument.EmbeddedFiles[1]`) para recuperar archivos adjuntos en diferentes índices dentro del PDF.

#### P: ¿Cómo guardo el archivo adjunto recuperado en un archivo?

R: Este tutorial proporciona código para recuperar el contenido del archivo adjunto y guardarlo en un archivo de texto con un nombre específico.

#### P: ¿Cuál es el significado de la propiedad "Check Hash" en la información del archivo adjunto?

R: La propiedad "Check Hash" representa el valor hash de control del archivo adjunto, que se puede utilizar para verificar la integridad del archivo adjunto.

#### P: ¿Puedo ampliar este conocimiento para extraer archivos adjuntos con criterios específicos, como el tipo de archivo?

R: Sí, puede mejorar el código para filtrar archivos adjuntos según criterios específicos, como el tipo de archivo u otras propiedades.

#### P: ¿Cómo simplifica Aspose.PDF para .NET el proceso de extracción de archivos adjuntos individuales?

R: Aspose.PDF para .NET proporciona una API fácil de usar que facilita la extracción y manipulación de archivos adjuntos dentro de documentos PDF.

#### P: ¿Este tutorial también es relevante para archivos PDF protegidos con contraseña?

R: Sí, puede adaptar técnicas similares para recuperar archivos adjuntos individuales de archivos PDF protegidos con contraseña utilizando Aspose.PDF para .NET.
