---
title: Obtener información del archivo
linktitle: Obtener información del archivo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar la función GetFileInfo de Aspose.PDF para .NET para recuperar información de metadatos sobre un documento PDF.
type: docs
weight: 180
url: /es/net/programming-with-document/getfileinfo/
---

 Aspose.PDF para .NET es una popular biblioteca de manipulación de PDF que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de recuperar información sobre los metadatos de un documento PDF. Este tutorial lo guiará a través de los pasos para usar el`GetFileInfo`función de Aspose.PDF para .NET para recuperar información sobre los metadatos de un documento PDF.

## Paso 1: Instale Aspose.PDF para .NET

 Para usar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde el[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP en una carpeta de su computadora. Luego deberá agregar una referencia a Aspose.PDF para .NET DLL en su proyecto .NET.

## Paso 2: Cargue el documento PDF

 Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetFileInfo` función para recuperar información sobre los metadatos de un documento PDF.

El primer paso para usar esta función es cargar el documento PDF sobre el que desea recuperar información. Para hacer esto, puede usar el siguiente código:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abre el documento PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede usar para recuperar información sobre los metadatos del documento.

## Paso 3: recuperar los metadatos del documento

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

### El código fuente de ejemplo obtiene información del archivo PDF usando Aspose.PDF para .NET

 Aquí está el código fuente completo para recuperar los metadatos de un documento PDF usando el`GetFileInfo` característica de Aspose.PDF para .NET:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abre el documento PDF
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