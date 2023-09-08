---
title: Incrustar fuentes estándar tipo 1 en un archivo PDF
linktitle: Incrustar fuentes estándar tipo 1 en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a incrustar fuentes estándar Tipo 1 en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-text/embed-standard-type-1fonts/
---
Este tutorial lo guiará a través del proceso de incrustar fuentes estándar Tipo 1 en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea incrustar fuentes estándar Tipo 1, agregue la siguiente directiva usando en la parte superior del archivo:

```csharp
using Aspose.Pdf;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: cargue el documento PDF existente
 Cargue un documento PDF existente usando el`Document`constructor y pasando la ruta al archivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Paso 5: establezca la propiedad EmbedStandardFonts
 Selecciona el`EmbedStandardFonts` propiedad del documento para`true` para permitir la incrustación de fuentes estándar Tipo 1.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Paso 6: incrusta fuentes en cada página
 Recorra cada página del documento PDF y compruebe si las fuentes ya están incrustadas. Si no, configure el`IsEmbedded` propiedad a`true` para incrustar la fuente.

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

## Paso 7: guarde el documento PDF actualizado
 Guarde el documento PDF actualizado utilizando el`Save` método de la`Document` objeto, especificando la ruta del archivo de salida.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Código fuente de muestra para incrustar fuentes estándar tipo 1 usando Aspose.PDF para .NET 
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
Ha incrustado con éxito fuentes estándar Tipo 1 en un documento PDF utilizando Aspose.PDF para .NET. El archivo PDF actualizado con fuentes incrustadas se guardó en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial proporciona una guía paso a paso para incrustar fuentes Tipo 1 estándar en un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. El código fuente de C# adjunto demuestra los procedimientos necesarios.

#### P: ¿Qué espacio de nombres necesito importar?

R: En el archivo de código donde desea incrustar fuentes estándar Tipo 1, incluya el siguiente espacio de nombres en la parte superior del archivo:

```csharp
using Aspose.Pdf;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: Localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` en el código y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo cargo un documento PDF existente?

 R: En el Paso 4, cargará un documento PDF existente usando el`Document` constructor y proporcionando la ruta al archivo PDF de entrada.

####  P: ¿Cuál es el propósito de la`EmbedStandardFonts` property?

 R: En el paso 5, configurará el`EmbedStandardFonts` propiedad del documento para`true`, permitiendo la incrustación de fuentes estándar Tipo 1.

#### P: ¿Cómo incrusto fuentes en cada página?

 R: El paso 6 implica recorrer cada página del documento PDF. Para fuentes que aún no están incrustadas, configurará el`IsEmbedded` propiedad a`true` para incrustar la fuente.

#### P: ¿Cómo guardo el documento PDF actualizado?

 R: En el paso 7, utilizará el`Save` método de la`Document` objeto para guardar el documento PDF actualizado, especificando la ruta del archivo de salida.

#### P: ¿Cuál es la importancia de incrustar fuentes en un documento PDF?

R: Incrustar fuentes garantiza que las fuentes utilizadas en el PDF estén incluidas dentro del propio archivo. Esto garantiza una visualización consistente del texto incluso si el sistema del destinatario no tiene instaladas las fuentes requeridas.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, obtendrá los conocimientos y las habilidades para incrustar fuentes Tipo 1 estándar en un documento PDF utilizando Aspose.PDF para .NET. Esto garantiza la representación adecuada del texto en diferentes sistemas.