---
title: Crear hipervínculo local en archivo PDF
linktitle: Crear hipervínculo local en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear hipervínculos locales en archivos PDF usando Aspose.PDF para .NET sin esfuerzo con nuestra guía paso a paso.
type: docs
weight: 40
url: /es/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Introducción

En esta guía, le explicaremos el proceso de creación de hipervínculos locales en un archivo PDF con Aspose.PDF para .NET. Desglosaremos cada paso con claridad, para garantizar que, incluso si es nuevo en el mundo de la manipulación de PDF, pueda seguirlo sin esfuerzo.

## Prerrequisitos

Antes de sumergirnos de lleno en el código, asegurémonos de que tienes todo lo que necesitas:

1.  Visual Studio: lo necesitarás para desarrollar tus aplicaciones .NET. Descárgalo desde[sitio web](https://visualstudio.microsoft.com/).
2.  Aspose.PDF para .NET: Puede descargar esta biblioteca a través de[enlace de descarga aquí](https://releases.aspose.com/pdf/net/)Viene con un amplio conjunto de funciones para la manipulación de PDF.
3. Conocimientos básicos de C#: Un poco de familiaridad con la programación en C# será de ayuda, pero no te preocupes; repasaremos el código línea por línea.
4.  .NET Framework: Asegúrate de tener instalado .NET Framework en tu equipo. Puedes consultar los requisitos en Aspose.PDF[documentación](https://reference.aspose.com/pdf/net/).

¡Con estos requisitos previos configurados, está listo para aprender a crear hipervínculos locales en sus documentos PDF!

## Importar paquetes

Ahora que ya está todo preparado, es momento de importar los paquetes necesarios en su proyecto de C#. La biblioteca Aspose.PDF contiene todas las clases que necesitamos. A continuación, le indicamos cómo hacerlo:

### Abra su proyecto

Abra su proyecto .NET existente o cree uno nuevo en Visual Studio. Si está comenzando desde cero, seleccione “Crear un nuevo proyecto” en la pantalla de inicio.

### Agregar referencia a Aspose.PDF

 Haga clic con el botón derecho en "Dependencias" en la carpeta de su proyecto en el Explorador de soluciones. Seleccione "Administrar paquetes NuGet" y luego busque`Aspose.PDF`. Instale la última versión disponible. Esto le proporcionará todas las herramientas que necesita para crear y manipular archivos PDF.

### Importar espacios de nombres

En la parte superior de su archivo .cs, agregue directivas de uso para la biblioteca Aspose.PDF de la siguiente manera:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

De esta manera podrás acceder a las funcionalidades de la biblioteca.

Vamos a dividir el proceso de creación de hipervínculos locales en pasos sencillos. Explicaremos cada paso en detalle para que comprenda la lógica detrás de cada uno.

## Paso 1: Configurar la instancia del documento

En este paso, creará una nueva instancia de la clase Documento, que representa el archivo PDF con el que trabajará.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Establezca su directorio de documentos
Document doc = new Document(); // Crear instancia de documento
```
 El`dataDir` La variable es donde se ubicará el PDF recién creado. Deberá reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual en su sistema.`Document` La clase crea un nuevo documento PDF donde podemos agregar páginas y enlaces.

## Paso 2: Agregar una página al documento

A continuación, agregará una página a su documento PDF. 

```csharp
Page page = doc.Pages.Add(); // Agregar página a la colección de páginas
```
 El`Pages.Add()` El método agrega una nueva página al documento. Aquí es donde se ubicará todo el contenido.

## Paso 3: Crear un fragmento de texto

Ahora, vamos a crear un fragmento de texto que actuará como un enlace en el que se puede hacer clic.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 El`TextFragment` Representa un segmento de texto en el PDF. Aquí, estamos creando un enlace que indica a los usuarios que los llevará a la página 7.

## Paso 4: Crear un hipervínculo local

¡Aquí es donde ocurre la magia! Debes crear un hipervínculo local que le indique al fragmento de texto a dónde apuntar.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Crear hipervínculo local
link.TargetPageNumber = 7; //Establecer la página de destino para la instancia de enlace
text.Hyperlink = link; // Establecer hipervínculo TextFragment
```
 El`LocalHyperlink` La clase es lo que nos permite señalar otras páginas en el mismo documento. Al configurar`TargetPageNumber` En el paso 7, le indicas al hipervínculo que salte a esa página específica cuando se hace clic.

## Paso 5: Agrega el fragmento de texto a la página

Después de configurar el hipervínculo, es hora de agregar nuestro fragmento de texto a la página que creamos.

```csharp
page.Paragraphs.Add(text); // Agregar texto a la colección de párrafos de la página
```
Esta línea agrega el texto en el que se puede hacer clic a la colección de párrafos de la página.

## Paso 6: Crea otro fragmento de texto (opcional)

Agreguemos otro hipervínculo para regresar a la página 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Crear nuevo fragmento de texto
text.IsInNewPage = true; // Agregarlo a una nueva página
```
 Creando un nuevo`TextFragment` Para el segundo enlace, establecemos`IsInNewPage` a verdadero, indicando que este texto aparecerá en una nueva página.

## Paso 7: Configurar el segundo hipervínculo local

Al igual que antes, creará otro hipervínculo local para la página 1.

```csharp
link = new LocalHyperlink(); // Crear otra instancia de hipervínculo local
link.TargetPageNumber = 1; //Establecer página de destino para el segundo hipervínculo
text.Hyperlink = link; // Establecer enlace para el segundo TextFragment
```
Este hipervínculo apunta a la página 1, lo que permite a los usuarios volver atrás cuando llegan a la segunda página.

## Paso 8: Agrega el segundo fragmento de texto a la nueva página

Ahora, agreguemos este texto a su página.

```csharp
page.Paragraphs.Add(text); // Agregar texto a la colección de párrafos del objeto de página
```
De manera similar al paso 5, esta línea agrega el nuevo texto del hipervínculo a la página recién creada.

## Paso 9: Guardar el documento

¡Por fin ha llegado el momento de guardar todo tu arduo trabajo! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Especificar el nombre del archivo de salida
doc.Save(dataDir); // Guardar documento actualizado
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Esto combina la ruta de su directorio con el nombre del archivo.`Save()` ¡El método guarda su documento y un mensaje de confirmación le permite saber que todo salió bien!

## Conclusión

Crear hipervínculos locales en archivos PDF con Aspose.PDF para .NET no es solo un truco genial, es una característica práctica que mejora la navegación y la experiencia del usuario. Ahora está equipado con el conocimiento para indicarle a sus lectores directamente la información que necesitan. Recuerde nuestra analogía inicial: no más almas perdidas vagando por páginas interminables.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF mediante programación utilizando el marco .NET.

### ¿Puedo crear hipervínculos a páginas web externas?
Sí, Aspose.PDF también admite la creación de hipervínculos a URL externas además de hipervínculos locales dentro del PDF.

### ¿Existe una prueba gratuita de Aspose.PDF?
 ¡Por supuesto! Puedes acceder a la prueba gratuita desde el[sitio](https://releases.aspose.com/).

### ¿Qué lenguajes de programación admite Aspose?
Aspose ofrece bibliotecas para varios lenguajes de programación, incluidos Java, C++, y Python, entre otros.

### ¿Cómo puedo obtener soporte para los productos Aspose?
 Puede buscar ayuda a través de[Foro de Aspose](https://forum.aspose.com/c/pdf/10).