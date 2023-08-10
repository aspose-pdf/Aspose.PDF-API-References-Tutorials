---
title: Establecer fuente predeterminada en archivo PDF
linktitle: Establecer fuente predeterminada en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar la fuente predeterminada en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 280
url: /es/net/programming-with-document/setdefaultfont/
---
Si está trabajando con documentos PDF en .NET, es posible que encuentre problemas en los que la fuente utilizada en el PDF no esté disponible en el sistema donde se está viendo o imprimiendo. Esto puede resultar en que el texto aparezca incorrectamente o no aparezca en absoluto. Aspose.PDF para .NET ofrece una solución a este problema al permitirle establecer una fuente predeterminada para el documento. En este ejemplo, cómo configurar la fuente predeterminada usando Aspose.PDF para .NET.

## Paso 1: establezca la ruta al directorio del documento

necesitamos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Guardaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento PDF

 Comenzaremos cargando un documento PDF existente al que le faltan fuentes. En este ejemplo, supondremos que el documento PDF se encuentra en el directorio especificado por el`dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // el código va aquí
}
```

## Paso 3: establece la fuente predeterminada

 A continuación, estableceremos la fuente predeterminada para el documento PDF usando el`PdfSaveOptions` clase. En este ejemplo, estableceremos la fuente predeterminada en "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Paso 4: Guarde el documento actualizado

Finalmente, guardaremos el documento actualizado en un archivo nuevo. En este ejemplo, guardaremos el documento actualizado en un archivo llamado "output_out.pdf" en el mismo directorio que el archivo de entrada.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Ejemplo de código fuente para establecer la fuente predeterminada usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue un documento PDF existente al que le falta la fuente
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Especificar nombre de fuente predeterminado
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusión

Establecer una fuente predeterminada en documentos PDF usando Aspose.PDF para .NET es una forma simple y efectiva de garantizar que el texto se muestre correctamente, incluso si las fuentes originales no están disponibles. Al seguir la guía paso a paso y usar el código fuente de C# proporcionado, los desarrolladores pueden configurar fácilmente la fuente predeterminada y crear archivos PDF que ofrezcan una experiencia de visualización consistente y confiable en diferentes entornos. Esta característica es particularmente útil en escenarios donde los archivos PDF se verán o imprimirán en varios sistemas que pueden tener instalados diferentes conjuntos de fuentes.

### Preguntas frecuentes para establecer la fuente predeterminada en el archivo PDF

#### P: ¿Por qué es importante establecer una fuente predeterminada en los documentos PDF?

R: La configuración de una fuente predeterminada en los documentos PDF es importante porque garantiza que el texto se muestre correctamente incluso si las fuentes originales no están disponibles en el sistema donde se visualiza o imprime el PDF. Ayuda a evitar problemas como texto faltante o ilegible, lo que garantiza una experiencia de visualización consistente y confiable.

#### P: ¿Puedo elegir cualquier fuente como fuente predeterminada usando Aspose.PDF para .NET?

 R: Sí, puede elegir cualquier fuente que esté disponible en el sistema como fuente predeterminada utilizando Aspose.PDF para .NET. Simplemente especifique el nombre de la fuente en el`DefaultFontName` propiedad de la`PdfSaveOptions` clase.

#### P: ¿Qué sucede si la fuente predeterminada especificada no está disponible en el sistema?

R: Si la fuente predeterminada especificada no está disponible en el sistema, el visor de PDF utilizará una fuente alternativa para mostrar el texto. Es recomendable elegir una fuente comúnmente disponible como Arial o Times New Roman para garantizar la compatibilidad entre diferentes sistemas.