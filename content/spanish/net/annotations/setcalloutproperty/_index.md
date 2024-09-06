---
title: Establecer propiedad de llamada en archivo PDF
linktitle: Establecer propiedad de llamada en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar la propiedad de llamada en un archivo PDF usando Aspose.PDF para .NET en este tutorial detallado paso a paso.
type: docs
weight: 130
url: /es/net/annotations/setcalloutproperty/
---
## Introducción

Para crear documentos PDF profesionales y visualmente atractivos, a menudo es necesario añadir anotaciones que llamen la atención sobre un contenido específico. Una de esas anotaciones es el texto destacado, que es como esos globos de diálogo que se ven en los cómics. Ayudan a aclarar o enfatizar el texto dentro de un PDF. Aspose.PDF para .NET hace que sea increíblemente fácil añadir este tipo de anotaciones a los documentos y, en este tutorial, explicaremos cómo configurar la propiedad de texto destacado en un archivo PDF utilizando esta potente biblioteca. Tanto si es un desarrollador experimentado como si está empezando, al final de esta guía comprenderá claramente cómo trabajar con textos destacados en archivos PDF.

## Prerrequisitos

Antes de sumergirnos en el código, cubramos los aspectos esenciales que necesitas para comenzar.

1.  Aspose.PDF para .NET: Asegúrese de tener instalada la biblioteca Aspose.PDF para .NET. Puede descargarla desde[aquí](https://releases.aspose.com/pdf/net/).
2. IDE: Un entorno de desarrollo como Visual Studio.
3. .NET Framework: asegúrese de tener .NET instalado en su máquina.
4. Licencia temporal: si desea probar todas las funciones de Aspose.PDF sin limitaciones, obtenga una[licencia temporal](https://purchase.aspose.com/temporary-license/).

## Importar paquetes

Antes de comenzar a escribir el código, debe importar los paquetes necesarios que le permitirán trabajar con archivos PDF y anotaciones.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Estas importaciones le proporcionarán todas las clases y métodos necesarios para manipular documentos PDF y crear anotaciones como el llamado.

## Paso 1: Inicializar el documento PDF

El primer paso de nuestro recorrido es crear un nuevo documento PDF en el que agregaremos nuestra anotación destacada. Piense en esto como si estuviera creando un lienzo en blanco en el que puede comenzar a agregar elementos.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializar un nuevo documento PDF
Document doc = new Document();
```
 Aquí estamos creando uno nuevo`Document` objeto que servirá como nuestro archivo PDF.`dataDir` La variable se establece en el directorio donde desea guardar el archivo PDF después de que hayamos terminado.

## Paso 2: Agregar una nueva página al documento

Un documento PDF puede tener varias páginas y, en este paso, agregaremos una nueva página a nuestro documento. Esta página será donde se colocará nuestra anotación destacada.

```csharp
//Agregar una nueva página al documento
Page page = doc.Pages.Add();
```
 El`Pages.Add()`El método se utiliza para agregar una nueva página a la`doc` objeto. La nueva página se almacena en el`page` variable, que usaremos más adelante al agregar la anotación.

## Paso 3: Definir la apariencia predeterminada

Las anotaciones, al igual que el texto destacado, tienen una apariencia visual que puedes personalizar. En este paso, definiremos cómo debe verse el texto dentro del texto destacado.

```csharp
// Definir la apariencia predeterminada para la anotación
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Creamos una`DefaultAppearance` objeto que define el color del texto y el tamaño de la fuente. Aquí, el texto será rojo y el tamaño de la fuente se establecerá en 10. Esta apariencia se aplicará a la anotación de llamada.

## Paso 4: Crear la anotación de texto libre

Ahora es el momento de crear la anotación propiamente dicha. La anotación de texto libre es lo que nos permite agregar un texto destacado con un estilo y un texto específicos.

```csharp
// Crear una anotación de texto libre con un texto destacado
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Creamos una`FreeTextAnnotation` objeto con coordenadas específicas, que definen su posición en la página.`Intent` está configurado para`FreeTextCallout` , lo que indica que se trata de una anotación de llamada.`EndingStyle` está configurado para`OpenArrow`lo que significa que la línea de llamada terminará con una flecha abierta.

## Paso 5: Defina los puntos de la línea de llamada

Una anotación de llamada tiene una línea que señala el área de interés. Aquí, definiremos los puntos que componen esta línea.

```csharp
// Definir los puntos para la línea de llamada
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 El`Callout` La propiedad es un conjunto de`Point` objetos, cada uno de los cuales representa una coordenada en la página. Estos puntos definen la ruta de la línea de llamada, lo que le da la apariencia clásica de bocadillo de diálogo.

## Paso 6: Agrega la anotación a la página

Después de crear y configurar nuestra anotación, el siguiente paso es agregarla a la página.

```csharp
// Añadir la anotación a la página
page.Annotations.Add(fta);
```
 El`Annotations.Add()` El método se utiliza para colocar la anotación en la página que creamos anteriormente. Este paso "dibuja" efectivamente el texto destacado en la página PDF.

## Paso 7: Establezca el contenido de texto enriquecido

Las anotaciones de texto destacado pueden incluir texto enriquecido, lo que permite incluir contenido formateado dentro de la burbuja. Agreguemos un texto de muestra.

```csharp
// Establecer el texto enriquecido para la anotación
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Esta es una muestra</span></p></body>";
```
 El`RichText` La propiedad se configura con contenido HTML. Esto permite un formato detallado dentro del texto destacado, como especificar el tamaño de fuente, el color y el estilo.

## Paso 8: Guarde el documento PDF

Finalmente, después de configurar todo, debemos guardar el documento. Este paso finaliza la creación del PDF con la anotación de llamada.

```csharp
// Guardar el documento
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 El`Save()` El método guarda el documento en el directorio especificado con el nombre de archivo "SetCalloutProperty.pdf". Este paso concluye nuestro proceso de creación de PDF.

## Conclusión

¡Y ya está! Acaba de crear un documento PDF con una anotación de llamada con Aspose.PDF para .NET. Esta anotación puede resultar increíblemente útil para resaltar o explicar partes específicas de su documento. Aspose.PDF ofrece una potente API que hace que la manipulación de PDF sea sencilla y flexible. Ya sea que esté agregando anotaciones, convirtiendo documentos o manejando tareas PDF complejas, Aspose.PDF lo tiene cubierto.

## Preguntas frecuentes

### ¿Puedo personalizar aún más la apariencia del llamado?

¡Por supuesto! Puedes personalizar varios aspectos como el color de línea, el grosor y la familia de fuentes y el estilo del texto.

### ¿Es posible agregar múltiples llamadas en una sola página?

Sí, puedes agregar tantas llamadas como necesites repitiendo los pasos para cada anotación.

### ¿Cómo cambio la posición del llamado?

 Simplemente modifique las coordenadas en el`Rectangle` y`Callout` Propiedades para reposicionar la anotación.

### ¿Puedo agregar otros tipos de anotaciones usando Aspose.PDF?

Sí, Aspose.PDF admite varios tipos de anotaciones, incluidos resaltados, sellos y archivos adjuntos.

### ¿El contenido de texto enriquecido está limitado a HTML?

 El`RichText` La propiedad admite un subconjunto de HTML, lo que le permite incluir texto con estilo y formato básico.