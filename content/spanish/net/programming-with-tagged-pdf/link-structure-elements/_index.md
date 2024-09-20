---
title: Elementos de la estructura de enlaces
linktitle: Elementos de la estructura de enlaces
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear elementos de estructura de vínculos en un PDF con Aspose.PDF para .NET. Guía paso a paso para agregar vínculos accesibles, imágenes y validación de cumplimiento.
type: docs
weight: 120
url: /es/net/programming-with-tagged-pdf/link-structure-elements/
---
## Introducción

La creación y gestión de elementos de estructura de enlaces dentro de un PDF puede ser crucial para documentos que requieren accesibilidad y una navegación fluida. En este tutorial, le explicaremos cómo hacerlo con Aspose.PDF para .NET. Si no está familiarizado con Aspose.PDF o con la manipulación de PDF en general, no se preocupe. Le explicaré cada paso en detalle para que pueda seguirlo fácilmente.

## Prerrequisitos  

Antes de empezar a codificar, aclaremos algunos puntos. Estos son los requisitos básicos para garantizar una experiencia de desarrollo fluida.

1.  Aspose.PDF para .NET: Puede descargar la última versión[aquí](https://releases.aspose.com/pdf/net/).
2. Entorno de desarrollo .NET: ya sea Visual Studio o cualquier IDE compatible con .NET, téngalo instalado y listo.
3.  Licencia de Aspose: Puede utilizar la versión de prueba gratuita de Aspose.PDF[aquí](https://releases.aspose.com/) o adquirir una[licencia temporal](https://purchase.aspose.com/temporary-license/).
4. Conocimientos básicos de C#: Trabajaremos con algo de código C#, por lo que comprender los fundamentos hará que las cosas sean mucho más fáciles.

## Importar paquetes

Necesitará importar algunos paquetes antes de escribir el código para los elementos de la estructura de enlaces. Comience por hacer referencia a las bibliotecas Aspose.PDF necesarias en su proyecto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Estas importaciones nos permiten trabajar con documentos PDF, agregar etiquetas y administrar elementos de estructura.

Ahora crearemos un documento PDF con diferentes tipos de estructuras de enlaces y desglosaremos cada paso para ayudarle a comprender el proceso a fondo.

## Paso 1: Inicializar el documento  

Comencemos creando un nuevo documento PDF y configurando contenido etiquetado para accesibilidad.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Crear un nuevo documento PDF
Document document = new Document(); 

// Recuperar la interfaz TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Aquí, estamos inicializando el`Document` objeto, que representa nuestro archivo PDF. También recuperamos el`TaggedContent` interfaz, permitiéndonos agregar elementos de estructura como párrafos, enlaces e imágenes.

## Paso 2: Establezca el título y el idioma  

Cada PDF debe tener un título y una configuración de idioma, especialmente si su objetivo es cumplir con los estándares PDF/UA.

```csharp
// Establecer el título y el idioma del documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Este paso garantiza que su PDF tenga un título significativo y establece el idioma en inglés (`en-US`). Esto es fundamental para la accesibilidad y garantiza que los lectores de pantalla u otras tecnologías de asistencia puedan interpretar su documento correctamente.

## Paso 3: Crear y añadir párrafos  

En este paso, agregaremos párrafos para contener nuestros elementos de enlace.

```csharp
// Crear el elemento raíz
StructureElement rootElement = taggedContent.RootElement;

// Crea un párrafo y agrégalo al elemento raíz
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Creamos un elemento de estructura raíz, que es esencialmente el contenedor de nivel superior para todos los demás elementos. Luego creamos un párrafo (`p1`) y añádelo al elemento raíz.

## Paso 4: Agregar un enlace simple  

Ahora agreguemos un hipervínculo básico que apunte a Google.

```csharp
// Crea un elemento de enlace y agrégalo al párrafo
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Establecer hipervínculo y texto para el enlace
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
En este paso, creamos un elemento de enlace, configuramos su hipervínculo como "http://google.com" y proporcionamos texto ("Google") para el enlace. También agregamos una descripción alternativa para garantizar la accesibilidad.

## Paso 5: Agregar un enlace con tramos  

También podemos crear enlaces con diferentes tramos de texto.

```csharp
// Crea otro párrafo
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Crear un enlace con un elemento span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Aquí, utilizamos un elemento span para encerrar parte del texto dentro del enlace, lo que nos permite personalizar cómo aparecen ciertas partes del enlace.

## Paso 6: Enlace multilínea  

¿Qué pasa si el texto del enlace es demasiado largo? No te preocupes, puedes dividirlo en varias líneas.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
En este caso, creamos un enlace de varias líneas simplemente estableciendo un valor de texto largo, y el texto se ajustará automáticamente a lo largo de varias líneas.

## Paso 7: Agrega una imagen al enlace  

Por último, también puedes agregar imágenes dentro de un enlace.

```csharp
// Crear un nuevo párrafo y elemento de enlace
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Añade una imagen al enlace
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Este paso demuestra cómo puedes mejorar tus enlaces con una imagen. En este caso, agregamos un ícono de Google dentro del enlace. También garantizamos la accesibilidad configurando un texto alternativo para la imagen.

## Paso 8: Validar el PDF para comprobar su conformidad  

Si su objetivo es cumplir con los estándares de accesibilidad PDF/UA, es una buena práctica validar su documento.

```csharp
// Guardar el documento PDF
document.Save(outFile);

// Validar el documento para la conformidad con PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Guardamos el documento y lo validamos según el estándar PDF/UA, que garantiza que el PDF cumple con los requisitos de accesibilidad.

## Conclusión  

En este tutorial, explicamos cómo crear documentos PDF estructurados con Aspose.PDF para .NET. Desde la incorporación de hipervínculos básicos hasta estructuras más complejas como enlaces de varias líneas e incluso imágenes, esta guía proporciona una base sólida para manipular elementos de vínculo en sus archivos PDF. Con el beneficio adicional de la compatibilidad con PDF/UA, ahora está equipado para crear archivos PDF accesibles y navegables.

## Preguntas frecuentes

### ¿Puedo agregar estructuras más complejas como tablas dentro de enlaces?  
No, los enlaces son principalmente para texto e imágenes, pero puedes incrustar elementos complejos cerca.

### ¿Es obligatoria la validación PDF/UA?  
No siempre, pero es muy recomendable si te preocupa la accesibilidad.

### ¿Qué sucede si la ruta del archivo de imagen es incorrecta?  
El documento no mostrará la imagen y podría generar un error durante la representación.

### ¿Puedo darle estilo al texto dentro del enlace?  
Sí, puedes aplicar estilos de texto utilizando los elementos span.

### ¿Es posible crear enlaces a documentos internos?  
¡Por supuesto! Puedes incluir enlaces a secciones específicas dentro del mismo documento.