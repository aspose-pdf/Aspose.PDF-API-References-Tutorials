---
title: Establecer propiedades para el diálogo de impresión
linktitle: Establecer propiedades para el diálogo de impresión
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar las propiedades para el cuadro de diálogo de impresión en Aspose.PDF para .NET usando la guía paso a paso.
type: docs
weight: 320
url: /es/net/programming-with-document/setpropertiesforprintdialog/
---
aquí hay una guía paso a paso para configurar las propiedades del cuadro de diálogo de impresión usando Aspose.PDF para .NET:


## Paso 1: Defina el directorio donde se encuentra su documento PDF:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Paso 2: Crear una nueva instancia de la`Document` class:

```csharp
using (Document doc = new Document())
{
  // código aquí
}
```
   
## Paso 3: agregue una nueva página al documento:

```csharp
doc.Pages.Add();
```
   
##  Paso 4: establezca la propiedad dúplex en`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Paso 5: guarde el documento con el nombre de archivo y el formato especificados:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### Ejemplo de código fuente para el cuadro de diálogo Establecer propiedades para imprimir usando Aspose.PDF para .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## Conclusión

Aspose.PDF para .NET facilita la configuración de propiedades para el cuadro de diálogo de impresión en sus archivos PDF. Siguiendo la guía paso a paso anterior, puede optimizar rápidamente sus archivos PDF para su impresión.