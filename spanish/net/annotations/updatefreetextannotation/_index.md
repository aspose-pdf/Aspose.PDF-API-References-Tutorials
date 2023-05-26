---
title: Actualizar anotación de texto libre
linktitle: Actualizar anotación de texto libre
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a actualizar la función de anotación de texto libre de Aspose.PDF para .NET usando el código fuente de C#.
type: docs
weight: 160
url: /es/net/annotations/updatefreetextannotation/
---
En este artículo, proporcionaremos una guía paso a paso para explicar el siguiente código fuente de C# de la función Actualizar anotación de texto libre de Aspose.PDF para .NET. Revisaremos cada línea de código y explicaremos lo que hace, para que incluso los principiantes puedan entenderlo.

Ahora vamos a explicar paso a paso cada línea del código anterior:

## Paso 1: Configuración del directorio de documentos

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

En esta línea estamos configurando la ruta al directorio que contiene el documento PDF que queremos actualizar.

## Paso 2: Abrir el documento PDF

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 Aquí estamos abriendo el documento PDF usando Aspose.PDF's`Document` class y especificando la ruta al archivo PDF de entrada.

## Paso 3: actualizar el tamaño de fuente y el color de la anotación de texto libre

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 En este paso, estamos actualizando el tamaño de fuente y el color de la primera anotación de texto libre en la segunda página del documento PDF. Estamos haciendo esto accediendo a la`TextStyle` propiedad de la`FreeTextAnnotation` objeto y establecer su`FontSize` y`Color` propiedades a 18 y Green, respectivamente.

## Paso 4: Manejo de excepciones

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 Este es un estándar`try-catch` bloque que detecta cualquier excepción que pueda ocurrir al ejecutar el código e imprime el mensaje de error en la consola.

## Conclusión

En este artículo, proporcionamos una guía paso a paso para explicar el código fuente de C# de la función Actualizar anotación de texto libre de Aspose.PDF para .NET. Siguiendo estos pasos, puede actualizar fácilmente el tamaño de fuente y el color de las anotaciones de texto libre en sus documentos PDF utilizando Aspose.PDF para .NET.

### Ejemplo de código fuente para Actualizar anotación de texto libre usando Aspose.PDF para .NET

Antes de profundizar en la explicación del código, primero echemos un vistazo al código en sí. Este ejemplo de código muestra cómo actualizar las propiedades de una anotación de texto libre en un documento PDF usando Aspose.PDF para .NET.

```csharp
try
{
    // La ruta al directorio de documentos.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Abrir documento
    Document doc1 = new Document(dataDir + "input.pdf");

    // Establezca el tamaño de fuente y el color de la anotación:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```