---
title: Agregar texto con colores de sombreado en un archivo PDF
linktitle: Agregar texto con colores de sombreado en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar texto con colores de sombreado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-text/add-text-with-shading-colors/
---
Este tutorial lo guiará a través del proceso de agregar texto con colores de sombreado en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea agregar texto con colores de sombreado, agregue la siguiente directiva usando en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: cargue el documento PDF
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

## Paso 6: establece el color de sombreado del texto
 Crear un nuevo`Color` objeto con un espacio de color de patrón y especifique los colores de sombreado degradado. Asigna este color al`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Paso 7: aplique formato de texto adicional (opcional)
 Puede aplicar formato adicional al fragmento de texto, como subrayado, modificando las propiedades del`TextState` objeto.

```csharp
textFragment.TextState.Underline = true;
```

## Paso 8: guarde el documento PDF modificado
 Guarde el documento PDF modificado utilizando el`Save` método de la`Document` objeto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Código fuente de muestra para agregar texto con colores de sombreado usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crea un nuevo color con el espacio de color del patrón.
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusión
Ha agregado con éxito texto con colores sombreados a su documento PDF usando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque principal de este tutorial?

R: Este tutorial lo guía a través del proceso de agregar texto con colores de sombreado a un archivo PDF usando la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar texto con colores de sombreado, importe los siguientes espacios de nombres al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: En el código, localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo cargo un documento PDF existente?

 R: En el Paso 4, cargará un documento PDF existente usando el`Document` constructor y proporcionando la ruta al archivo del documento:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // El código va aquí...
}
```

#### P: ¿Cómo encuentro y modifico texto específico dentro del documento PDF?

 R: En el paso 5, utilizará el`TextFragmentAbsorber`para encontrar el texto deseado dentro del documento. Luego, puedes modificar sus propiedades:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### P: ¿Cómo puedo configurar colores de sombreado para el texto?

 R: En el paso 6, creará un nuevo`Color` objeto con un espacio de color de patrón y especifique los colores de sombreado degradado. Asigna este color al`ForegroundColor` propiedad de la`TextState` del`TextFragment` objeto:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### P: ¿Puedo aplicar formato de texto adicional al texto modificado?

 R: Sí, en el Paso 7, puede aplicar formato de texto adicional, como subrayado, modificando las propiedades del`TextState` objeto:

```csharp
textFragment.TextState.Underline = true;
```

#### P: ¿Cómo guardo el documento PDF modificado?

 R: En el paso 8, guardará el documento PDF modificado usando el`Save` método de la`Document` objeto:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, habrá aprendido con éxito cómo mejorar su documento PDF agregando texto con colores sombreados usando Aspose.PDF para .NET. Esto puede resultar particularmente útil para resaltar y enfatizar contenido de texto específico dentro de sus archivos PDF.