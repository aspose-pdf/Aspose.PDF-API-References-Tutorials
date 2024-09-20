---
title: Buscar y obtener todo el texto
linktitle: Buscar y obtener todo el texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar y obtener texto de todas las páginas de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 420
url: /es/net/programming-with-text/search-and-get-text-all/
---
## Introducción

¿Alguna vez ha necesitado extraer texto específico de un PDF pero le resultó complicado? A veces, los PDF pueden parecer contenedores cerrados, lo que dificulta obtener la información que necesita. Pero aquí tiene la buena noticia: con Aspose.PDF para .NET, puede buscar y recuperar fácilmente texto de cualquier PDF. Esta potente biblioteca proporciona todo lo que necesita para trabajar con archivos PDF en sus aplicaciones .NET, lo que hace que la extracción de texto sea muy sencilla. En este tutorial, lo guiaremos a través del proceso de búsqueda y extracción de texto de un archivo PDF con Aspose.PDF para .NET. Ya sea que esté creando una herramienta de análisis de texto o simplemente necesite automatizar la extracción de datos de informes PDF, ¡está en el lugar correcto!

## Prerrequisitos

Antes de pasar al código, asegurémonos de que tienes todo configurado:

1. Aspose.PDF para .NET: deberá descargar e instalar Aspose.PDF para .NET. Puede obtenerlo desde la página de descarga[aquí](https://releases.aspose.com/pdf/net/).
2. Entorno .NET: asegúrese de tener .NET Framework o .NET Core configurado en su máquina de desarrollo.
3. Conocimientos básicos de C##: se recomienda cierta familiaridad con C# y trabajar con proyectos .NET.
4.  Documento PDF: un archivo PDF de muestra del que extraeremos texto. En este ejemplo, utilizaremos`SearchAndGetTextFromAll.pdf`.

## Importar paquetes

Antes de escribir cualquier código, debe importar los espacios de nombres necesarios en su proyecto para trabajar con Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Estos espacios de nombres proporcionan acceso al modelo de objetos del documento PDF y nos permiten manipular texto dentro del archivo.

Dividamos el proceso en pasos simples para que puedas seguirlo fácilmente.

## Paso 1: Establezca el directorio del documento

Lo primero es lo primero: debes especificar la ruta del directorio donde se encuentra tu PDF. Esto ayuda a la aplicación a localizar el archivo del que extraerás el texto.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  El`dataDir` La variable debe apuntar al directorio donde se encuentra su`SearchAndGetTextFromAll.pdf` El archivo se almacena.
-  Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual en su máquina.

## Paso 2: Abra el documento PDF

 continuación, abriremos el documento PDF usando Aspose.PDF.`Document` objeto.

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Creamos una nueva instancia del`Document` clase pasando la ruta completa del archivo PDF.
- Esto cargará el PDF en la memoria, dejándolo listo para su procesamiento.

## Paso 3: Crea un absorbente de texto

 El`TextFragmentAbsorber` El objeto se utiliza para buscar texto específico dentro del PDF. En este caso, buscaremos la palabra "texto".

```csharp
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda ingresada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  El`TextFragmentAbsorber` se inicializa con la cadena`"text"`Esto significa que buscará cualquier ocurrencia de la palabra “texto” dentro del documento PDF.

## Paso 4: Acepte el Absorbedor para todas las páginas

Ahora, le indicaremos al documento PDF que acepte el absorbedor y busque el texto en todas sus páginas.

```csharp
// Acepta el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  El`Accept` El método se aplica a las páginas del documento. Esto buscará el texto especificado en todas las páginas.

## Paso 5: Extraer fragmentos de texto

Una vez que el absorbedor ha escaneado el documento, podemos recuperar los fragmentos de texto extraídos.

```csharp
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  El`TextFragments` propiedad de la`TextFragmentAbsorber` devuelve una colección de todos los fragmentos de texto que coinciden con el término de búsqueda.

## Paso 6: Recorrer los fragmentos de texto

Ahora que tenemos la colección de fragmentos de texto, los recorreremos y extraeremos los detalles.

```csharp
// Recorrer los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  El`foreach` El bucle se repite en cada uno de ellos`TextFragment` En la colección.
- Imprimimos varias propiedades de cada fragmento, como el texto real, su posición en la página, detalles de la fuente y tamaño de la fuente.
-  El`XIndent` y`YIndent` Las propiedades dan las coordenadas exactas del fragmento de texto dentro del PDF.

## Conclusión

¡Y ahí lo tienes! Con solo unas pocas líneas de código, hemos buscado y extraído texto de un PDF con éxito usando Aspose.PDF para .NET. La flexibilidad de Aspose.PDF te permite manipular archivos PDF de muchas maneras, lo que lo convierte en una excelente opción para desarrolladores que necesitan soluciones PDF sólidas en entornos .NET. Puedes ampliar fácilmente este ejemplo para buscar otras palabras, extraer más detalles o incluso manipular el contenido del PDF según tus necesidades. Esperamos que esta guía te haya proporcionado un enfoque claro y sencillo para trabajar con archivos PDF. ¡Anímate a probarlo con tus propios archivos PDF!

## Preguntas frecuentes

### ¿Puedo buscar varias palabras a la vez?  
 Sí, puedes modificar el`TextFragmentAbsorber` para buscar múltiples frases ajustando la cadena de búsqueda en consecuencia.

### ¿Qué pasa si el texto ocupa varias líneas?  
Aspose.PDF seguirá reconociendo y extrayendo texto incluso si ocupa varias líneas. Puede gestionar estos fragmentos individualmente.

### ¿Cómo guardo el texto extraído en un archivo?  
 Puede escribir el texto extraído en un archivo mediante operaciones de E/S de archivos estándar de C#, como`StreamWriter`.

### ¿Aspose.PDF admite la extracción de texto de archivos PDF escaneados?  
Aspose.PDF no admite OCR. Para los archivos PDF escaneados, necesitará una herramienta de OCR para reconocer el texto.

### ¿Cómo manejo los archivos PDF cifrados?  
Si su PDF está protegido con contraseña, puede desbloquearlo usando Aspose.PDF proporcionando la contraseña al cargar el documento.