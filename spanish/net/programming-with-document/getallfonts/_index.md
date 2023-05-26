---
title: Obtener todas las fuentes
linktitle: Obtener todas las fuentes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener todas las fuentes utilizadas en un documento PDF mediante programación con esta guía paso a paso y código de ejemplo.
type: docs
weight: 160
url: /es/net/programming-with-document/getallfonts/
---

Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con documentos PDF mediante programación. Una de las funciones que ofrece es la posibilidad de obtener todas las fuentes utilizadas en un documento PDF. Esto puede ser útil si necesita analizar o manipular mediante programación las fuentes en un documento PDF.

En este tutorial, discutiremos cómo usar Aspose.PDF para .NET para obtener todas las fuentes utilizadas en un documento PDF. Proporcionaremos una guía paso a paso sobre cómo hacer esto, junto con un código fuente de ejemplo.

## Paso 1: Cree una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez que se crea el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Cargue el documento PDF
Cargue el documento PDF del que desea obtener las fuentes:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: Obtenga todas las fuentes
Obtenga todas las fuentes utilizadas en el documento PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Paso 5: imprime todas las fuentes
Imprima todas las fuentes utilizadas en el documento PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Ejemplo de código fuente para Obtener todas las fuentes usando Aspose.PDF para .NET
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
En este tutorial, hemos discutido cómo obtener todas las fuentes utilizadas en un documento PDF usando Aspose.PDF para .NET. Obtener todas las fuentes utilizadas en un documento PDF puede ser útil si necesita analizar o manipular mediante programación las fuentes en un documento PDF. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, incluida la obtención de todas las fuentes utilizadas en un documento PDF.


