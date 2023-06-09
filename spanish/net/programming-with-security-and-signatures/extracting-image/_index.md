---
title: Extracción de imagen
linktitle: Extracción de imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Extraiga fácilmente imágenes de documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-security-and-signatures/extracting-image/
---

La extracción de imágenes de un documento PDF puede ser útil en muchos casos. Con Aspose.PDF para .NET, puede extraer imágenes fácilmente utilizando el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Paso 2: establecer la ruta a la carpeta de documentos

En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea extraer la imagen. Reemplazar`"YOUR DOCUMENTS DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Paso 3: Extraiga la imagen del documento PDF

Ahora extraeremos la imagen del documento PDF usando el siguiente código:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

En este ejemplo, recorremos cada campo del formulario en el documento PDF. Si se encuentra un campo de firma, extraemos la imagen asociada y la guardamos en un archivo JPEG.

### Ejemplo de código fuente para extraer imágenes con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para extraer imágenes de un documento PDF usando Aspose.PDF para .NET. Puede integrar este código en sus propios proyectos para extraer imágenes y usarlas según sea necesario.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las características avanzadas de extracción de imágenes y manipulación de documentos PDF.