---
title: Ventana Obtener documento
linktitle: Ventana Obtener documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar la función GetDocumentWindow de Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF.
type: docs
weight: 170
url: /es/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF para .NET es una potente biblioteca de manipulación de PDF que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de recuperar información sobre las propiedades de la ventana de un documento. Este tutorial le guiará a través de los pasos para utilizar la biblioteca.`GetDocumentWindow` característica de Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF.

## Paso 1: Instalar Aspose.PDF para .NET

 Para utilizar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP en una carpeta de su computadora. Luego, deberá agregar una referencia a la DLL Aspose.PDF para .NET en su proyecto .NET.

## Paso 2: Cargue el documento PDF

 Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetDocumentWindow`Función para recuperar información sobre las propiedades de la ventana de un documento PDF.

El primer paso para utilizar esta función es cargar el documento PDF del que desea recuperar información. Para ello, puede utilizar el siguiente código:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede utilizar para recuperar información sobre las propiedades de la ventana del documento.

## Paso 3: Recuperar las propiedades de la ventana del documento

Para recuperar información sobre las propiedades de la ventana de un documento PDF, puede utilizar el siguiente código:

```csharp
// Recuperar las propiedades de la ventana del documento
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

En el código anterior, cada línea recupera una propiedad de ventana diferente del documento PDF y la envía a la consola. Puede personalizar este código para recuperar solo las propiedades que le interesen.

### Ejemplo de código fuente para la ventana de obtención de documentos de un archivo PDF utilizando Aspose.PDF para .NET 

 Aquí está el código fuente completo para recuperar las propiedades de la ventana de un documento PDF usando el`GetDocumentWindow` Característica de Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Obtener diferentes propiedades del documento
// Posición de la ventana del documento - Predeterminado: falso
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Orden de lectura predominante; determina la posición de la página
// Cuando se muestran uno al lado del otro: predeterminado: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Si la barra de título de la ventana debe mostrar el título del documento
// Si es falso, la barra de título muestra el nombre del archivo PDF. Predeterminado: falso
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Si desea cambiar el tamaño de la ventana del documento para que se ajuste al tamaño de
// Primera página mostrada - Predeterminado: falso
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Si desea ocultar la barra de menú de la aplicación de visualización: valor predeterminado: falso
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Si desea ocultar la barra de herramientas de la aplicación de visualización: valor predeterminado: falso
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Si desea ocultar elementos de la interfaz de usuario como barras de desplazamiento
// Y dejando solo el contenido de la página visible - Predeterminado: falso
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Modo de página del documento. Cómo visualizar el documento al salir del modo de pantalla completa.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// El diseño de la página, es decir, página única, una columna.
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Cómo debe verse el documento al abrirlo
// Mostrar miniaturas, pantalla completa, mostrar panel de archivos adjuntos
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusión

En este tutorial, hemos aprendido a utilizar Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF. Al cargar un documento PDF y acceder a sus propiedades de ventana, puede obtener información sobre cómo se debe mostrar el documento cuando se abre en una aplicación de visualización. Aspose.PDF para .NET proporciona un potente conjunto de funciones para trabajar con archivos PDF de forma programática, lo que lo convierte en una herramienta valiosa para la manipulación de PDF en aplicaciones .NET.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de recuperar las propiedades de la ventana de un documento PDF?

A: La recuperación de las propiedades de la ventana de un documento PDF le permite reunir información sobre cómo debe mostrarse el documento PDF cuando se abre en una aplicación de visualización. Estas propiedades controlan diversos aspectos, como la posición de la ventana, el modo de visualización y la visibilidad de los elementos de la interfaz de usuario.

#### P: ¿Cómo puedo instalar Aspose.PDF para .NET en mi proyecto .NET?

 R: Para instalar Aspose.PDF para .NET, debe descargar la biblioteca desde el sitio[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Después de la descarga, extraiga el contenido del archivo ZIP y agregue una referencia a la DLL Aspose.PDF para .NET en su proyecto .NET.

#### P: ¿Puedo personalizar el código para recuperar únicamente propiedades de ventana específicas?

R: Sí, puedes personalizar el código para recuperar propiedades de ventana específicas comentando las líneas que no necesitas. Cada línea del código corresponde a una propiedad de ventana específica, por lo que puedes incluir o excluir propiedades según tus requisitos.

#### P: ¿Qué tipos de propiedades de ventana puedo recuperar usando Aspose.PDF para .NET?

R: Al utilizar Aspose.PDF para .NET, puede recuperar varias propiedades de ventana de un documento PDF, incluido centrar la ventana, configurar el diseño de la página, controlar la visualización de barras de herramientas y barras de menú, y más.