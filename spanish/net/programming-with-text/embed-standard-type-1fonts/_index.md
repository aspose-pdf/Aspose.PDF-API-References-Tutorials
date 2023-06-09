---
title: Incrustar fuentes tipo 1 estándar
linktitle: Incrustar fuentes tipo 1 estándar
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a incrustar fuentes Tipo 1 estándar en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-text/embed-standard-type-1fonts/
---

Este tutorial lo guiará a través del proceso de incrustación de fuentes Tipo 1 estándar en un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código en el que desea incrustar las fuentes Tipo 1 estándar, agregue la siguiente directiva de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cargue el documento PDF existente
 Cargue un documento PDF existente usando el`Document` constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Paso 5: establezca la propiedad EmbedStandardFonts
 Selecciona el`EmbedStandardFonts` propiedad del documento a`true` para habilitar la incrustación de fuentes Tipo 1 estándar.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Paso 6: incrustar fuentes en cada página
 Recorra cada página del documento PDF y verifique si las fuentes ya están incrustadas. Si no, establezca el`IsEmbedded` propiedad a`true` para incrustar la fuente.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Paso 7: Guarde el documento PDF actualizado
 Guarde el documento PDF actualizado usando el`Save` metodo de la`Document` objeto, especificando la ruta del archivo de salida.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Ejemplo de código fuente para fuentes tipo 1 estándar incrustadas mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar un documento PDF existente
Document pdfDocument = new Document(dataDir + "input.pdf");
// Establecer la propiedad EmbedStandardFonts del documento
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Compruebe si la fuente ya está incrustada
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Conclusión
Ha incrustado con éxito fuentes tipo 1 estándar en un documento PDF utilizando Aspose.PDF para .NET. El archivo PDF actualizado con fuentes incrustadas se guardó en la ruta del archivo de salida especificada.