---
title: Obtener ventana de documento
linktitle: Obtener ventana de documento
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar la función GetDocumentWindow de Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF.
type: docs
weight: 170
url: /es/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF para .NET es una poderosa biblioteca de manipulación de PDF que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de recuperar información sobre las propiedades de la ventana de un documento. Este tutorial lo guiará a través de los pasos para usar el`GetDocumentWindow` característica de Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF.

## Paso 1: Instale Aspose.PDF para .NET

 Para utilizar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP a una carpeta en su computadora. Luego deberá agregar una referencia a Aspose.PDF para .NET DLL en su proyecto .NET.

## Paso 2: cargue el documento PDF

Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetDocumentWindow` función para recuperar información sobre las propiedades de la ventana de un documento PDF.

El primer paso para utilizar esta función es cargar el documento PDF sobre el que desea recuperar información. Para hacer esto, puedes usar el siguiente código:

```csharp
// La ruta al documento PDF.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Abrir el documento PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede utilizar para recuperar información sobre las propiedades de la ventana del documento.

## Paso 3: recuperar las propiedades de la ventana del documento

Para recuperar información sobre las propiedades de la ventana de un documento PDF, puede utilizar el siguiente código:

```csharp
// Recuperar las propiedades de la ventana del documento.
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

### Código fuente de ejemplo para obtener la ventana del documento de un archivo PDF usando Aspose.PDF para .NET 

 Aquí está el código fuente completo para recuperar las propiedades de ventana de un documento PDF usando el`GetDocumentWindow` característica de Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Obtener diferentes propiedades del documento
// Posición de la ventana del documento - Predeterminado: falso
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Orden de lectura predominante; determina la posición de la página
// Cuando se muestra uno al lado del otro - Valor predeterminado: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Si la barra de título de la ventana debe mostrar el título del documento
// Si es falso, la barra de título muestra el nombre del archivo PDF. Predeterminado: falso
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Si se debe cambiar el tamaño de la ventana del documento para que se ajuste al tamaño de
// Primera página mostrada - Predeterminado: falso
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Si se debe ocultar la barra de menú de la aplicación del visor - Valor predeterminado: falso
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Si se debe ocultar la barra de herramientas de la aplicación del visor - Valor predeterminado: falso
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Si se deben ocultar elementos de la interfaz de usuario como barras de desplazamiento
// Y dejando solo el contenido de la página mostrado - Predeterminado: falso
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Modo de página del documento. Cómo mostrar el documento al salir del modo de pantalla completa.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// El diseño de la página, es decir, una sola página, una columna.
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Cómo debe mostrarse el documento cuando se abre
// Es decir, mostrar miniaturas, pantalla completa, mostrar panel de archivos adjuntos.
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusión

En este tutorial, hemos aprendido cómo usar Aspose.PDF para .NET para recuperar información sobre las propiedades de la ventana de un documento PDF. Al cargar un documento PDF y acceder a las propiedades de su ventana, puede recopilar información sobre cómo debe mostrarse el documento cuando se abre en una aplicación de visualización. Aspose.PDF para .NET proporciona un potente conjunto de funciones para trabajar con archivos PDF mediante programación, lo que lo convierte en una herramienta valiosa para la manipulación de PDF en aplicaciones .NET.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de recuperar las propiedades de ventana de un documento PDF?

R: Recuperar las propiedades de la ventana de un documento PDF le permite recopilar información sobre cómo debe mostrarse el documento PDF cuando se abre en una aplicación de visualización. Estas propiedades controlan varios aspectos, como la posición de la ventana, el modo de visualización y la visibilidad de los elementos de la interfaz de usuario.

#### P: ¿Cómo puedo instalar Aspose.PDF para .NET en mi proyecto .NET?

 R: Para instalar Aspose.PDF para .NET, necesita descargar la biblioteca desde[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net). Después de la descarga, extraiga el contenido del archivo ZIP y agregue una referencia a Aspose.PDF para .NET DLL en su proyecto .NET.

#### P: ¿Puedo personalizar el código para recuperar propiedades de ventana específicas únicamente?

R: Sí, puedes personalizar el código para recuperar propiedades de ventana específicas comentando las líneas que no necesitas. Cada línea del código corresponde a una propiedad de ventana específica, por lo que puede incluir o excluir propiedades según sus requisitos.

#### P: ¿Qué tipos de propiedades de ventana puedo recuperar usando Aspose.PDF para .NET?

R: Al utilizar Aspose.PDF para .NET, puede recuperar varias propiedades de la ventana de un documento PDF, incluido centrar la ventana, configurar el diseño de la página, controlar la visualización de las barras de herramientas y de menú, y más.