---
title: Obtener metadatos XMP
linktitle: Obtener metadatos XMP
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar la función GetXmpMetadata de Aspose.PDF para .NET para extraer metadatos XMP de un documento PDF utilizando el código fuente C#.
type: docs
weight: 200
url: /es/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF para .NET es una popular biblioteca de manipulación de PDF que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de extraer metadatos XMP de un documento PDF. Este tutorial lo guiará a través de los pasos para usar el`GetXmpMetadata` característica de Aspose.PDF para .NET para extraer metadatos XMP de un documento PDF.

## Paso 1: Instale Aspose.PDF para .NET

 Para utilizar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP a una carpeta en su computadora. Luego deberá agregar una referencia a Aspose.PDF para .NET DLL en su proyecto .NET.

## Paso 2: cargue el documento PDF

Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetXmpMetadata` función para extraer metadatos XMP de un documento PDF.

El primer paso para utilizar esta función es cargar el documento PDF del que desea extraer metadatos XMP. Para hacer esto, puedes usar el siguiente código:

```csharp
// La ruta al documento PDF.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede utilizar para extraer metadatos XMP.

## Paso 3: extraer metadatos XMP

Para extraer metadatos XMP de un documento PDF, puede utilizar el siguiente código:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 En el código anterior,`xmp:CreateDate`, `xmp:Nickname` , y`xmp:CustomProperty` son ejemplos de propiedades de metadatos XMP que puede extraer de un documento PDF. Puede reemplazar estos nombres de propiedades con los nombres de cualquier otra propiedad de metadatos XMP que desee extraer.

### Código fuente de ejemplo para obtener metadatos XMP usando Aspose.PDF para .NET

 Aquí está el código fuente completo para extraer metadatos XMP de un documento PDF usando el`GetXmpMetadata` característica de Aspose.PDF para .NET:

```csharp
// La ruta al documento PDF.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extraer metadatos XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código extraerá metadatos XMP del documento PDF y los enviará a la consola.

## Conclusión

En este tutorial, analizamos cómo utilizar Aspose.PDF para .NET para extraer metadatos XMP de un documento PDF. Los metadatos XMP proporcionan información valiosa sobre un documento y Aspose.PDF para .NET permite a los desarrolladores acceder a esta información y utilizarla en sus aplicaciones según sea necesario. Al extraer metadatos XMP, los desarrolladores pueden obtener información sobre la fecha de creación, el autor y otros datos descriptivos de un documento. Esta información se puede utilizar para mejorar la funcionalidad y la experiencia del usuario de las aplicaciones PDF. Aspose.PDF para .NET proporciona una API sencilla y directa para acceder a metadatos XMP, lo que facilita la integración de esta función en aplicaciones .NET.

### Preguntas frecuentes

#### P: ¿Qué son los metadatos XMP en un documento PDF?

R: Los metadatos XMP en un documento PDF se refieren a la información de la Plataforma de metadatos extensible (XMP) que está incrustada en el documento. Los metadatos XMP proporcionan una forma estándar de almacenar información sobre el documento, como el autor, la fecha de creación, las palabras clave y otros datos descriptivos. Permite una fácil recuperación e intercambio de metadatos entre diferentes sistemas y aplicaciones.

#### P: ¿Qué tipo de información se puede extraer utilizando la función GetXmpMetadata?

 R: La función GetXmpMetadata permite a los desarrolladores extraer varias propiedades de metadatos XMP de un documento PDF. Algunos ejemplos de propiedades de metadatos XMP que se pueden extraer son`xmp:CreateDate`, `xmp:Nickname` , y`xmp:CustomProperty`. Los desarrolladores pueden acceder a estas propiedades y utilizarlas en sus aplicaciones según sea necesario.

#### P: ¿Puedo extraer propiedades de metadatos XMP personalizadas usando Aspose.PDF para .NET?

R: Sí, puede extraer propiedades de metadatos XMP personalizadas utilizando Aspose.PDF para .NET. Se pueden incluir propiedades de metadatos XMP personalizadas en un documento PDF para almacenar información adicional específica de su aplicación o requisitos. Puede extraer y utilizar estas propiedades personalizadas según sea necesario.

#### P: ¿Aspose.PDF para .NET es capaz de extraer otra información de metadatos de un documento PDF?

R: Sí, Aspose.PDF para .NET proporciona varias funciones para extraer información de metadatos de un documento PDF. Además de los metadatos XMP, también puede extraer información como información del documento (título, autor, tema, palabras clave), versión PDF, detalles de cifrado y más.