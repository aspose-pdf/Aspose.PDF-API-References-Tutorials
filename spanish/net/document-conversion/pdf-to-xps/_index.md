---
title: PDF a XPS
linktitle: PDF a XPS
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a XPS utilizando Aspose.PDF para .NET.
type: docs
weight: 220
url: /es/net/document-conversion/pdf-to-xps/
---
En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato XPS (Especificación de papel XML) usando Aspose.PDF para .NET. El formato XPS es un formato de archivo basado en XML que se utiliza para representar documentos electrónicamente. Siguiendo los pasos a continuación, podrá convertir un archivo PDF a formato XPS.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
En este paso, cargaremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: crea una instancia de las opciones de guardado de XPS
Después de cargar el archivo PDF, crearemos una instancia de las opciones de guardado de XPS. Usa el siguiente código:

```csharp
// Crear una instancia de las opciones de guardado de XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Paso 3: Guardar el archivo XPS resultante
Ahora guardaremos el archivo PDF convertido en formato XPS. Usa el siguiente código:

```csharp
// Guarde el documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 El código anterior guarda el archivo PDF convertido en formato XPS con el nombre de archivo`"PDFToXPS_out.xps"`.


### Código fuente de ejemplo para PDF a XPS usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Crear una instancia de las opciones de guardado de XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Guarde el documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato XPS usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF a formato XPS. Esta característica es útil cuando desea ver o imprimir documentos PDF en formato XPS.

### Preguntas frecuentes

#### P: ¿El formato XPS es adecuado para la compatibilidad multiplataforma?

R: El formato XPS, al ser un formato de archivo basado en XML, es independiente de la plataforma y se puede ver en varios sistemas operativos y dispositivos. Los archivos XPS son compatibles con las plataformas Windows de forma predeterminada, y algunas aplicaciones y visores de terceros pueden estar disponibles para otras plataformas.

#### P: ¿Puede Aspose.PDF para .NET manejar archivos PDF complejos con varias páginas e imágenes durante la conversión XPS?

R: Sí, Aspose.PDF para .NET puede manejar archivos PDF complejos con varias páginas e imágenes durante la conversión XPS. Conserva con precisión el diseño, las imágenes y el contenido textual del PDF mientras lo convierte a formato XPS.

#### P: ¿Es posible especificar configuraciones u opciones adicionales durante el proceso de conversión de XPS?

 R: Sí, Aspose.PDF para .NET ofrece varias opciones y configuraciones que se pueden personalizar durante el proceso de conversión de XPS. Puede controlar la compresión de la imagen, la incrustación de fuentes y otras configuraciones usando el`XpsSaveOptions` clase.

#### P: ¿Se pueden convertir archivos PDF protegidos con contraseña a formato XPS usando Aspose.PDF para .NET?

 R: Sí, Aspose.PDF para .NET admite la conversión de archivos PDF protegidos con contraseña a formato XPS. Al cargar un PDF protegido con contraseña, puede proporcionar la contraseña mediante el`Document` constructor de clase o configurando el`Password` propiedad antes de cargar el PDF.