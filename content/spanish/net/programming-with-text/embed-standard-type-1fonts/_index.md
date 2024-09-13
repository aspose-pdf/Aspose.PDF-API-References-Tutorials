---
title: Incrustar fuentes estándar Type 1 en un archivo PDF
linktitle: Incrustar fuentes estándar Type 1 en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a incrustar fuentes Type 1 estándar en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-text/embed-standard-type-1fonts/
---
Este tutorial le guiará a través del proceso de incorporación de fuentes Type 1 estándar en un archivo PDF mediante Aspose.PDF para .NET. El código fuente C# proporcionado muestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea incrustar fuentes Type 1 estándar, agregue la siguiente directiva using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cargue el documento PDF existente
 Cargue un documento PDF existente utilizando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Paso 5: Establezca la propiedad EmbedStandardFonts
 Establecer el`EmbedStandardFonts` propiedad del documento a`true` para permitir la incrustación de fuentes Tipo 1 estándar.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Paso 6: Incruste fuentes en cada página
 Recorra cada página del documento PDF y verifique si las fuentes ya están incrustadas. Si no es así, configure las fuentes`IsEmbedded` propiedad a`true` para incrustar la fuente.

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
 Guarde el documento PDF actualizado utilizando el`Save` método de la`Document` objeto, especificando la ruta del archivo de salida.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Código fuente de muestra para insertar fuentes estándar Type 1 con Aspose.PDF para .NET 
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
			// Comprueba si la fuente ya está incrustada
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
Ha incorporado correctamente fuentes estándar Type 1 en un documento PDF mediante Aspose.PDF para .NET. El archivo PDF actualizado con fuentes incorporadas se ha guardado en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

A: Este tutorial proporciona una guía paso a paso para incorporar fuentes Type 1 estándar en un archivo PDF mediante la biblioteca Aspose.PDF para .NET. El código fuente C# adjunto muestra los procedimientos necesarios.

#### P: ¿Qué espacio de nombres necesito importar?

R: En el archivo de código donde desea insertar fuentes Type 1 estándar, incluya el siguiente espacio de nombres en la parte superior del archivo:

```csharp
using Aspose.Pdf;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: Localiza la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo cargo un documento PDF existente?

 A: En el paso 4, cargará un documento PDF existente utilizando el`Document` constructor y proporcionar la ruta al archivo PDF de entrada.

####  P: ¿Cuál es el propósito de la`EmbedStandardFonts` property?

 A: En el paso 5, configurarás el`EmbedStandardFonts` propiedad del documento a`true`, permitiendo la incorporación de fuentes Tipo 1 estándar.

#### P: ¿Cómo puedo insertar fuentes en cada página?

 A: El paso 6 implica recorrer cada página del documento PDF. Para las fuentes que aún no están incrustadas, deberá configurarlas`IsEmbedded` propiedad a`true` para incrustar la fuente.

#### P: ¿Cómo guardo el documento PDF actualizado?

 A: En el paso 7, utilizarás el`Save` método de la`Document` objeto para guardar el documento PDF actualizado, especificando la ruta del archivo de salida.

#### P: ¿Cuál es la importancia de incrustar fuentes en un documento PDF?

A: La incorporación de fuentes garantiza que las fuentes utilizadas en el PDF se incluyan en el archivo. Esto garantiza una visualización uniforme del texto incluso si el sistema del destinatario no tiene instaladas las fuentes necesarias.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, ha adquirido los conocimientos y las habilidades necesarios para incorporar fuentes Type 1 estándar en un documento PDF mediante Aspose.PDF para .NET. Esto garantiza la representación correcta del texto en diferentes sistemas.