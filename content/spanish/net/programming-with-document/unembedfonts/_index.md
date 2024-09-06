---
title: Desincrustar fuentes y optimizar archivos PDF
linktitle: Desincrustar fuentes y optimizar archivos PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar Aspose.PDF para .NET para obtener fuentes no incrustadas y optimizar archivos PDF. Una guía paso a paso.
type: docs
weight: 370
url: /es/net/programming-with-document/unembedfonts/
---
Aspose.PDF para .NET es una potente biblioteca que ofrece una amplia gama de funciones para trabajar con documentos PDF. Una de sus funciones es la de extraer fuentes no incrustadas de un documento PDF. Esto puede resultar útil si necesita extraer fuentes de un documento PDF y utilizarlas en otras aplicaciones.

Proporcionaremos una guía paso a paso para explicar el siguiente código fuente de C# de la función de obtención de fuentes no incrustadas de Aspose.PDF para .NET.

## Paso 1: Establezca la ruta al directorio del documento

Antes de comenzar, debemos establecer la ruta del directorio donde se encuentra nuestro documento PDF. Almacenaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 2: Abra el documento PDF

 El primer paso es cargar el documento PDF que desea realizar, utilice el`Document` Clase de Aspose.PDF para .NET. El siguiente fragmento de código muestra cómo cargar el documento PDF:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 3: Establezca la opción UnembedFonts

 Para obtener fuentes no incrustadas del documento PDF, debe configurar la`UnembedFonts` Opción a`true` Esta opción está disponible en el`OptimizationOptions` clase. El siguiente fragmento de código muestra cómo configurar la clase`UnembedFonts` opción:

```csharp
// Establecer la opción UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Paso 4: Optimizar el documento PDF

 Después de configurar el`UnembedFonts` Opción, puede optimizar el documento PDF utilizando la`OptimizeResources` método de la`Document` clase. El siguiente fragmento de código muestra cómo optimizar el documento PDF:

```csharp
// Optimizar un documento PDF mediante OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 5: Guarde el documento actualizado

 Una vez optimizado el documento PDF, puede guardar el documento actualizado utilizando el`Save` método de la`Document`clase. El siguiente fragmento de código muestra cómo guardar el documento actualizado:

```csharp
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Paso 6: Obtenga el tamaño de archivo original y reducido

 Finalmente, puedes obtener el tamaño de archivo original y reducido del documento PDF utilizando el`FileInfo` Clase de System.IO. El siguiente fragmento de código muestra cómo obtener el tamaño de archivo original y reducido:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Código fuente de ejemplo para obtener fuentes no incrustadas con Aspose.PDF para .NET

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
// Optimizar un documento PDF mediante OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusión

En este tutorial, demostramos cómo usar Aspose.PDF para .NET para obtener fuentes no incrustadas de un documento PDF. Si sigue la guía paso a paso, podrá implementar fácilmente esta función en sus aplicaciones C#. La desincrustación de fuentes puede resultar ventajosa cuando necesite trabajar con las fuentes extraídas por separado o garantizar un uso uniforme de las fuentes en varias plataformas.

## Preguntas frecuentes

#### P: ¿Cuál es el propósito de desincrustar fuentes de un documento PDF?

A: Desincrustar fuentes de un documento PDF le permite extraer las fuentes incrustadas y usarlas en otras aplicaciones. Esto puede resultar útil para garantizar una representación uniforme de las fuentes y preservar la apariencia visual del documento.

#### P: ¿Cómo especifico la ruta al directorio del documento en el código C#?

 A: Para especificar la ruta al directorio del documento, reemplace`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta real al directorio donde se encuentra su documento PDF.

####  P: ¿Qué significa el`UnembedFonts` option do, and where is it set?

 A: El`UnembedFonts` opción, disponible en el`OptimizationOptions` clase, habilita o deshabilita la desincrustación de fuentes del documento PDF. Para configurar esta opción en`true`, utilice el siguiente código:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: ¿Puedo revertir los cambios realizados durante el proceso de optimización?

A: Aspose.PDF para .NET no realiza cambios permanentes en el documento PDF original durante la optimización. El proceso de optimización se realiza en una copia del documento, dejando intacto el original.

#### P: ¿Cómo puedo verificar el tamaño del archivo original y reducido después de la optimización?

 A: Puedes utilizar el`FileInfo` clase de`System.IO` Para obtener el tamaño de archivo original y reducido, aquí hay un fragmento de código de ejemplo para lograrlo:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```