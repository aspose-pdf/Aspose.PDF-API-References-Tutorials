---
title: Extraer información de la firma
linktitle: Extraer información de la firma
second_title: Referencia de API de Aspose.PDF para .NET
description: Extracción de información de firma usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-security-and-signatures/extract-signature-info/
---

El proceso de extraer información de la firma de un documento PDF puede ser bastante útil en varios escenarios. Ya sea que necesite validar la autenticidad de un documento firmado o analizar el certificado utilizado para la firma, la biblioteca Aspose.PDF para .NET proporciona una solución conveniente. En este tutorial, lo guiaremos a través del proceso paso a paso para extraer información de la firma utilizando el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos en su lugar:

1. Conocimientos básicos del lenguaje de programación C#.
2. Aspose.PDF para la biblioteca .NET instalada en su sistema.
3. Un documento PDF válido con uno o más campos de firma.

Ahora, profundicemos en los detalles de implementación.

## Paso 1: Importación de las bibliotecas requeridas

 Para comenzar, debe importar las bibliotecas necesarias en su proyecto de C#. En este caso, necesitamos importar el`Aspose.Pdf` y`System.IO` espacios de nombres Esto se puede hacer agregando el siguiente código al comienzo de su archivo C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Paso 2: Configuración de la ruta del documento

 A continuación, debe establecer la ruta al documento PDF del que desea extraer la información de la firma. Reemplazar`"YOUR DOCUMENTS DIRECTORY"` en el siguiente fragmento de código con la ruta real a su documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Paso 3: Extracción de la información de la firma

Ahora, pasemos a la parte principal del código donde extraemos la información de la firma del documento PDF. Iteramos a través de cada campo en el formulario del documento y verificamos si es un campo de firma. Si se encuentra un campo de firma, procedemos a extraer el certificado. Agregue el siguiente fragmento de código:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Extraer el certificado
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Paso 4: Extracción del Certificado

En este paso, extraemos el certificado del campo de firma y lo guardamos como archivo. El certificado extraído se puede analizar más a fondo o utilizarse con fines de validación. El fragmento de código a continuación demuestra el proceso de extracción y guardado:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Paso 5

: Guardar el certificado

Finalmente, guardamos el certificado extraído como un archivo. En este ejemplo, el certificado se guarda con el nombre "input.cer" en el directorio especificado. Puede modificar el código para adaptarlo a sus necesidades. Aquí está el fragmento de código para guardar el certificado:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

¡Eso es todo! Ha extraído correctamente la información de la firma con Aspose.PDF para .NET. Siéntase libre de integrar este código en sus propias aplicaciones o modificarlo según sus necesidades.

### Ejemplo de código fuente para Extraer información de firma usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, repasamos una guía paso a paso sobre cómo extraer información de la firma de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Cubrimos el proceso de importar las bibliotecas requeridas, establecer la ruta del documento, extraer la información de la firma, extraer el certificado y guardarlo en un archivo. Siguiendo estos pasos, puede recuperar fácilmente los detalles de la firma y trabajar con ellos según sea necesario.