---
title: Obtener campos de la región en un archivo PDF
linktitle: Obtener campos de la región en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Obtenga fácilmente campos de una región específica en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 130
url: /es/net/programming-with-forms/get-fields-from-region/
---
En este tutorial, le mostraremos cómo obtener los campos de una región específica en un archivo PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: abre el archivo PDF

Abra el archivo PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Paso 3: cree un objeto rectangular para delimitar la región

Cree un objeto rectangular para delimitar la región donde desea obtener los campos:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Paso 4: Obtenga el formulario PDF

Obtenga el formato PDF del documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Paso 5: obtenga los campos en la región rectangular

Obtenga los campos ubicados en la región rectangular especificada:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Paso 6: Mostrar nombres y valores de campos

Itere a través de los campos resultantes y muestre sus nombres y valores:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Código fuente de muestra para Obtener campos de la región usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir archivo pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Cree un objeto rectangular para obtener campos en esa área
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Obtenga el formulario PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Obtener campos en el área rectangular
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Mostrar nombres y valores de campos
foreach (Field field in fields)
{
	// Mostrar propiedades de ubicación de imágenes para todas las ubicaciones
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los campos de una región específica en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede extraer fácilmente los campos ubicados en un área rectangular determinada de su documento PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo utilizar este método para obtener campos de una región no rectangular en un documento PDF?

 R: No, el método proporcionado`GetFieldsInRect` está diseñado específicamente para recuperar campos ubicados dentro de una región rectangular en un documento PDF. Si necesita extraer campos de una región no rectangular, deberá implementar una lógica personalizada para identificar y extraer los campos en función de otros criterios, como coordenadas o nombres de campos.

#### P: ¿Cómo puedo modificar el tamaño o la posición del rectángulo para obtener campos de una región diferente?

 R: Para obtener campos de una región diferente, puede modificar el`Aspose.Pdf.Rectangle` Parámetros del objeto utilizados para definir el rectángulo delimitador. El`Rectangle` El constructor toma cuatro parámetros:`x`, `y`, `width` , y`height`que representan las coordenadas de la esquina superior izquierda y las dimensiones del rectángulo. Ajustar estos parámetros cambiará la región de la que se extraen los campos.

#### P: ¿Qué pasa si no hay campos dentro de la región rectangular especificada?

 R: Si no hay campos dentro de la región rectangular especificada, el`GetFieldsInRect` El método devolverá una matriz vacía. Puede verificar la longitud de la matriz para determinar si hay campos dentro de la región.

#### P: ¿Puedo obtener campos de regiones superpuestas en un documento PDF?

 R: Sí, puede obtener campos de regiones superpuestas en un documento PDF creando varios`Aspose.Pdf.Rectangle` objetos y llamando al`GetFieldsInRect` método para cada uno de ellos. Las regiones superpuestas se manejarán de forma independiente y recibirá matrices de campos independientes para cada región.

#### P: ¿Es posible obtener campos de una página específica o de varias páginas en el documento PDF?

R: Sí, puede obtener campos de una página específica o de varias páginas en un documento PDF. Para lograr esto, puede cargar el documento PDF, acceder a las páginas deseadas usando el`doc.Pages` colección, y luego aplicar el`GetFieldsInRect` método para la región específica de cada página.