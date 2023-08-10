---
title: Número de página en el pie de página del encabezado usando el cuadro flotante
linktitle: Número de página en el pie de página del encabezado usando el cuadro flotante
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar el número de página en el encabezado y pie de página de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar un número de página en el encabezado y pie de página de un documento PDF utilizando FloatingBox con Aspose.PDF para .NET. Usaremos el código fuente de C# provisto para crear un documento PDF, agregar una página, crear un FloatingBox, establecer su posición y agregarle el número de página, luego guardar el documento PDF modificado.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: crear el documento PDF y agregar una página

El primer paso es crear una instancia del documento PDF y agregarle una página. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear una instancia del documento PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Agregar una página al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF.

## Paso 3: Creando el FloatingBox y agregando el número de página

Ahora que la página se agregó al documento PDF, podemos crear un cuadro flotante, establecer su posición y agregarle el número de página. Así es cómo:

```csharp
// Cree un FloatingBox con un ancho de 140 y una altura de 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//Establecer la posición izquierda del párrafo
box1. Left = 2;

// Establecer la posición superior del párrafo
box1. Top = 10;

// Agregue el número de página al FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Agregar el FloatingBox a la página
page.Paragraphs.Add(box1);
```

El código anterior crea un FloatingBox con un ancho de 140 y una altura de 80. Luego, establecemos su posición especificando los valores izquierdo y superior. Finalmente, agregamos el número de página a FloatingBox usando un TextFragment que contiene la sintaxis "($p/ $P)" que será reemplazada con el número de página actual y el número total de páginas.

## Paso 4: Guardar el documento PDF modificado

Una vez que el número de página se agrega al encabezado o pie de página usando FloatingBox, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para el número de página en el pie de página del encabezado mediante el cuadro flotante mediante Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar instancia de documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Añadir una página en el documento pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inicializa una nueva instancia de la clase FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valor flotante que indica la posición izquierda del párrafo
box1.Left = 2;

// Valor flotante que indica la posición superior del párrafo
box1.Top = 10;

// Agregue las macros a la colección de párrafos de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//Agregar un cuadro flotante a la página
page.Paragraphs.Add(box1);

// Guardar el documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusión

¡Felicidades! Aprendió a agregar el número de página en el encabezado y pie de página de un documento PDF usando FloatingBox con Aspose.PDF para .NET. Ahora puede personalizar sus encabezados y pies de página agregando información dinámica, como el número de página.

### Preguntas frecuentes

#### P: ¿Qué es un cuadro flotante y cómo se usa para agregar números de página en el encabezado o pie de página de un documento PDF?

R: Un FloatingBox es un elemento de diseño versátil en Aspose.PDF que puede contener varios contenidos, incluidos texto e imágenes. En este tutorial, se usa para crear un contenedor para el número de página, lo que le permite insertar dinámicamente el número de página actual y el recuento total de páginas en el encabezado o pie de página.

#### P: ¿Cómo logra el código fuente de C# proporcionado agregar números de página usando un FloatingBox?

R: El fragmento de código muestra cómo crear un documento PDF, agregar una página, crear un cuadro flotante, establecer su posición dentro de la página e insertar el número de página mediante un TextFragment. La sintaxis "($p/ $P )" en TextFragment se reemplaza con el número de página actual y el recuento total de páginas.

#### P: ¿Puedo personalizar la apariencia y el formato del número de página agregado usando FloatingBox?

R: Sí, puede personalizar la apariencia del número de página modificando las propiedades de TextFragment dentro de FloatingBox. Puede cambiar el tamaño de fuente, el color, el estilo, la alineación y otras opciones de formato.

#### P: ¿Es posible agregar diferentes elementos dinámicos, como fecha y hora, al encabezado o pie de página usando un enfoque similar?

R: Absolutamente, puede agregar diferentes elementos dinámicos como fecha, hora, metadatos de documentos o texto personalizado modificando el contenido de TextFragment dentro de FloatingBox. Puede usar macros como "($p/ $P )" para los números de página o "($fecha)" para la fecha actual.

#### P: ¿Cómo especifico la posición de FloatingBox dentro de la sección de encabezado o pie de página?
 R: El código provisto establece la posición de FloatingBox usando el`Left` y`Top` propiedades. Puede ajustar estos valores para colocar el FloatingBox como desee dentro de la sección de encabezado o pie de página.

#### P: ¿Puedo usar una fuente o estilo diferente para el número de página en el encabezado o pie de página?

R: Sí, puede personalizar la fuente, el estilo y otras propiedades de formato del texto del número de página modificando las propiedades de TextFragment dentro de FloatingBox.

#### P: ¿Qué sucede si el contenido de FloatingBox excede sus dimensiones?

R: Si el contenido dentro de FloatingBox excede sus dimensiones, es posible que se corte o que surjan problemas de diseño. Asegúrese de que las dimensiones de FloatingBox sean adecuadas para acomodar el contenido y considere ajustar el diseño de la página si es necesario.

#### P: ¿Es posible agregar varios FloatingBoxes con diferente contenido al encabezado o pie de página de la misma página?

R: Sí, puede agregar varios FloatingBoxes con contenido diferente al encabezado o pie de página de la misma página creando instancias de FloatingBox separadas y agregándolas a la colección de párrafos de la página.

#### P: ¿Puedo usar el método FloatingBox para agregar contenido a otras secciones del documento PDF, como el cuerpo o los márgenes?

R: Si bien los cuadros flotantes se usan comúnmente para encabezados y pies de página, también puede usarlos para agregar contenido a otras secciones del documento PDF, como el cuerpo o los márgenes, colocándolos en consecuencia dentro de la página.