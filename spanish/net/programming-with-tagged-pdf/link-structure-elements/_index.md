---
title: Elementos de estructura de enlace
linktitle: Elementos de estructura de enlace
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para usar elementos de estructura de enlace con Aspose.PDF para .NET. Cree hipervínculos en sus documentos PDF.
type: docs
weight: 120
url: /es/net/programming-with-tagged-pdf/link-structure-elements/
---
En esta guía paso a paso, le mostraremos cómo usar elementos de estructura de enlace con Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear y manipular documentos PDF mediante programación. Los elementos de la estructura de enlaces le permiten agregar hipervínculos a su documento PDF, lo que permite a los usuarios hacer clic en los enlaces y navegar a los recursos en línea.

Profundicemos en el código y aprendamos a usar elementos de estructura de enlace con Aspose.PDF para .NET.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Un conocimiento básico del lenguaje de programación C#.

## Paso 1: Configuración del entorno

Para comenzar, abra su entorno de desarrollo C# y cree un nuevo proyecto. Asegúrese de haber agregado una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Paso 2: Crear el documento

 El primer paso es crear un nuevo documento PDF usando el`Document` clase.

```csharp
// Crear el documento PDF
Document document = new Document();
```

## Paso 3: Trabajar con contenido etiquetado

Luego obtenemos el contenido etiquetado del documento para trabajar.

```csharp
// Obtener el contenido etiquetado del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Paso 4: establecer el título y el idioma del documento

Ahora podemos configurar el título del documento y el idioma.

```csharp
// Definir el título del documento y el idioma
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Paso 5: Agregar elementos de estructura de enlace

Ahora agreguemos elementos de estructura de enlace a nuestro documento. Crearemos diferentes tipos de enlaces, incluidos enlaces de texto simple, enlaces de imágenes y enlaces de varias líneas.
```csharp
// Obtener el elemento de estructura raíz (elemento de estructura del documento)
StructureElement rootElement = taggedContent.RootElement;

// Agregar un párrafo con un hipervínculo
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Agregue un párrafo con un hipervínculo que contenga texto enriquecido
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Agregue un párrafo con un hipervínculo que contenga texto parcialmente formateado
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Agregar un párrafo con un hipervínculo de varias líneas
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Agregue un párrafo con un hipervínculo que contenga una imagen
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Paso 6: Guarde el documento PDF etiquetado

Finalmente, guardamos el documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document. Save(outFile);
```

## Paso 7: Comprobar el cumplimiento de PDF/UA

 También podemos verificar el documento para el cumplimiento de PDF/UA usando el`Validate` metodo de la`Document` clase.

```csharp
// Compruebe el cumplimiento de PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Ejemplo de código fuente para elementos de estructura de enlace mediante Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Documento de creación y obtención de contenido PDF etiquetado
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Configuración del título y el idioma natural del documento
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Obtención del elemento de estructura raíz (elemento de estructura del documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Guardar documento PDF etiquetado
document.Save(outFile);

// Comprobación del cumplimiento de PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusión

¡Felicidades! Ha aprendido a utilizar elementos de estructura de enlaces con Aspose.PDF para .NET. Ahora puede crear hipervínculos en sus documentos PDF, lo que permite a los usuarios navegar a los recursos en línea. Experimente y explore más características de Aspose.PDF para crear documentos PDF interactivos y enriquecidos.

### Preguntas frecuentes

#### P: ¿Qué son los elementos de la estructura de enlaces en un documento PDF y cómo mejoran la interactividad del documento?

R: Los elementos de la estructura de vínculos en un documento PDF se utilizan para crear hipervínculos que permiten a los usuarios navegar a recursos en línea o ubicaciones específicas dentro del documento. Estos elementos mejoran la interactividad al proporcionar enlaces en los que se puede hacer clic que permiten a los usuarios acceder a contenido relacionado o sitios web externos.

#### P: ¿Cómo pueden ser beneficiosos los elementos de la estructura de enlaces en un documento PDF?

R: Los elementos de la estructura de enlaces mejoran la experiencia del usuario al hacer que el documento PDF sea interactivo. Proporcionan acceso rápido a información adicional, contenido relacionado, sitios web externos o secciones específicas dentro del documento, mejorando la navegación y facilitando la recuperación de información.

#### P: ¿Puedo crear diferentes tipos de hipervínculos utilizando elementos de estructura de vínculos en Aspose.PDF para .NET?

R: Sí, puede crear varios tipos de hipervínculos utilizando elementos de estructura de enlaces. Aspose.PDF para .NET le permite crear hipervínculos con texto sin formato, texto enriquecido, imágenes y descripciones de varias líneas, lo que ofrece versatilidad en la forma de vincular contenido externo o ubicaciones dentro del documento.

#### P: ¿Cómo configuro e inicializo los elementos de la estructura de enlaces en un documento PDF usando Aspose.PDF para .NET?

 R: Para usar elementos de estructura de enlace, primero necesita crear un nuevo documento PDF usando el`Document` clase. Luego, obtenga el contenido etiquetado usando el`TaggedContent`propiedad del documento. Desde allí, puede crear y personalizar elementos de estructura de enlace y agregarlos al elemento de estructura raíz.

#### P: ¿Cómo puedo crear un hipervínculo de texto simple utilizando elementos de estructura de vínculo?
 R: Puede crear un hipervínculo de texto simple creando un`LinkElement` y estableciendo su`Hyperlink` propiedad a un`WebHyperlink` con la URL a la que desea enlazar. También puede configurar el texto de visualización del enlace usando el`SetText` método.

#### P: ¿Es posible crear hipervínculos con imágenes usando elementos de estructura de enlaces?

 R: Sí, puede crear hipervínculos con imágenes usando elementos de estructura de enlaces. Crearías un`LinkElement` y luego agregar un`FigureElement` con una imagen a la misma. Esto le permite crear un hipervínculo basado en imágenes.

#### P: ¿Cómo puedo asegurarme de que mi documento PDF con hipervínculos cumple con el estándar de accesibilidad PDF/UA?

 R: Aspose.PDF para .NET brinda la capacidad de validar el cumplimiento de su documento PDF con el estándar PDF/UA utilizando el`Validate` metodo de la`Document`clase. Esto garantiza que los hipervínculos del documento sean accesibles para los usuarios con discapacidades.

#### P: ¿Cuáles son las descripciones alternativas de los elementos de la estructura de enlaces y por qué son importantes?

R: Las descripciones alternativas (texto alternativo) para los elementos de la estructura del enlace proporcionan descripciones textuales de los hipervínculos. Estas descripciones son esenciales para la accesibilidad, ya que permiten a los usuarios con discapacidad visual comprender el propósito del enlace y su destino.

#### P: ¿Puedo personalizar la apariencia y el comportamiento de los hipervínculos creados con elementos de estructura de vínculos?

R: Si bien los elementos de la estructura del vínculo se centran principalmente en la creación de hipervínculos, puede personalizar aún más la apariencia y el comportamiento de los hipervínculos utilizando otras funciones que ofrece Aspose.PDF para .NET. Esto incluye especificar colores, estilos y acciones de enlace.

#### P: ¿Cómo contribuyen los elementos de la estructura de enlaces a hacer que los documentos PDF sean más interactivos y fáciles de usar?

R: Los elementos de la estructura de enlaces transforman los documentos PDF estáticos en experiencias interactivas al agregar hipervínculos en los que se puede hacer clic. Esta interactividad mejora la participación del usuario, permite una navegación fluida entre contenido relacionado y mejora la usabilidad general del documento.