---
title: Obtener información del archivo en formato PDF
linktitle: Obtener información del archivo en formato PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar la función GetFileInfo en archivos PDF de Aspose.PDF para .NET para recuperar información de metadatos sobre un documento PDF.
type: docs
weight: 180
url: /es/net/programming-with-document/getfileinfo/
---
 Aspose.PDF para .NET es una biblioteca de manipulación de PDF muy popular que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de recuperar información sobre los metadatos de un documento PDF. Este tutorial le guiará a través de los pasos para utilizar la biblioteca.`GetFileInfo` característica de Aspose.PDF para .NET para recuperar información sobre los metadatos de un documento PDF.

## Paso 1: Instalar Aspose.PDF para .NET

 Para utilizar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP en una carpeta de su computadora. Luego, deberá agregar una referencia a la DLL Aspose.PDF para .NET en su proyecto .NET.

## Paso 2: Cargue el documento PDF

 Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetFileInfo` Función para recuperar información sobre los metadatos de un documento PDF.

El primer paso para utilizar esta función es cargar el documento PDF del que desea recuperar información. Para ello, puede utilizar el siguiente código:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede utilizar para recuperar información sobre los metadatos del documento.

## Paso 3: Recuperar los metadatos del documento

Para recuperar información sobre los metadatos de un documento PDF, puede utilizar el siguiente código:

```csharp
// Obtener información del documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostrar información del documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

En el código anterior, cada línea recupera una propiedad de metadatos diferente del documento PDF y la envía a la consola. Puede personalizar este código para recuperar solo las propiedades que le interesan.

### Código fuente de ejemplo para obtener información de un archivo PDF usando Aspose.PDF para .NET

 Aquí está el código fuente completo para recuperar los metadatos de un documento PDF usando el`GetFileInfo` Característica de Aspose.PDF para .NET:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Obtener información del documento
DocumentInfo docInfo = pdfDocument.Info;

// Mostrar información del documento
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusión

En este tutorial, hemos analizado cómo utilizar Aspose.PDF para .NET para recuperar información sobre los metadatos de un documento PDF. Al cargar un documento PDF y acceder a sus propiedades de metadatos, puede recopilar información sobre las características y propiedades del documento. Aspose.PDF para .NET proporciona una API sencilla y fácil de usar para trabajar con documentos PDF, incluida la recuperación de información de metadatos, lo que lo convierte en una herramienta valiosa para la manipulación de PDF en aplicaciones .NET.

### Preguntas frecuentes

#### P: ¿Qué son los metadatos en un documento PDF?

R: Los metadatos de un documento PDF hacen referencia a la información que describe las propiedades y características del documento. Esta información suele incluir el título del documento, el autor, el tema, las palabras clave, la fecha de creación, la fecha de modificación, etc.

#### P: ¿Cómo puedo instalar Aspose.PDF para .NET en mi proyecto .NET?

 R: Para instalar Aspose.PDF para .NET, debe descargar la biblioteca desde el sitio[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Después de la descarga, extraiga el contenido del archivo ZIP y agregue una referencia a la DLL Aspose.PDF para .NET en su proyecto .NET.

#### P: ¿Puedo personalizar el código para recuperar únicamente propiedades de metadatos específicas?

R: Sí, puedes personalizar el código para recuperar propiedades de metadatos específicas comentando las líneas que no necesitas. Cada línea del código corresponde a una propiedad de metadatos específica, por lo que puedes incluir o excluir propiedades según tus requisitos.

#### P: ¿Qué tipos de propiedades de metadatos puedo recuperar usando Aspose.PDF para .NET?

R: Con Aspose.PDF para .NET, puede recuperar varias propiedades de metadatos de un documento PDF, incluido el autor, el título, el tema, las palabras clave, la fecha de creación y la fecha de modificación.