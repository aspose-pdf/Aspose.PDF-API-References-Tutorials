---
title: Obtenga todos los archivos adjuntos en un archivo PDF
linktitle: Obtenga todos los archivos adjuntos en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo obtener todos los archivos adjuntos en un archivo PDF con Aspose.PDF para .NET. Guía paso a paso para un fácil manejo.
type: docs
weight: 40
url: /es/net/programming-with-attachments/get-all-the-attachments/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para obtener todos los archivos adjuntos en un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio donde se encuentra el archivo PDF del que desea obtener los archivos adjuntos. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: Abra el documento PDF existente

Abrimos el documento PDF existente usando la ruta especificada.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Paso 3: Obtención de la colección de archivos adjuntos

Obtenemos la colección de archivos adjuntos del documento.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Paso 4: Recuperar archivos adjuntos

Revisamos la colección para obtener todos los archivos adjuntos y mostrar su información. También guardamos archivos adjuntos en archivos individuales.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Comprobar si los parámetros del objeto contienen información adicional
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Recupere el archivo adjunto y guárdelo en un archivo
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Ejemplo de código fuente para Obtener todos los archivos adjuntos usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Obtener colección de archivos incrustados
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Obtener el recuento de los archivos incrustados
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Recorra la colección para obtener todos los archivos adjuntos
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Comprobar si el objeto de parámetro contiene los parámetros
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusión

En este tutorial, explicamos cómo obtener todos los archivos adjuntos de un archivo PDF usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para extraer y manipular archivos adjuntos de sus archivos PDF.

## Preguntas frecuentes para obtener todos los archivos adjuntos en un archivo PDF

#### P: ¿Por qué tendría que recuperar todos los archivos adjuntos de un documento PDF?

R: La recuperación de archivos adjuntos le permite acceder y manipular archivos adicionales incrustados en un PDF, lo que puede ser útil para archivar, compartir o procesar más.

#### P: ¿Qué tipos de archivos se pueden adjuntar a un documento PDF?

R: Los documentos PDF pueden contener una amplia gama de archivos adjuntos, incluidas imágenes, documentos, hojas de cálculo, archivos de audio y más.

#### P: ¿Cómo me ayuda este tutorial a recuperar archivos adjuntos de un PDF usando Aspose.PDF para .NET?

R: Este tutorial proporciona instrucciones paso a paso y código fuente de C# para acceder y recuperar todos los archivos adjuntos dentro de un documento PDF.

#### P: ¿Puedo recuperar archivos adjuntos específicos en lugar de todos los archivos adjuntos usando este tutorial?

R: Sí, puede modificar el código proporcionado para recuperar archivos adjuntos de forma selectiva según sus requisitos.

#### P: ¿Qué información sobre cada archivo adjunto puedo obtener usando este tutorial?

R: Este tutorial demuestra cómo recuperar y mostrar detalles como el nombre del archivo adjunto, la descripción, el tipo MIME, la fecha de creación, la fecha de modificación y el tamaño.

#### P: ¿Cómo se guardan los archivos adjuntos recuperados usando este tutorial?

R: El tutorial lo guía para guardar cada archivo adjunto recuperado como un archivo separado en el directorio especificado.

#### P: ¿Puedo usar este conocimiento para extraer archivos adjuntos de archivos PDF protegidos con contraseña?

R: Sí, puede aplicar principios similares para recuperar archivos adjuntos de archivos PDF protegidos con contraseña usando Aspose.PDF para .NET.

#### P: ¿Cómo facilita Aspose.PDF para .NET la recuperación de archivos adjuntos?

R: Aspose.PDF para .NET proporciona una API intuitiva que le permite acceder y manipular archivos adjuntos en documentos PDF fácilmente.

#### P: ¿Existen escenarios específicos en los que se recomienda recuperar archivos adjuntos?

R: La recuperación de archivos adjuntos es útil cuando necesita acceder a archivos incrustados en un PDF, como extraer imágenes, archivos de audio o documentos adicionales.