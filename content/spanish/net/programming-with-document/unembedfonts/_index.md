---
title: Desincrustar fuentes y optimizar archivos PDF
linktitle: Desincrustar fuentes y optimizar archivos PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar Aspose.PDF para .NET para desintegrar fuentes y optimizar archivos PDF. Una guía paso a paso.
type: docs
weight: 370
url: /es/net/programming-with-document/unembedfonts/
---
Aspose.PDF para .NET es una potente biblioteca que proporciona una amplia gama de funciones para trabajar con documentos PDF. Una de sus características es desintegrar fuentes de un documento PDF. Esto puede resultar útil si necesita extraer fuentes de un documento PDF y utilizarlas en otras aplicaciones.

Proporcionaremos una guía paso a paso para explicar el siguiente código fuente C# de la función de desintegración de fuentes de Aspose.PDF para .NET.

## Paso 1: establezca la ruta al directorio de documentos

Antes de comenzar, debemos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Almacenaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 2: abra el documento PDF

 El primer paso es cargar el documento PDF que deseas hacer, utiliza el`Document` clase de Aspose.PDF para .NET. El siguiente fragmento de código muestra cómo cargar el documento PDF:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 3: configure la opción UnembedFonts

 Para obtener fuentes no incrustadas del documento PDF, debe configurar el`UnembedFonts` opción de`true` . Esta opción está disponible en el`OptimizationOptions` clase. El siguiente fragmento de código muestra cómo configurar el`UnembedFonts` opción:

```csharp
// Establecer la opción UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Paso 4: Optimice el documento PDF

 Después de configurar el`UnembedFonts` opción, puede optimizar el documento PDF utilizando la`OptimizeResources` método de la`Document` clase. El siguiente fragmento de código muestra cómo optimizar el documento PDF:

```csharp
// Optimice el documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 5: guarde el documento actualizado

 Una vez que el documento PDF esté optimizado, puede guardar el documento actualizado usando el`Save` método de la`Document`clase. El siguiente fragmento de código muestra cómo guardar el documento actualizado:

```csharp
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Paso 6: obtenga el tamaño de archivo original y reducido

 Finalmente, puede obtener el tamaño de archivo original y reducido del documento PDF utilizando el`FileInfo` clase de System.IO. El siguiente fragmento de código muestra cómo obtener el tamaño de archivo original y reducido:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Código fuente de ejemplo para obtener fuentes incrustadas usando Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para obtener fuentes no incrustadas de un documento PDF usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Establecer la opción UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimice el documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusión

En este tutorial, demostramos cómo usar Aspose.PDF para .NET para desintegrar fuentes de un documento PDF. Si sigue la guía paso a paso, podrá implementar fácilmente esta característica en sus aplicaciones C#. Desincrustar fuentes puede resultar ventajoso cuando necesita trabajar con las fuentes extraídas por separado o garantizar un uso coherente de las fuentes en varias plataformas.

## Preguntas frecuentes

#### P: ¿Cuál es el propósito de eliminar fuentes de un documento PDF?

R: Desincrustar fuentes de un documento PDF le permite extraer las fuentes incrustadas y usarlas en otras aplicaciones. Esto puede resultar útil para garantizar una representación de fuentes coherente y preservar la apariencia visual del documento.

#### P: ¿Cómo especifico la ruta al directorio de documentos en el código C#?

 R: Para especificar la ruta al directorio de documentos, reemplace`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta real al directorio donde se encuentra su documento PDF.

####  P: ¿Qué significa el`UnembedFonts` option do, and where is it set?

 R: El`UnembedFonts` opción, disponible en el`OptimizationOptions` clase, habilita o deshabilita la desincrustación de fuentes del documento PDF. Para configurar esta opción en`true`, utilice el siguiente código:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: ¿Puedo revertir los cambios realizados durante el proceso de optimización?

R: Aspose.PDF para .NET no realiza cambios permanentes en el documento PDF original durante la optimización. El proceso de optimización se realiza sobre una copia del documento, dejando intacto el original.

#### P: ¿Cómo puedo verificar el tamaño del archivo original y reducido después de la optimización?

R: Puedes usar el`FileInfo` clase de`System.IO` para obtener el tamaño de archivo original y reducido. Aquí hay un fragmento de código de ejemplo para lograr esto:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```