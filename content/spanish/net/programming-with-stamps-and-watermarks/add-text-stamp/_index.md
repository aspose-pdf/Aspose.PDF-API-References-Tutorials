---
title: Agregar sello de texto en archivo PDF
linktitle: Agregar sello de texto en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo agregar un sello de texto en un archivo PDF usando Aspose.PDF para .NET con nuestra guía paso a paso y mejore las presentaciones de sus documentos.
type: docs
weight: 50
url: /es/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Introducción

En la era digital actual, los archivos PDF son un formato común para compartir y entregar documentos. Ya sea que sea un desarrollador, un creador de contenido o simplemente alguien que busca mejorar sus archivos PDF, saber cómo manipular archivos PDF mediante programación puede ser un cambio radical. Una característica ingeniosa que puede querer utilizar es la capacidad de agregar sellos de texto en sus archivos PDF. Agregar un sello de texto puede darle a sus documentos un toque profesional o transmitir información importante, como "Muestra", "Confidencial" o incluso una marca de agua.

## Prerrequisitos

Antes de comenzar con el código, hay algunos requisitos previos para garantizar que todo esté configurado correctamente. Esto es lo que necesitará:

1.  Aspose.PDF para .NET: Asegúrese de tener la biblioteca Aspose.PDF instalada en su proyecto. Si aún no lo ha hecho, puede descargarla desde el sitio web[Sitio web de Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio o IDE compatible: necesitará un entorno de desarrollo para escribir y ejecutar su código .NET. Visual Studio es la opción más común entre los desarrolladores.
3. Conocimientos básicos de C#: la familiaridad con C# y los principios de programación orientada a objetos le ayudará a comprender mejor los ejemplos.
4. Archivo PDF de muestra: debe tener un archivo PDF listo para trabajar. Puede crear un PDF básico o usar cualquier PDF existente para probar la funcionalidad.

¡Una vez que hayas resuelto estos requisitos previos, podemos pasar a la codificación!

## Importar paquetes

Ahora, importemos los paquetes necesarios. Este paso es crucial, ya que hace que las clases y los métodos de la biblioteca Aspose estén disponibles en el proyecto.

### Importar ensamblaje Aspose.PDF

Para comenzar, debe importar el espacio de nombres Aspose.PDF. En la parte superior de su archivo C#, agregue la siguiente directiva using:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Esto le permitirá acceder a clases que son esenciales para crear y manipular documentos PDF.

Ahora, entremos en el meollo del tutorial. Dividiremos el proceso en pasos claros y concisos. Cada paso te guiará a través del código para agregar un sello de texto a un archivo PDF.

## Paso 1: Configurar el directorio de documentos

En primer lugar, debe establecer el directorio en el que se almacena el documento PDF. Esto significa que su código debe saber dónde encontrar el archivo PDF que desea editar.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Explicación: Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde se encuentra su archivo PDF (`AddTextStamp.pdf`) se almacena. Esta ruta se utiliza más adelante para abrir y guardar el PDF modificado.

## Paso 2: Abra el documento PDF

 A continuación, abriremos el documento PDF utilizando el`Document` clase del espacio de nombres Aspose.PDF.

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Explicación: Aquí, estamos creando una instancia de la`Document` Clase y pasando la ruta a nuestro archivo PDF. Esto cargará el PDF para que podamos manipularlo.

## Paso 3: Crea un sello de texto

Ahora, crearemos un sello de texto que luego aplicaremos a nuestro documento PDF.

```csharp
// Crear sello de texto
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Explicación: El`TextStamp` El objeto se crea con el texto que desea mostrar. En este caso, usamos "Sello de muestra" como texto para nuestro sello.

## Paso 4: Establecer las propiedades del sello

Para personalizar el sello, podemos configurar varias propiedades, como el color de fondo, la posición y la rotación. Hagámoslo ahora:

```csharp
// Establecer si el sello es el fondo
textStamp.Background = true;

// Establecer origen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Girar sello
textStamp.Rotate = Rotation.on90;
```

Explicación:
- Antecedentes: Establecer esto en`true` significa que el sello aparecerá detrás del contenido del PDF.
- XIndent y YIndent: estas propiedades determinan la posición del sello en la página. En este ejemplo, el sello se colocará a 100 unidades de los bordes izquierdo y superior de la página.
- Rotar: esta opción rota el sello 90 grados. Puede elegir diferentes opciones de rotación según los requisitos de su diseño.

## Paso 5: Personalizar las propiedades del texto

A continuación, seamos creativos personalizando la apariencia del texto dentro de nuestro sello:

```csharp
// Establecer propiedades de texto
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Explicación:
- Fuente: Estamos utilizando la fuente Arial y la ponemos en negrita y cursiva.
- Tamaño de fuente: está establecido en 14 puntos.
- Color de primer plano: use RGB para configurar el color del texto en aguamarina. ¡Siéntase libre de cambiar el color para adaptarlo a sus necesidades de marca o diseño!

## Paso 6: Agregar sello a la página PDF

Ahora es el momento de agregar el sello a una página específica del documento PDF.

```csharp
// Añadir sello a una página específica
pdfDocument.Pages[1].AddStamp(textStamp);
```

Explicación: En este ejemplo, el sello se agrega a la primera página del PDF (las páginas tienen un índice de 1). Ajuste el número de página según sea necesario para su documento.

## Paso 7: Guardar el PDF modificado

Por último, guardemos el documento con el sello de texto recién agregado.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Explicación: Definimos una nueva ruta para el archivo de salida y luego guardamos el documento modificado. Después de guardar, la ruta se imprime en la consola, lo que confirma que la operación se realizó correctamente.

## Conclusión

¡Felicitaciones! Ha agregado con éxito un sello de texto a un archivo PDF con Aspose.PDF para .NET. Este método le permite realizar anotaciones en sus documentos de manera eficiente, mejorando tanto su profesionalismo como su facilidad de uso. Ya sea que esté agregando marcas de agua, firmas o notas simples, la biblioteca Aspose proporciona herramientas poderosas para manipular sus archivos PDF con facilidad.

## Preguntas frecuentes

### ¿Qué es un sello de texto en un PDF?
Un sello de texto es una superposición gráfica que contiene texto que se puede colocar en un documento PDF y que a menudo se utiliza para anotaciones o marcas de agua.

### ¿Puedo personalizar el sello con imágenes?
Sí, Aspose.PDF también permite agregar sellos de imagen, lo que proporciona más flexibilidad de diseño.

### ¿Qué lenguajes de programación puedo utilizar con Aspose.PDF?
Aspose.PDF se centra principalmente en .NET, pero hay versiones disponibles para otros lenguajes como Java y Python.

### ¿Cómo puedo obtener una licencia temporal para Aspose.PDF?
 Puede solicitar una licencia temporal visitando el[enlace de compra](https://purchase.aspose.com/temporary-license/) en su sitio web.

### ¿Dónde puedo encontrar soporte para Aspose.PDF?
 El soporte para Aspose.PDF está disponible en su[foro de soporte](https://forum.aspose.com/c/pdf/10).