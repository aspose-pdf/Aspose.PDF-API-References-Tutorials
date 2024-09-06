---
title: Número de página en el encabezado y pie de página mediante cuadro flotante
linktitle: Número de página en el encabezado y pie de página mediante cuadro flotante
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar el número de página en el encabezado y pie de página de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
En este tutorial, le mostraremos paso a paso cómo agregar un número de página en el encabezado y pie de página de un documento PDF usando FloatingBox con Aspose.PDF para .NET. Usaremos el código fuente de C# provisto para crear un documento PDF, agregar una página, crear un FloatingBox, establecer su posición y agregarle el número de página, luego guardaremos el documento PDF modificado.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Crear el documento PDF y agregar una página

El primer paso es crear una instancia del documento PDF y agregarle una página. A continuación, le indicamos cómo hacerlo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear una instancia del documento PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Agregar una página al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF.

## Paso 3: Crear el FloatingBox y agregar el número de página

Ahora que la página está agregada al documento PDF, podemos crear un FloatingBox, establecer su posición y agregarle el número de página. A continuación, le indicamos cómo hacerlo:

```csharp
// Crea un FloatingBox con un ancho de 140 y una altura de 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Establecer la posición izquierda del párrafo
box1. Left = 2;

// Establecer la posición superior del párrafo
box1. Top = 10;

// Añade el número de página al FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Añade el FloatingBox a la página
page.Paragraphs.Add(box1);
```

El código anterior crea un FloatingBox con un ancho de 140 y una altura de 80. A continuación, establecemos su posición especificando los valores izquierdo y superior. Por último, agregamos el número de página al FloatingBox mediante un TextFragment que contiene la sintaxis "($p/ $P )", que se reemplazará con el número de página actual y el número total de páginas.

## Paso 4: Guardar el documento PDF modificado

Una vez que se agrega el número de página al encabezado o pie de página mediante FloatingBox, podemos guardar el documento PDF modificado. A continuación, le indicamos cómo hacerlo:

```csharp
// Guardar el documento PDF modificado
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Código fuente de muestra para numeración de página en encabezado y pie de página mediante cuadro flotante con Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia de documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Agregar una página al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inicializa una nueva instancia de la clase FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valor flotante que indica la posición izquierda del párrafo
box1.Left = 2;

// Valor flotante que indica la posición superior del párrafo
box1.Top = 10;

// Añade las macros a la colección de párrafos de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Añadir un floatingBox a la página
page.Paragraphs.Add(box1);

// Guardar el documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusión

¡Felicitaciones! Aprendió a agregar números de página en el encabezado y pie de página de un documento PDF usando FloatingBox con Aspose.PDF para .NET. Ahora puede personalizar sus encabezados y pies de página agregando información dinámica como el número de página.

### Preguntas frecuentes

#### P: ¿Qué es un FloatingBox y cómo se utiliza para agregar números de página en el encabezado o pie de página de un documento PDF?

A: FloatingBox es un elemento de diseño versátil en Aspose.PDF que puede contener distintos tipos de contenido, incluidos texto e imágenes. En este tutorial, se utiliza para crear un contenedor para el número de página, lo que le permite insertar dinámicamente el número de página actual y el recuento total de páginas en el encabezado o pie de página.

#### P: ¿Cómo logra el código fuente C# proporcionado agregar números de página usando un FloatingBox?

A: El fragmento de código demuestra cómo crear un documento PDF, agregar una página, crear un FloatingBox, establecer su posición dentro de la página e insertar el número de página mediante un TextFragment. La sintaxis "($p/ $P )" en el TextFragment se reemplaza con el número de página actual y el recuento total de páginas.

#### P: ¿Puedo personalizar la apariencia y el formato del número de página agregado mediante FloatingBox?

R: Sí, puede personalizar la apariencia del número de página modificando las propiedades de TextFragment dentro de FloatingBox. Puede cambiar el tamaño de fuente, el color, el estilo, la alineación y otras opciones de formato.

#### P: ¿Es posible agregar diferentes elementos dinámicos, como fecha y hora, al encabezado o pie de página utilizando un enfoque similar?

R: Por supuesto. Puedes agregar diferentes elementos dinámicos como fecha, hora, metadatos del documento o texto personalizado modificando el contenido de TextFragment dentro de FloatingBox. Puedes usar macros como "($p/ $P )" para los números de página o "($date)" para la fecha actual.

#### P: ¿Cómo especifico la posición del FloatingBox dentro de la sección de encabezado o pie de página?
 A: El código proporcionado establece la posición de FloatingBox usando el`Left` y`Top` Propiedades. Puede ajustar estos valores para posicionar el FloatingBox como desee dentro de la sección de encabezado o pie de página.

#### P: ¿Puedo utilizar una fuente o estilo diferente para el número de página en el encabezado o pie de página?

R: Sí, puede personalizar la fuente, el estilo y otras propiedades de formato del texto del número de página modificando las propiedades de TextFragment dentro de FloatingBox.

#### P: ¿Qué sucede si el contenido del FloatingBox excede sus dimensiones?

R: Si el contenido dentro del FloatingBox excede sus dimensiones, puede que se corte o que surjan problemas de diseño. Asegúrese de que las dimensiones del FloatingBox sean adecuadas para acomodar el contenido y considere ajustar el diseño de la página si es necesario.

#### P: ¿Es posible agregar varios FloatingBoxes con diferente contenido al encabezado o pie de página de la misma página?

R: Sí, puede agregar varios FloatingBoxes con contenido diferente al encabezado o pie de página de la misma página creando instancias de FloatingBox independientes y agregándolas a la colección Párrafos de la página.

#### P: ¿Puedo utilizar el método FloatingBox para agregar contenido a otras secciones del documento PDF, como el cuerpo o los márgenes?

R: Si bien los FloatingBoxes se utilizan comúnmente para encabezados y pies de página, también puedes usarlos para agregar contenido a otras secciones del documento PDF, como el cuerpo o los márgenes, posicionándolos adecuadamente dentro de la página.