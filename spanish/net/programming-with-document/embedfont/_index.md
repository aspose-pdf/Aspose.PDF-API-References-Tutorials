---
title: Fuente incrustada
linktitle: Fuente incrustada
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a incrustar fuentes en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso. Asegúrese de que sus documentos se muestren correctamente en cualquier dispositivo.
type: docs
weight: 120
url: /es/net/programming-with-document/embedfont/
---

En este tutorial, discutiremos cómo incrustar fuentes en un archivo PDF usando Aspose.PDF para .NET. Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, editar y manipular documentos PDF mediante programación. Esta biblioteca proporciona una amplia gama de funciones para trabajar con documentos PDF, incluida la adición de texto, imágenes, tablas y mucho más. Incrustar fuentes en un archivo PDF es un requisito común para los desarrolladores que desean asegurarse de que el archivo PDF se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos o no.

## Paso 1: Cree una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez que se crea el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Cargue un archivo PDF existente
Para incrustar fuentes en un archivo PDF existente, debe cargar ese archivo usando la clase Documento. El siguiente código demuestra cómo cargar un archivo PDF existente:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: iterar a través de todas las páginas
Una vez que haya cargado el archivo PDF, debe recorrer todas las páginas del documento. Para cada página, debe verificar si se utilizan fuentes y, de ser así, debe incrustar esas fuentes. El siguiente código demuestra cómo recorrer todas las páginas del archivo PDF e incrustar las fuentes:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Compruebe si la fuente ya está incrustada
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Compruebe los objetos de formulario
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Comprobar si la fuente está incrustada
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Paso 5: Guarde el documento PDF
Una vez que haya incrustado todas las fuentes en el archivo PDF, debe guardar el documento. El siguiente código muestra cómo guardar el archivo PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Embed Font usando Aspose.PDF para .NET

Aquí está el código fuente completo para incrustar una fuente usando Aspose.PDF para .NET.


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargue un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");

// Iterar a través de todas las páginas
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Compruebe si la fuente ya está incrustada
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Compruebe los objetos de formulario
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Comprobar si la fuente está incrustada
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Conclusión
En este artículo, hemos discutido cómo incrustar fuentes en un archivo PDF usando Aspose.PDF para .NET. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, lo que incluye agregar e incrustar fuentes. Incrustar fuentes en un archivo PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos.
