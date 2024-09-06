---
title: Crear enlace de documento
linktitle: Crear enlace de documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente enlaces a otros documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-links-and-actions/create-document-link/
---
Al vincular a otro documento en un archivo PDF, podrá crear enlaces en los que se puede hacer clic y que redirigen a los usuarios a otros documentos PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: Importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Esta es la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: Establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un vínculo a otro documento. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir el enlace a otro documento utilizando el siguiente código:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Paso 4: Crea el enlace a otro documento

 En este paso, crearemos el enlace a otro documento utilizando el`LinkAnnotation` Anotación. Especificaremos las coordenadas y el área del enlace, así como la acción de navegación a un documento externo. A continuación el código correspondiente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Paso 5: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` método de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Código fuente de muestra para crear un vínculo a un documento mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Crear enlace
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusión

¡Felicitaciones! Ahora tiene una guía paso a paso para crear vínculos a otros documentos con Aspose.PDF para .NET. Puede usar este código para crear vínculos en los que se puede hacer clic en sus archivos PDF y redirigir a los usuarios a otros documentos.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de los enlaces interactivos.

### Preguntas frecuentes sobre el enlace para crear un documento

#### P: ¿Qué son los enlaces de documentos en archivos PDF?

A: Los enlaces a documentos en archivos PDF son enlaces en los que se puede hacer clic que dirigen a los usuarios a otros documentos PDF. Estos enlaces mejoran la navegación al proporcionar una forma eficiente de conectar contenido relacionado y facilitar una experiencia de lectura fluida.

#### P: ¿Cómo puedo beneficiarme de la creación de enlaces a documentos?

A: La creación de vínculos entre documentos le permite establecer conexiones entre distintas secciones o temas dentro de sus documentos PDF. Esta función permite a los usuarios acceder a información complementaria o materiales relacionados con facilidad.

#### P: ¿Cómo admite Aspose.PDF para .NET la creación de enlaces a documentos?

A: Aspose.PDF para .NET simplifica el proceso de creación de vínculos a documentos al proporcionar un conjunto completo de API. El tutorial paso a paso que se describe en esta guía demuestra cómo agregar vínculos a documentos a sus archivos PDF.

#### P: ¿Puedo personalizar la apariencia de los enlaces de los documentos?

R: ¡Por supuesto! Aspose.PDF para .NET ofrece opciones de personalización para la apariencia de los vínculos de los documentos, incluidos el color, el estilo y los efectos al pasar el mouse sobre ellos. Puede personalizar la apariencia para que coincida con el diseño de su documento.

#### P: ¿Es posible vincular secciones o páginas específicas dentro de otro documento?

R: Sí, puede crear vínculos que dirijan a los usuarios a páginas o secciones específicas dentro de otro documento PDF. Aspose.PDF para .NET ofrece la flexibilidad de definir la ubicación de destino dentro del documento vinculado.

#### P: ¿Cómo puedo asegurarme de que los enlaces a mis documentos funcionen?

R: Si sigue el tutorial y el código de muestra que se proporcionan, podrá crear con confianza vínculos funcionales a documentos. Puede probar los vínculos abriendo el documento PDF generado y haciendo clic en ellos.

#### P: ¿Puedo crear varios enlaces a documentos dentro de un solo archivo PDF?

 R: ¡Por supuesto! Puedes crear múltiples vínculos a documentos dentro de un solo documento PDF utilizando el`LinkAnnotation` Anotación. Esto le permite proporcionar a los usuarios acceso a varios documentos relacionados desde diferentes secciones.

#### P: ¿Existen limitaciones al vincularse a documentos externos?

R: Al vincular documentos externos, asegúrese de que los documentos vinculados sean accesibles y se encuentren en las rutas especificadas. También es importante tener en cuenta los permisos de usuario y la compatibilidad de los documentos vinculados.

#### P: ¿Puedo vincularme a documentos almacenados en la web o repositorios en línea?

R: Si bien este tutorial se centra en la vinculación a documentos locales, Aspose.PDF para .NET también admite la vinculación a URL web o repositorios en línea. Puede adaptar el código proporcionado para crear vínculos a documentos basados en la web.