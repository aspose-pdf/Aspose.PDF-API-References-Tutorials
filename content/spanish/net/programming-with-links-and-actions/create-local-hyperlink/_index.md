---
title: Crear hipervínculo local en un archivo PDF
linktitle: Crear hipervínculo local en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Cree fácilmente hipervínculos locales en archivos PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-links-and-actions/create-local-hyperlink/
---
La creación de hipervínculos locales en un archivo PDF le permite crear vínculos en los que se puede hacer clic y que llevan a los usuarios a otras páginas del mismo documento PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta donde desea guardar el archivo PDF resultante. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: crear una instancia de documento

 Crearemos una instancia del`Document` clase para representar nuestro documento PDF. Aquí está el código correspondiente:

```csharp
Document doc = new Document();
```

## Paso 4: agregue página y texto con hipervínculos

En este paso, agregaremos una página a nuestro documento PDF y agregaremos texto que contenga hipervínculos locales. Definiremos las páginas de destino para cada enlace. Aquí está el código correspondiente:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Paso 5: guarde el documento actualizado

 Ahora guardemos el archivo PDF actualizado usando el`Save` método de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para crear un hipervínculo local usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Agregar página a colección de páginas de archivos PDF
Page page = doc.Pages.Add();
// Crear instancia de fragmento de texto
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Crear instancia de hipervínculo local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Establecer página de destino para instancia de enlace
link.TargetPageNumber = 7;
// Establecer hipervínculo TextFragment
text.Hyperlink = link;
//Agregar texto a la colección de párrafos de la página
page.Paragraphs.Add(text);
// Crear nueva instancia de TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment debe agregarse en una página nueva
text.IsInNewPage = true;
// Crear otra instancia de hipervínculo local
link = new LocalHyperlink();
// Establecer página de destino para el segundo hipervínculo
link.TargetPageNumber = 1;
// Establecer enlace para el segundo TextFragment
text.Hyperlink = link;
// Agregar texto a la colección de párrafos del objeto de página
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Guardar documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusión

¡Enhorabuena! Ahora tiene una guía paso a paso para crear hipervínculos locales en un PDF usando Aspose.PDF para .NET. Puede utilizar este código para crear enlaces en los que se pueda hacer clic y que lleven a los usuarios a otras páginas del mismo documento.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre funciones avanzadas de hipervínculos.

### Preguntas frecuentes para crear un hipervínculo local en un archivo PDF

#### P: ¿Qué son los hipervínculos locales en un archivo PDF?

R: Los hipervínculos locales en un archivo PDF son vínculos en los que se puede hacer clic y que llevan a los usuarios a diferentes páginas dentro del mismo documento. Estos enlaces mejoran la navegación y permiten a los lectores acceder rápidamente a las secciones relevantes.

#### P: ¿Cómo pueden los hipervínculos locales beneficiar a mi documento PDF?

R: Los hipervínculos locales proporcionan una forma eficaz de conectar contenido relacionado dentro del mismo documento PDF. Mejoran la experiencia del usuario al permitir a los lectores saltar rápidamente a secciones específicas sin tener que desplazarse por todo el documento.

#### P: ¿Cómo admite Aspose.PDF para .NET la creación de hipervínculos locales?
R: Aspose.PDF para .NET ofrece soporte integral para la creación de hipervínculos locales. El tutorial paso a paso proporcionado en esta guía demuestra cómo agregar hipervínculos locales a su documento PDF usando C#.

#### P: ¿Puedo personalizar la apariencia de los hipervínculos locales?

R: Sí, puede personalizar la apariencia de los hipervínculos locales, incluido el color y el estilo del texto, para asegurarse de que coincidan con el diseño de su documento y brinden una experiencia visual consistente.

#### P: ¿Es posible crear varios hipervínculos locales dentro de una sola página PDF?

R: ¡Absolutamente! Puede crear múltiples hipervínculos locales dentro de una sola página PDF, lo que permite a los lectores saltar a varias secciones o páginas según sea necesario. Cada hipervínculo local se puede adaptar a su objetivo respectivo.

#### P: ¿Puedo vincular a secciones específicas de una página utilizando hipervínculos locales?

R: Si bien los hipervínculos locales normalmente navegan a páginas enteras, puedes crear anclajes o marcadores dentro de tu documento PDF para lograr enlaces específicos. Aspose.PDF para .NET admite varias opciones de hipervínculos.

#### P: ¿Cómo puedo verificar que mis hipervínculos locales estén funcionando correctamente?

R: Si sigue el tutorial y el código de muestra proporcionados, podrá crear con confianza hipervínculos locales funcionales. Puede probar los enlaces abriendo el documento PDF generado y haciendo clic en el texto con hipervínculo.

#### P: ¿Existe alguna limitación al utilizar hipervínculos locales?

R: Los hipervínculos locales son una forma eficaz de mejorar la navegación del documento, pero es importante garantizar que la estructura del documento siga siendo clara e intuitiva. Los hipervínculos y anclajes correctamente etiquetados contribuyen a una experiencia de usuario positiva.

#### P: ¿Puedo crear hipervínculos locales dentro de tablas o imágenes?

R: Sí, puede crear hipervínculos locales dentro de varios elementos de su documento PDF, incluidas tablas, imágenes y texto. Aspose.PDF para .NET ofrece flexibilidad para agregar hipervínculos a diferentes tipos de contenido.