---
title: XPS a PDF
linktitle: XPS a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir archivos XPS a PDF con Aspose.PDF para .NET.
type: docs
weight: 350
url: /es/net/document-conversion/xps-to-pdf/
---
En este tutorial, lo guiaremos a través de cómo convertir un archivo XPS a PDF utilizando la biblioteca Aspose.PDF para .NET paso a paso. Detallaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, podrá convertir fácilmente archivos XPS a documentos PDF.

## Paso 1: establecer el directorio de documentos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta donde guardó sus archivos.

## Paso 2: Cree una instancia del objeto LoadOptions mediante las opciones de carga de XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Cree una instancia del objeto LoadOptions mediante las opciones de carga de XPS.

## Paso 3: crear el objeto de documento
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Cree un objeto Documento especificando el archivo XPS de entrada y las opciones de carga.

## Paso 4: Guarde el documento PDF resultante
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Guarde el documento PDF resultante en el directorio especificado.

### Código fuente de ejemplo para XPS a PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Crear una instancia del objeto LoadOption usando la opción de carga XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Crear objeto de documento
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Guarde el documento PDF resultante
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, aprendimos cómo convertir un archivo XPS a PDF usando la biblioteca Aspose.PDF para .NET. Siguiendo los pasos proporcionados, puede realizar fácilmente esta conversión en sus propias aplicaciones. Obtenga resultados precisos y profesionales al convertir archivos XPS a PDF.

### Preguntas frecuentes

#### P: ¿Qué es XPS y por qué querría convertirlo a PDF?

R: XPS (Especificación de papel XML) es un formato de documento de diseño fijo desarrollado por Microsoft. La conversión de XPS a PDF le permite hacer que el documento sea más accesible y ampliamente compatible, ya que PDF es un formato admitido universalmente en diferentes plataformas y dispositivos.

#### P: ¿La biblioteca Aspose.PDF admite otros formatos de archivo además de XPS?

R: Sí, Aspose.PDF para .NET admite varios otros formatos de archivo para la conversión, como HTML, EPUB, SVG, XML y más. También le permite crear y manipular documentos PDF mediante programación.

#### P: ¿Puedo personalizar el proceso de conversión de PDF, como configurar el tamaño de página, los márgenes u otras opciones?

R: Sí, puede personalizar el proceso de conversión de PDF con Aspose.PDF para .NET. La biblioteca proporciona una amplia gama de opciones para controlar el tamaño de página, los márgenes, la compresión de imágenes, la incrustación de fuentes y otras configuraciones relacionadas con PDF para cumplir con sus requisitos específicos.

#### P: ¿Hay una versión de prueba de Aspose.PDF para .NET disponible para probar?

R: Sí, puede descargar y probar la versión de prueba de Aspose.PDF para .NET desde el sitio web oficial de Aspose. La versión de prueba le permite explorar las funciones de la biblioteca antes de realizar una compra.

#### P: ¿Puedo convertir varios archivos XPS a PDF en un proceso por lotes?

R: Sí, puede convertir varios archivos XPS a PDF en un proceso por lotes implementando un ciclo o iterando a través de la lista de archivos XPS y convirtiendo cada archivo a PDF usando el código proporcionado.