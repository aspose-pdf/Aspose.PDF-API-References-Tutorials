---
title: Sellos de número de página en archivo PDF
linktitle: Sellos de número de página en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar sellos de número de página a archivos PDF usando Aspose.PDF para .NET a través de nuestra guía fácil de seguir, completa con un ejemplo de código.
type: docs
weight: 160
url: /es/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Introducción

¿Alguna vez te has encontrado luchando con un documento PDF, deseando que tuviera números de página para navegar más fácilmente? Ya seas un estudiante que comparte notas, un profesional que presenta informes o cualquier persona que maneja documentos de varias páginas, agregar números de página puede mejorar realmente la claridad de tus archivos PDF. Afortunadamente, con la poderosa biblioteca Aspose.PDF para .NET, puedes agregar sellos de números de página a tus documentos PDF con facilidad. En esta guía, te guiaremos a través de todo el proceso paso a paso, asegurándonos de que estés equipado con todo el conocimiento que necesitas. ¡Vamos a sumergirnos!

## Prerrequisitos

Antes de comenzar a agregar sellos de número de página a sus documentos PDF, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio: asegúrate de tener Visual Studio instalado en tu sistema. Aquí escribirás y ejecutarás tu código.
2. .NET Framework: Es esencial estar familiarizado con la programación C# y el marco .NET, ya que Aspose.PDF está diseñado para aplicaciones .NET.
3.  Biblioteca Aspose.PDF: Puede descargar la biblioteca Aspose.PDF desde[Comunicados de Aspose en formato PDF](https://releases.aspose.com/pdf/net/). 
4. Comprensión básica de los archivos PDF: si bien no es necesario que sea un experto, una comprensión básica de cómo funcionan los archivos PDF lo ayudará a comprender mejor el tutorial.

Una vez que hayas configurado estos requisitos previos, ¡estarás listo para comenzar a estampar esos números de página!

## Importar paquetes

Antes de comenzar a codificar, debe asegurarse de que los paquetes Aspose.PDF necesarios se importen a su proyecto. Esto es fundamental para aprovechar las funciones de la biblioteca sin problemas. A continuación, le indicamos cómo hacerlo:

### Crear un nuevo proyecto

1. Abra Visual Studio.
2.  Hacer clic en`File` >`New` >`Project`.
3.  Seleccione una plantilla adecuada para C# (por ejemplo, Aplicación de consola), asígnele un nombre y haga clic`Create`.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en el nombre del proyecto en el Explorador de soluciones.
2.  Hacer clic en`Manage NuGet Packages`.
3.  Buscar`Aspose.PDF` e instalar la última versión.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

¡Con la biblioteca lista para funcionar, comencemos a codificar!

Ahora que nuestro entorno está configurado, es momento de agregar sellos de números de página a un archivo PDF. Dividiremos este proceso en pasos claros para una mejor comprensión.

## Paso 1: Especifique el directorio del documento

Para comenzar, debes especificar el directorio donde se encuentra tu archivo PDF. Este es el punto de partida de tu proyecto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Actualizar esta ruta
```

 Explicación: Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta que lleva al directorio que contiene el archivo PDF. Esto es fundamental, ya que le indica al código dónde encontrar el archivo que desea manipular.

## Paso 2: Abra el documento

A continuación, abriremos el documento PDF existente al que queremos agregar los sellos de número de página.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Explicación: Aquí, estamos usando el`Document` Clase proporcionada por Aspose.PDF para abrir nuestro archivo PDF específico. Asegúrese de que el nombre del archivo coincida con el archivo real que tiene en su directorio.

## Paso 3: Crea un sello con el número de página

¡Ahora viene la parte divertida! Vamos a crear un sello de número de página para agregarlo a nuestro PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Explicación: El`PageNumberStamp`La clase nos permitirá crear un sello que mostrará el número de página actual con respecto al número total de páginas del documento.

## Paso 4: Configurar el sello

Ahora, deberá configurar los ajustes del sello. Aquí es donde diseña el aspecto y el comportamiento del sello.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Explicación:
- `Background = false`:Esto significa que el sello aparecerá en primer plano.
- `Format`:Aquí, estás configurando el formato para mostrar "Página X de Y", donde obtienes dinámicamente el total de páginas del documento.
- `BottomMargin`:Ajusta la distancia desde la parte inferior de la página.
- `HorizontalAlignment`:Centra el sello horizontalmente.
- `StartingNumber`:Establece cuál será el número de página inicial, normalmente 1.

## Paso 5: Establecer propiedades de texto

A continuación, puedes personalizar el aspecto del texto en el sello.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Explicación: Estos atributos configuran el tipo de fuente, el tamaño de fuente, el estilo (negrita y cursiva) y el color del texto dentro del sello para hacerlo visualmente atractivo.

## Paso 6: Agrega el sello a una página específica

Con su sello configurado, es hora de agregarlo a una página específica en su documento.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Explicación: Esta línea agrega el sello a la primera página del PDF. Puede ajustar el tamaño`Pages[1]` índice para otras páginas según sea necesario.

## Paso 7: Guardar el documento de salida

Por último, guarde el documento PDF modificado para que los cambios sean permanentes.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Explicación: Estás definiendo la ruta del archivo de salida y guardando el documento. La consola te informará que el sello se agregó correctamente y dónde se guardó el archivo.

## Conclusión

Agregar sellos de número de página a sus archivos PDF con Aspose.PDF para .NET no solo es simple, sino que también es altamente personalizable. Le mostramos paso a paso cómo crear un sello de número de página, lo que le garantiza una guía clara durante el proceso. Ahora posee los conocimientos necesarios para mejorar sus documentos PDF y hacerlos más profesionales y fáciles de usar. 

## Preguntas frecuentes

### ¿Puedo personalizar la apariencia de los números de página?  
¡Sí! Puedes cambiar la fuente, el tamaño, el color y el formato de los números de página como se muestra en la guía.

### ¿Aspose.PDF es de uso gratuito?  
 Aspose.PDF ofrece una versión de prueba gratuita, pero necesitará una licencia para un uso extensivo. Eche un vistazo a la[página de compra](https://purchase.aspose.com/buy) Para más información.

### ¿Qué pasa si tengo problemas durante la implementación?  
 Puedes visitar el[Foro de soporte de Aspose](https://forum.aspose.com/c/pdf/10) para solicitar ayuda.

### ¿Cómo puedo generar números de página automáticamente para varias páginas?  
El código de la guía calcula automáticamente el número total de páginas, lo que facilita la personalización para varias páginas.

### ¿Puedo utilizar Aspose.PDF en otros lenguajes de programación?  
Si bien esta guía se centra en .NET, Aspose tiene bibliotecas para Java, Python y más.