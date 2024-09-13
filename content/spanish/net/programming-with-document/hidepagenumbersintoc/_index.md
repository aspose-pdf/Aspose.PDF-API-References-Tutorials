---
title: Ocultar números de página en la tabla de contenidos
linktitle: Ocultar números de página en la tabla de contenidos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a ocultar los números de página en la tabla de contenido con Aspose.PDF para .NET. Siga esta guía detallada con ejemplos de código para crear archivos PDF profesionales.
type: docs
weight: 220
url: /es/net/programming-with-document/hidepagenumbersintoc/
---
## Introducción

Cuando trabajas con archivos PDF, a veces es posible que quieras generar una tabla de contenido (TOC) pero mantener la nitidez ocultando los números de página. Tal vez el documento fluya mejor sin ellos, o tal vez sea una elección estética. Cualquiera sea tu motivo, si trabajas con Aspose.PDF para .NET, este tutorial te mostrará exactamente cómo ocultar los números de página en tu TOC.

## Prerrequisitos

Antes de comenzar, hay algunas cosas que necesitará tener en cuenta. A continuación, se incluye una lista de verificación rápida:

- Visual Studio instalado: necesitará una versión funcional de Visual Studio para codificar.
- Biblioteca Aspose.PDF para .NET: asegúrese de haber instalado la biblioteca Aspose.PDF para .NET.
  -  Enlace de descarga:[Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/)
- Licencia temporal: si está probando las funciones, es útil tener una licencia temporal.
  -  Licencia temporal:[Consíguelo aquí](https://purchase.aspose.com/temporary-license/)

## Importar paquetes

Antes de comenzar a trabajar con el código, asegúrese de importar los siguientes espacios de nombres en su proyecto de C#. Estos proporcionarán las clases y los métodos necesarios para trabajar con documentos PDF y crear su tabla de contenido (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ahora que su entorno está listo y se importaron los paquetes, desglosaremos cada paso del proceso. Cubriremos cada parte del código para garantizar la claridad, de modo que pueda seguirlo fácilmente.

## Paso 1: Inicialice su documento PDF

Lo primero que debemos hacer es crear un nuevo documento PDF y agregar una página para la Tabla de Contenidos (TOC).


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: este es el directorio donde se guardará su archivo de salida.
- Document(): Inicializa un nuevo documento PDF.
- Pages.Add(): agrega una nueva página en blanco al documento, que luego contendrá su tabla de contenidos.

## Paso 2: Configurar la información y el título de la tabla de contenidos

continuación, definiremos la información de la tabla de contenidos, incluida la configuración del título que aparecerá en la parte superior de la tabla de contenidos.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: este objeto contiene toda la información sobre la tabla de contenidos.
- TextFragment: Representa el texto del título del TOC, aquí lo establecemos como "Tabla de contenido".
- FontStyle: Damos estilo al título de la tabla de contenidos estableciendo su tamaño en 20 y poniéndolo en negrita.
- tocPage.TocInfo: Asignamos la información del TOC a la página que mostrará el TOC.

## Paso 3: Ocultar los números de página en la tabla de contenidos

¡Ahora viene la parte divertida! Aquí es donde configuramos la tabla de contenidos para ocultar los números de página.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: este es el interruptor mágico que oculta los números de página. Configúrelo en`false`, y los números de página no aparecerán en la tabla de contenidos.
- FormatArrayLength: establecemos esto en 4, lo que indica que queremos definir el formato para cuatro niveles de encabezados de TOC.

## Paso 4: Personalizar el formato de la tabla de contenidos

Para agregar más estilo a su tabla de contenido, ahora definiremos el formato para diferentes niveles de encabezados.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: esta matriz controla el formato de las entradas de la tabla de contenidos. Cada índice representa un nivel de encabezado diferente.
- Margen y estilo de texto: establecemos márgenes y aplicamos estilos de fuente como negrita, cursiva y subrayado para cada nivel de encabezado.

## Paso 5: Agregar encabezados al documento

Por último, agreguemos los encabezados reales que formarán parte de la tabla de contenidos.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Encabezado y segmento de texto: representan los encabezados que aparecerán en la tabla de contenidos. Cada nivel tiene su propio encabezado.
- IsAutoSequence: Numera automáticamente los encabezados.
- IsInList: garantiza que cada encabezado aparezca en la tabla de contenidos.

## Paso 6: Guardar el documento

Una vez que todo esté configurado, guarde el documento PDF en el archivo de salida especificado.

```csharp
doc.Save(outFile);
```

¡Y eso es todo! ¡Has creado con éxito un PDF con una tabla de contenidos y los números de página están ocultos!

## Conclusión

Crear una tabla de contenido en un PDF y ocultar los números de página puede parecer complicado, pero con Aspose.PDF para .NET, es muy fácil. Siguiendo esta guía paso a paso, aprendió a personalizar el formato de la tabla de contenido, ocultar los números de página y aplicar diferentes estilos a los encabezados. Ahora puede crear archivos PDF profesionales adaptados a sus necesidades exactas.

## Preguntas frecuentes

### ¿Puedo mostrar números de página para encabezados específicos en la tabla de contenidos?
No, Aspose.PDF oculta o muestra los números de página de toda la tabla de contenidos. No es posible ocultarlos de forma selectiva para entradas específicas.

### ¿Es posible agregar más niveles al TOC?
 Sí, puedes aumentar el`FormatArrayLength` para definir más niveles de encabezados de TOC.

### ¿Cómo puedo cambiar la fuente de todas las entradas de la tabla de contenidos?
 Puede cambiar la fuente modificando el`TextState.Font` propiedad para cada nivel en el`FormatArray`.

### ¿Puedo insertar hipervínculos en la tabla de contenidos?
 Sí, puede vincular cada entrada de la tabla de contenidos a una sección específica del documento utilizando el`Heading.TocPage` propiedad.

### ¿Necesito una licencia para Aspose.PDF?
Sí, se requiere una licencia válida para el uso en producción. Puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/) Para probar las funciones.