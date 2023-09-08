---
title: Agregar sello de texto en archivo PDF
linktitle: Agregar sello de texto en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo agregar fácilmente un sello de texto en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
En este tutorial, le explicaremos paso a paso cómo agregar un sello de texto en un archivo PDF usando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente C# proporcionado para agregar un sello de texto personalizado a una página específica del archivo PDF.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// abrir el documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: crear el búfer de texto

Ahora que ha subido el documento PDF, puede crear el sello de texto para agregar. He aquí cómo hacerlo:

```csharp
// Crear el búfer de texto
TextStamp textStamp = new TextStamp("Example Stamp");
```

El código anterior crea un nuevo búfer de texto que contiene el texto especificado.

## Paso 4: Configurar las propiedades del sello de texto

Antes de agregar el sello de texto al documento PDF, puede configurar varias propiedades del sello, como fondo, posición, rotación, fuente, tamaño, etc. Aquí se explica cómo:

```csharp
// Configurar las propiedades del búfer de texto
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

## Paso 5: Agregar sello de texto a PDF

Ahora que el sello de texto está listo, puedes agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
//Agregar búfer de texto a una página específica
pdfDocument.Pages[1].AddStamp(textStamp);
```

El código anterior agrega el sello de texto a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 6: guarde el documento de salida

Una vez que haya agregado el sello de texto, puede guardar el documento PDF editado. Así es cómo:

```csharp
// Guarde el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF modificado en el directorio especificado.

### Código fuente de muestra para Agregar sello de texto usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crear sello de texto
TextStamp textStamp = new TextStamp("Sample Stamp");

// Establecer si el sello es fondo
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

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusión

¡Enhorabuena! Ha aprendido cómo agregar un sello de texto usando Aspose.PDF para .NET. Ahora puedes aplicar este conocimiento a tus propios proyectos para agregar sellos de texto personalizados a documentos PDF.

### Preguntas frecuentes para agregar un sello de texto en un archivo PDF

#### P: ¿Cuál es el propósito de agregar un sello de texto en un archivo PDF usando Aspose.PDF para .NET?

R: Agregar un sello de texto le permite colocar texto personalizado en una página específica de un documento PDF. Esta función es útil para agregar etiquetas, comentarios, marcas de agua o cualquier otra información textual para mejorar el contenido del documento y proporcionar contexto adicional.

#### P: ¿Puedo personalizar la apariencia del sello de texto, como la fuente, el tamaño, el color y la rotación?

 R: Sí, puedes personalizar completamente la apariencia del sello de texto. El código fuente de C# proporcionado demuestra cómo configurar varias propiedades del`TextStamp` objeto, incluida la fuente, el tamaño de fuente, el estilo de fuente, el color del texto, el color de fondo y la rotación.

#### P: ¿Es posible agregar varios sellos de texto a diferentes páginas del mismo documento PDF?

R: Por supuesto, puedes agregar varios sellos de texto a diferentes páginas del mismo documento PDF. El código proporcionado en el tutorial le permite especificar la página de destino para agregar el sello de texto, lo que lo hace versátil para diferentes páginas dentro del documento.

#### P: ¿Cómo especifico la posición del sello de texto dentro del documento PDF?

 R: Puede personalizar la posición del sello de texto modificando el`XIndent` y`YIndent` propiedades de la`TextStamp` objeto. Estas propiedades definen las coordenadas de la esquina superior izquierda del sello en relación con el origen de la página.

#### P: ¿Puedo aplicar este método a documentos PDF existentes para agregar sellos de texto?

R: Sí, puede aplicar este método a documentos PDF existentes para agregar sellos de texto. El código proporcionado en el tutorial demuestra cómo cargar un documento PDF existente y agregar un sello de texto a una página específica.

#### P: ¿Puedo agregar colores de fondo y de primer plano al sello de texto?

 R: Sí, puedes agregar colores de fondo y de primer plano al sello de texto. Al configurar el`Background` propiedad a`true` , puede proporcionar un fondo de color para el sello de texto. Además, puede configurar el`TextState.ForegroundColor` propiedad para especificar el color del texto en sí.

#### P: ¿Cómo puedo asegurarme de que el sello de texto no oscurezca el contenido subyacente del documento PDF?

 R: Al agregar un sello de texto, tenga en cuenta su ubicación para asegurarse de que no obstruya información crítica ni afecte negativamente la legibilidad del documento. Puedes ajustar el`XIndent` y`YIndent` propiedades para colocar el sello de texto apropiadamente.

#### P: ¿Puedo utilizar este método para agregar sellos que no sean texto, como imágenes o logotipos?

R: Este tutorial específico se centra en agregar sellos de texto, pero de manera similar puede agregar otros tipos de sellos, como imágenes o logotipos, usando Aspose.PDF para .NET. El proceso implica crear el objeto de sello apropiado y configurar sus propiedades.

#### P: ¿Cómo puedo automatizar el proceso de agregar sellos de texto a varios documentos PDF?

R: Puede automatizar el proceso de agregar sellos de texto a varios documentos PDF creando un script o programa que recorra una lista de documentos y aplique el mismo proceso de sellado de texto a cada uno.