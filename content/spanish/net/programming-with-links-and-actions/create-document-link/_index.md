---
title: Crear enlace de documento
linktitle: Crear enlace de documento
second_title: Aspose.PDF para referencia de API .NET
description: Cree fácilmente enlaces a otros documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-links-and-actions/create-document-link/
---
Vincular a otro documento en un archivo PDF le permite crear vínculos en los que se puede hacer clic y que redirigen a los usuarios a otros documentos PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establezca la ruta a la carpeta de documentos

En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un enlace a otro documento. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: abre el documento PDF

Ahora abriremos el documento PDF al que queremos agregar el enlace a otro documento usando el siguiente código:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Paso 4: crea el enlace a otro documento

 En este paso, crearemos el enlace a otro documento usando el`LinkAnnotation` anotación. Especificaremos las coordenadas y zona del enlace, así como la acción de navegación a un documento externo. Aquí está el código correspondiente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Paso 5: guarde el archivo actualizado

 Ahora guardemos el archivo PDF actualizado usando el`Save` método de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Código fuente de muestra para Crear enlace de documento usando Aspose.PDF para .NET 
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

¡Enhorabuena! Ahora tiene una guía paso a paso para vincular otros documentos con Aspose.PDF para .NET. Puede utilizar este código para crear enlaces en los que se puede hacer clic en sus archivos PDF, redirigiendo a los usuarios a otros documentos.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de los enlaces interactivos.

### Preguntas frecuentes para crear un enlace a un documento

#### P: ¿Qué son los enlaces a documentos en archivos PDF?

R: Los enlaces a documentos en archivos PDF son enlaces en los que se puede hacer clic y que dirigen a los usuarios a otros documentos PDF. Estos enlaces mejoran la navegación al proporcionar una manera eficiente de conectar contenido relacionado y facilitar una experiencia de lectura fluida.

#### P: ¿Cómo puedo beneficiarme de la creación de enlaces a documentos?

R: La creación de enlaces a documentos le permite establecer conexiones entre diferentes secciones o temas dentro de sus documentos PDF. Esta función permite a los usuarios acceder a información complementaria o materiales relacionados con facilidad.

#### P: ¿Cómo admite Aspose.PDF para .NET la creación de enlaces de documentos?

R: Aspose.PDF para .NET simplifica el proceso de creación de enlaces de documentos al proporcionar un conjunto completo de API. El tutorial paso a paso descrito en esta guía demuestra cómo agregar enlaces de documentos a sus archivos PDF.

#### P: ¿Puedo personalizar la apariencia de los enlaces de los documentos?

R: ¡Absolutamente! Aspose.PDF para .NET ofrece opciones de personalización para la apariencia de los enlaces de documentos, incluidos color, estilo y efectos de desplazamiento. Puede personalizar la apariencia para que coincida con el diseño de su documento.

#### P: ¿Es posible vincular a secciones o páginas específicas dentro de otro documento?

R: Sí, puede crear enlaces que lleven a los usuarios a páginas o secciones específicas dentro de otro documento PDF. Aspose.PDF para .NET proporciona la flexibilidad de definir la ubicación de destino dentro del documento vinculado.

#### P: ¿Cómo puedo asegurarme de que los enlaces de mis documentos funcionen?

R: Si sigue el tutorial y el código de muestra proporcionados, podrá crear con confianza enlaces de documentos funcionales. Puede probar los enlaces abriendo el documento PDF generado y haciendo clic en los enlaces.

#### P: ¿Puedo crear varios enlaces a documentos dentro de un solo archivo PDF?

 R: ¡Ciertamente! Puede crear múltiples enlaces a documentos dentro de un solo documento PDF usando el`LinkAnnotation`anotación. Esto le permite proporcionar a los usuarios acceso a varios documentos relacionados desde diferentes secciones.

#### P: ¿Existe alguna limitación al vincular a documentos externos?

R: Al vincular a documentos externos, asegúrese de que los documentos vinculados sean accesibles y estén ubicados en las rutas especificadas. También es importante considerar los permisos de usuario y la compatibilidad de los documentos vinculados.

#### P: ¿Puedo vincular documentos almacenados en la web o repositorios en línea?

R: Si bien este tutorial se centra en la vinculación a documentos locales, Aspose.PDF para .NET también admite la vinculación a URL web o repositorios en línea. Puede adaptar el código proporcionado para crear enlaces de documentos basados en la web.