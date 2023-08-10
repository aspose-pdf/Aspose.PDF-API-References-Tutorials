---
title: Crear hipervínculo local en archivo PDF
linktitle: Crear hipervínculo local en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente hipervínculos locales en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-links-and-actions/create-local-hyperlink/
---
La creación de hipervínculos locales en un archivo PDF le permite crear vínculos en los que se puede hacer clic que llevan a los usuarios a otras páginas en el mismo documento PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: Importar bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta donde desea guardar el archivo PDF resultante. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Crear una instancia de Documento

 Vamos a crear una instancia de la`Document` class para representar nuestro documento PDF. Aquí está el código correspondiente:

```csharp
Document doc = new Document();
```

## Paso 4: Agregar página y texto con hipervínculos

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

## Paso 5: Guarde el documento actualizado

 Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para crear un hipervínculo local con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
Page page = doc.Pages.Add();
// Crear instancia de fragmento de texto
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Crear una instancia de hipervínculo local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Establecer página de destino para instancia de enlace
link.TargetPageNumber = 7;
// Establecer hipervínculo TextFragment
text.Hyperlink = link;
//Agregar texto a la colección de párrafos de la página
page.Paragraphs.Add(text);
// Crear nueva instancia de TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment debe agregarse sobre la nueva página
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

¡Felicidades! Ahora tiene una guía paso a paso para crear hipervínculos locales en un PDF usando Aspose.PDF para .NET. Puede usar este código para crear enlaces en los que se puede hacer clic que lleven a los usuarios a otras páginas en el mismo documento.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de hipervínculos.

### Preguntas frecuentes para crear un hipervínculo local en un archivo PDF

#### P: ¿Qué son los hipervínculos locales en un archivo PDF?

R: Los hipervínculos locales en un archivo PDF son enlaces en los que se puede hacer clic que llevan a los usuarios a diferentes páginas dentro del mismo documento. Estos enlaces mejoran la navegación y permiten a los lectores acceder rápidamente a las secciones relevantes.

#### P: ¿Cómo pueden los hipervínculos locales beneficiar a mi documento PDF?

R: Los hipervínculos locales brindan una manera eficiente de conectar contenido relacionado dentro del mismo documento PDF. Mejoran la experiencia del usuario al permitir que los lectores salten rápidamente a secciones específicas sin tener que desplazarse por todo el documento.

#### P: ¿Cómo admite Aspose.PDF para .NET la creación de hipervínculos locales?
R: Aspose.PDF para .NET ofrece soporte completo para crear hipervínculos locales. El tutorial paso a paso proporcionado en esta guía demuestra cómo agregar hipervínculos locales a su documento PDF usando C#.

#### P: ¿Puedo personalizar la apariencia de los hipervínculos locales?

R: Sí, puede personalizar la apariencia de los hipervínculos locales, incluidos el color y el estilo del texto, para asegurarse de que coincidan con el diseño de su documento y brinden una experiencia visual uniforme.

#### P: ¿Es posible crear varios hipervínculos locales dentro de una sola página PDF?

R: ¡Absolutamente! Puede crear varios hipervínculos locales dentro de una sola página PDF, lo que permite a los lectores saltar a varias secciones o páginas según sea necesario. Cada hipervínculo local se puede adaptar a su objetivo respectivo.

#### P: ¿Puedo vincular a secciones específicas de una página usando hipervínculos locales?

R: Si bien los hipervínculos locales generalmente navegan a páginas enteras, puede crear anclas o marcadores dentro de su documento PDF para lograr enlaces específicos. Aspose.PDF para .NET admite varias opciones de hipervínculos.

#### P: ¿Cómo puedo verificar que mis hipervínculos locales funcionan correctamente?

R: Al seguir el tutorial y el código de muestra proporcionado, puede crear con confianza hipervínculos locales funcionales. Puede probar los enlaces abriendo el documento PDF generado y haciendo clic en el texto del hipervínculo.

#### P: ¿Existen limitaciones al usar hipervínculos locales?

R: Los hipervínculos locales son una forma eficaz de mejorar la navegación por el documento, pero es importante asegurarse de que la estructura del documento siga siendo clara e intuitiva. Los hipervínculos y anclas correctamente etiquetados contribuyen a una experiencia de usuario positiva.

#### P: ¿Puedo crear hipervínculos locales dentro de tablas o imágenes?

R: Sí, puede crear hipervínculos locales dentro de varios elementos de su documento PDF, incluidas tablas, imágenes y texto. Aspose.PDF para .NET ofrece flexibilidad para agregar hipervínculos a diferentes tipos de contenido.