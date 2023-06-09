---
title: Eliminar objetos gráficos
linktitle: Eliminar objetos gráficos
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para eliminar objetos gráficos de un documento PDF utilizando Aspose.PDF para .NET. Personaliza y limpia tus archivos PDF.
type: docs
weight: 30
url: /es/net/programming-with-operators/remove-graphics-objects/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo eliminar objetos gráficos de un documento PDF usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Con los operadores proporcionados por Aspose.PDF, puede apuntar y eliminar objetos gráficos específicos de una página PDF.

## requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos en su lugar:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca del sitio web oficial de Aspose e instalarla en su máquina.

## Paso 2: importa los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Paso 3: Cargar el documento PDF

Use el siguiente código para cargar el documento PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
```

Asegúrese de especificar la ruta real del archivo PDF en su máquina y ajuste el número de página según sea necesario.

## Paso 4: Eliminación de objetos gráficos

Utilice el siguiente código para eliminar objetos gráficos de la página PDF:

```csharp
Operator[] operators = new Operator[] {
newStroke(),
new ClosePathStroke(),
newFill()
};
oc.Delete(operators);
```

El código anterior elimina los objetos gráficos identificados por los operadores Trazo, Cierre de ruta y Relleno.

### Ejemplo de código fuente para eliminar objetos gráficos con Aspose.PDF para .NET
 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir+ "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
// Operadores de pintura de ruta usados
Operator[] operators = new Operator[] {
		new Aspose.Pdf.Operators.Stroke(),
		new Aspose.Pdf.Operators.ClosePathStroke(),
		new Aspose.Pdf.Operators.Fill()
};
oc.Delete(operators);
doc.Save(dataDir+ "No_Graphics_out.pdf");

```

## Conclusión

En este tutorial, aprendió a eliminar objetos gráficos de un documento PDF utilizando Aspose.PDF para .NET. Con los operadores proporcionados por Aspose.PDF, puede apuntar y eliminar objetos gráficos específicos de una página PDF. Esto le permite personalizar y limpiar el contenido de sus documentos PDF según sus necesidades.
