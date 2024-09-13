---
title: Agregar texto con colores sombreados en un archivo PDF
linktitle: Agregar texto con colores sombreados en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto con colores de sombreado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-text/add-text-with-shading-colors/
---
Este tutorial le guiará a través del proceso de agregar texto con colores de sombreado en un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar texto con colores de sombreado, agregue la siguiente directiva using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cargue el documento PDF
 Cargue el documento PDF existente utilizando el`Document` constructor y proporcionar la ruta al archivo del documento.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // El código va aquí...
}
```

## Paso 5: Encuentra el texto a modificar
Usar`TextFragmentAbsorber` Para encontrar el texto deseado dentro del documento, en el código proporcionado, busca el texto "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Paso 6: Establezca el color de sombreado para el texto
 Crear uno nuevo`Color` Objeto con un espacio de color de patrón y especifique los colores de sombreado de degradado. Asigne este color al`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto.

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
 Guarde el documento PDF modificado utilizando el`Save` método de la`Document` objeto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Código fuente de muestra para agregar texto con colores de sombreado utilizando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crear un nuevo color con el espacio de color de patrón
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusión
Ha añadido correctamente texto con colores de sombreado a su documento PDF con Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque principal de este tutorial?

A: Este tutorial lo guía a través del proceso de agregar texto con colores de sombreado a un archivo PDF mediante la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar texto con colores de sombreado, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, localiza la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo cargo un documento PDF existente?

 A: En el paso 4, cargará un documento PDF existente utilizando el`Document` constructor y proporcionando la ruta al archivo del documento:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // El código va aquí...
}
```

#### P: ¿Cómo puedo encontrar y modificar un texto específico dentro del documento PDF?

 A: En el paso 5, utilizarás el`TextFragmentAbsorber` para buscar el texto deseado dentro del documento. Luego, puede modificar sus propiedades:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### P: ¿Cómo puedo configurar colores de sombreado para el texto?

 A: En el paso 6, crearás un nuevo`Color` Objeto con un espacio de color de patrón y especifique los colores de sombreado de degradado. Asigne este color al`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### P: ¿Puedo aplicar formato de texto adicional al texto modificado?

R: Sí, en el paso 7, puede aplicar formato de texto adicional, como subrayado, modificando las propiedades del`TextState` objeto:

```csharp
textFragment.TextState.Underline = true;
```

#### P: ¿Cómo guardo el documento PDF modificado?

 A: En el paso 8, guardará el documento PDF modificado utilizando el`Save` método de la`Document` objeto:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Si sigue este tutorial, habrá aprendido a mejorar su documento PDF agregando texto con colores de sombreado mediante Aspose.PDF para .NET. Esto puede resultar especialmente útil para resaltar y enfatizar contenido de texto específico dentro de sus archivos PDF.