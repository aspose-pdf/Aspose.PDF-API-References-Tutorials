---
title: Agregar sello de texto en archivo PDF
linktitle: Agregar sello de texto en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo agregar fácilmente un sello de texto en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
En este tutorial, le mostraremos paso a paso cómo agregar un sello de texto en un archivo PDF con Aspose.PDF para .NET. Le mostraremos cómo usar el código fuente de C# proporcionado para agregar un sello de texto personalizado a una página específica del archivo PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en el proyecto. A continuación, le indicamos cómo hacerlo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abrir el documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Creación del buffer de texto

Ahora que has cargado el documento PDF, puedes crear el sello de texto que deseas agregar. A continuación, te indicamos cómo hacerlo:

```csharp
// Crear el buffer de texto
TextStamp textStamp = new TextStamp("Example Stamp");
```

El código anterior crea un nuevo búfer de texto que contiene el texto especificado.

## Paso 4: Configuración de las propiedades del sello de texto

Antes de agregar el sello de texto al documento PDF, puede configurar varias propiedades del sello, como el fondo, la posición, la rotación, la fuente, el tamaño, etc. A continuación, le indicamos cómo hacerlo:

```csharp
// Configurar las propiedades del buffer de texto
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 5: Agregar sello de texto al PDF

Ahora que el sello de texto está listo, puedes agregarlo a una página específica del documento PDF. A continuación, te indicamos cómo hacerlo:

```csharp
//Agregar buffer de texto a una página específica
pdfDocument.Pages[1].AddStamp(textStamp);
```

El código anterior agrega el sello de texto a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 6: Guarde el documento de salida

Una vez que hayas añadido el sello de texto, puedes guardar el documento PDF editado. A continuación, te indicamos cómo hacerlo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF modificado en el directorio especificado.

### Código fuente de muestra para agregar un sello de texto con Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crear sello de texto
TextStamp textStamp = new TextStamp("Sample Stamp");

// Establecer si el sello es el fondo
textStamp.Background = true;

// Establecer origen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Girar sello
textStamp.Rotate = Rotation.on90;

// Establecer propiedades de texto
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Añadir sello a una página específica
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusión

¡Felicitaciones! Aprendió a agregar un sello de texto con Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar sellos de texto personalizados a documentos PDF.

### Preguntas frecuentes sobre cómo añadir un sello de texto a un archivo PDF

#### P: ¿Cuál es el propósito de agregar un sello de texto en un archivo PDF usando Aspose.PDF para .NET?

A: Agregar un sello de texto le permite colocar texto personalizado en una página específica de un documento PDF. Esta función es útil para agregar etiquetas, comentarios, marcas de agua o cualquier otra información textual para mejorar el contenido del documento y brindar contexto adicional.

#### P: ¿Puedo personalizar la apariencia del sello de texto, como la fuente, el tamaño, el color y la rotación?

 R: Sí, puede personalizar completamente la apariencia del sello de texto. El código fuente de C# proporcionado demuestra cómo configurar varias propiedades del sello.`TextStamp` objeto, incluyendo fuente, tamaño de fuente, estilo de fuente, color de texto, color de fondo y rotación.

#### P: ¿Es posible agregar varios sellos de texto a diferentes páginas del mismo documento PDF?

R: Por supuesto, puedes agregar varios sellos de texto a distintas páginas del mismo documento PDF. El código proporcionado en el tutorial te permite especificar la página de destino para agregar el sello de texto, lo que lo hace versátil para distintas páginas dentro del documento.

#### P: ¿Cómo especifico la posición del sello de texto dentro del documento PDF?

 A: Puede personalizar la posición del sello de texto modificando el`XIndent` y`YIndent` Propiedades de la`TextStamp` objeto. Estas propiedades definen las coordenadas de la esquina superior izquierda del sello en relación con el origen de la página.

#### P: ¿Puedo aplicar este método a documentos PDF existentes para agregar sellos de texto?

R: Sí, puedes aplicar este método a documentos PDF existentes para agregar sellos de texto. El código proporcionado en el tutorial demuestra cómo cargar un documento PDF existente y agregar un sello de texto a una página específica.

#### P: ¿Puedo agregar colores de fondo y de primer plano al sello de texto?

 R: Sí, puede agregar colores de fondo y de primer plano al sello de texto. Al configurar el`Background` propiedad a`true` , puede proporcionar un fondo de color para el sello de texto. Además, puede configurar el`TextState.ForegroundColor` propiedad para especificar el color del texto en sí.

#### P: ¿Cómo puedo asegurarme de que el sello de texto no oscurezca el contenido subyacente del documento PDF?

A: Al agregar un sello de texto, tenga en cuenta su ubicación para asegurarse de que no obstruya información importante ni afecte negativamente la legibilidad del documento. Puede ajustar la`XIndent` y`YIndent` Propiedades para posicionar el sello de texto apropiadamente.

#### P: ¿Puedo usar este método para agregar sellos que no sean texto, como imágenes o logotipos?

R: Este tutorial específico se centra en cómo agregar sellos de texto, pero también puede agregar otros tipos de sellos, como imágenes o logotipos, mediante Aspose.PDF para .NET. El proceso implica crear el objeto de sello adecuado y configurar sus propiedades.

#### P: ¿Cómo puedo automatizar el proceso de agregar sellos de texto a varios documentos PDF?

R: Puede automatizar el proceso de agregar sellos de texto a varios documentos PDF creando un script o programa que recorra una lista de documentos y aplique el mismo proceso de estampado de texto a cada uno.