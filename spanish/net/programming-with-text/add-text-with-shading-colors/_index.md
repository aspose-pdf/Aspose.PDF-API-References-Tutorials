---
title: Agregar texto con colores de sombreado
linktitle: Agregar texto con colores de sombreado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto con colores de sombreado a un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-text/add-text-with-shading-colors/
---

Este tutorial lo guiará a través del proceso de agregar texto con colores de sombreado usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código en el que desea agregar texto con colores de sombreado, agregue la siguiente directiva de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cargue el documento PDF
 Cargue el documento PDF existente usando el`Document` constructor y proporcione la ruta al archivo del documento.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // El código va aquí...
}
```

## Paso 5: Encuentra el texto a modificar
 Usar`TextFragmentAbsorber` para encontrar el texto deseado dentro del documento. En el código proporcionado, busca el texto "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Paso 6: establece el color de sombreado para el texto
 Crear un nuevo`Color` objeto con un espacio de color de patrón y especifique los colores de sombreado del degradado. Asigne este color a la`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Paso 7: Aplicar formato de texto adicional (opcional)
 Puede aplicar formato adicional al fragmento de texto, como subrayado, modificando las propiedades del`TextState` objeto.

```csharp
textFragment.TextState.Underline = true;
```

## Paso 8: Guarde el documento PDF modificado
 Guarde el documento PDF modificado usando el`Save` metodo de la`Document` objeto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Ejemplo de código fuente para agregar texto con colores de sombreado usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crea un nuevo color con el espacio de color del patrón
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusión
Ha agregado con éxito texto con colores de sombreado a su documento PDF utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.