---
title: Aplanar anotación
linktitle: Aplanar anotación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a acoplar anotaciones en un documento PDF con Aspose.PDF para .NET. Conservar las anotaciones y evitar alteraciones accidentales.
type: docs
weight: 150
url: /es/net/programming-with-document/flattenannotation/
---

Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con documentos PDF mediante programación. Una de las características que proporciona es la capacidad de acoplar anotaciones en documentos PDF. Acoplar anotaciones en un documento PDF significa que las anotaciones pasan a formar parte del contenido del documento y ya no se pueden editar ni eliminar. Esto es útil cuando desea asegurarse de que las anotaciones se conserven y no se puedan modificar accidentalmente.

En este tutorial, analizaremos cómo usar Aspose.PDF para .NET para acoplar anotaciones en un documento PDF. Proporcionaremos una guía paso a paso sobre cómo hacer esto, junto con un código fuente de ejemplo.

## Paso 1: Cree una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez que se crea el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Abra el documento PDF
Abra el documento PDF que desea aplanar:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 4: aplane las anotaciones
Acoplar las anotaciones en el documento PDF:

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## Paso 5: Guarde el documento actualizado
Guarde el documento actualizado:

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Flatten Annotation usando Aspose.PDF para .NET
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Aplanar anotaciones
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

```csharp

            
            // La ruta al directorio de documentos.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            // Abrir documento
            Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
            // Aplanar anotaciones
            foreach (var page in pdfDocument.Pages)
            {
                foreach (var annotation in page.Annotations)
                {
                    annotation.Flatten();
                }

            }
            // Guardar documento actualizado
            pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
            
            Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
        
```

## Conclusión
En este tutorial, hemos discutido cómo acoplar anotaciones en un documento PDF utilizando Aspose.PDF para .NET. Aplanar las anotaciones en un documento PDF es una función útil que garantiza que las anotaciones se conserven y no se puedan alterar accidentalmente. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, incluidas las anotaciones acopladas. 

