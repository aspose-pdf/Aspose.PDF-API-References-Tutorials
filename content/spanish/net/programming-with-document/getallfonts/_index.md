---
title: Obtenga todas las fuentes en un archivo PDF
linktitle: Obtenga todas las fuentes en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener todas las fuentes utilizadas en un archivo PDF mediante programación con esta guía paso a paso y código de ejemplo.
type: docs
weight: 160
url: /es/net/programming-with-document/getallfonts/
---
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con archivos PDF de forma programada. Una de las funciones que ofrece es la capacidad de obtener todas las fuentes utilizadas en un archivo PDF. Esto puede resultar útil si necesita analizar o manipular de forma programada las fuentes de un archivo PDF.

En este tutorial, analizaremos cómo utilizar Aspose.PDF para .NET para obtener todas las fuentes utilizadas en un documento PDF. Proporcionaremos una guía paso a paso sobre cómo hacerlo, junto con un código fuente de ejemplo.

## Paso 1: Crear una nueva aplicación de consola C#
Para comenzar, crea una nueva aplicación de consola de C# en Visual Studio. Puedes ponerle el nombre que desees. Una vez creado el proyecto, debes agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Cargue el documento PDF
Cargue el documento PDF del que desea obtener las fuentes:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: Consigue todas las fuentes
Obtenga todas las fuentes utilizadas en el documento PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Paso 5: Imprima todas las fuentes
Imprima todas las fuentes utilizadas en el documento PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Código fuente de ejemplo para obtener todas las fuentes con Aspose.PDF para .NET
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusión
En este tutorial, hemos analizado cómo obtener todas las fuentes utilizadas en un documento PDF mediante Aspose.PDF para .NET. Obtener todas las fuentes utilizadas en un documento PDF puede resultar útil si necesita analizar o manipular mediante programación las fuentes de un documento PDF. Aspose.PDF para .NET proporciona una API sencilla y fácil de usar para trabajar con documentos PDF, incluida la obtención de todas las fuentes utilizadas en un documento PDF.

### Preguntas frecuentes

#### P: ¿Por qué necesitaría obtener todas las fuentes utilizadas en un documento PDF?

R: Obtener todas las fuentes utilizadas en un documento PDF puede ser útil si necesita analizar o manipular programáticamente las fuentes para diversos fines, como el reemplazo o la personalización de fuentes.

#### P: ¿Cómo puedo obtener todas las fuentes utilizadas en un documento PDF usando Aspose.PDF para .NET?

 A: Puede obtener todas las fuentes utilizadas en un documento PDF usando Aspose.PDF para .NET llamando al método`GetAllFonts` método de la`FontUtilities` clase. Este método devuelve una matriz de`Aspose.Pdf.Text.Font` objetos que representan las fuentes utilizadas en el documento PDF.

#### P: ¿Puedo filtrar fuentes según determinados criterios?

R: Sí, puede filtrar fuentes en función de determinados criterios mediante Aspose.PDF para .NET. Después de obtener todas las fuentes, puede analizarlas mediante programación y aplicar la lógica de filtrado según sea necesario.

#### P: ¿Aspose.PDF para .NET es compatible con varios formatos de fuente?

R: Sí, Aspose.PDF para .NET es compatible con varios formatos de fuentes, incluidas las fuentes TrueType, OpenType y Type 1. Puede trabajar con distintos formatos de fuentes y manejarlos durante la manipulación de documentos PDF.