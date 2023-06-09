---
title: Agregar sello de imagen
linktitle: Agregar sello de imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar fácilmente un sello de imagen a sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar un búfer de imagen a un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo usar el código fuente de C# provisto para agregar un búfer de imagen personalizado a una página específica en el documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Creando el framebuffer

Ahora que ha cargado el documento PDF, puede crear el sello de imagen para agregar. Aquí está cómo hacerlo:

```csharp
// Crear el búfer de cuadro
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

El código anterior crea un nuevo búfer de imagen utilizando el archivo "aspose-logo.jpg". Asegúrese de que la ruta del archivo de imagen sea correcta.

## Paso 4: Configuración de las propiedades del búfer de imagen

Antes de agregar el sello de imagen al documento PDF, puede configurar varias propiedades del sello, como la opacidad, el tamaño, la posición, etc. Así es como se hace:

```csharp
// Configurar las propiedades del búfer de imagen
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 5: agregar el sello de imagen al PDF

Ahora que el sello de imagen está listo, puede agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
// Agregue el búfer de marco a la página específica
pdfDocument.Pages[1].AddStamp(imageStamp);
```

El código anterior agrega el búfer de imagen a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 6: Guarde el documento de salida

Una vez que haya agregado el búfer de imagen, puede guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para Agregar sello de imagen usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Crear sello de imagen
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha aprendido a agregar un búfer de imagen mediante Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar sellos de imagen personalizados a documentos PDF.
