---
title: Rectángulo de control Z Orden
linktitle: Rectángulo de control Z Orden
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a controlar el orden Z de los rectángulos en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-graphs/control-rectangle-z-order/
---

En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para controlar el orden Z de los rectángulos usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y configure su entorno de desarrollo antes de comenzar. También tener conocimientos básicos de programación en C#.

## Paso 1: Configuración del directorio de documentos

En el código fuente provisto, debe especificar el directorio donde desea guardar el archivo PDF resultante. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: instanciar un objeto de documento y agregar una página

Creamos una instancia de la clase Documento y agregamos una página a este documento.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Paso 3: Configurar el tamaño de la página

Establecemos el tamaño de la página PDF usando el método SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Paso 4: Establecer márgenes de página

Podemos configurar los márgenes de la página usando las propiedades del objeto PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Paso 5: agregue rectángulos con orden Z especificado

Creamos y agregamos rectángulos a la página con diferentes colores y órdenes Z específicos.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Paso 6: Guardar el archivo PDF resultante

Finalmente, guardamos el archivo PDF resultante con el nombre "ControlRectangleZOrder_out.pdf" en el directorio especificado.

```csharp
doc1.Save(dataDir);
```
### Ejemplo de código fuente para Control Rectangle Z Order usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de clase de documento
Document doc1 = new Document();
/// Agregar página a la colección de páginas del archivo PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Establecer el tamaño de la página PDF
page1.SetPageSize(375, 300);
//Establecer el margen izquierdo para el objeto de la página como 0
page1.PageInfo.Margin.Left = 0;
// Establecer el margen superior del objeto de la página como 0
page1.PageInfo.Margin.Top = 0;
// Cree un nuevo rectángulo con Color como Rojo, Orden Z como 0 y ciertas dimensiones
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Cree un nuevo rectángulo con Color como Azul, Orden Z como 0 y ciertas dimensiones
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Cree un nuevo rectángulo con Color como Verde, Orden Z como 0 y ciertas dimensiones
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Guardar el archivo PDF resultante
doc1.Save(dataDir);

```

## Conclusión

En este tutorial, explicamos cómo controlar el orden Z de los rectángulos usando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para organizar y superponer rectángulos en sus archivos PDF con precisión.
