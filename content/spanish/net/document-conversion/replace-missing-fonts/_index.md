---
title: Reemplazar fuentes faltantes
linktitle: Reemplazar fuentes faltantes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar fuentes faltantes en documentos PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 260
url: /es/net/document-conversion/replace-missing-fonts/
---
## Introducción

¿Alguna vez ha abierto un documento PDF y se ha dado cuenta de que faltan algunas fuentes? Puede resultar frustrante, ¿verdad? La falta de fuentes puede hacer que el documento tenga un aspecto completamente distinto al que pretendía el creador. Afortunadamente, con Aspose.PDF para .NET, puede reemplazar fácilmente las fuentes faltantes y asegurarse de que sus documentos PDF mantengan el aspecto deseado. En este tutorial, le guiaremos paso a paso por el proceso, haciéndolo sencillo y directo.

## Prerrequisitos

Antes de comenzar, hay algunas cosas que deberá tener en cuenta:

1.  Aspose.PDF para .NET: Asegúrese de tener instalada la biblioteca Aspose.PDF. Puede descargarla desde[aquí](https://releases.aspose.com/pdf/net/).
2. Visual Studio: un entorno de desarrollo donde puedes escribir y probar tu código.
3. Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.

## Importar paquetes

Para comenzar, deberá importar los paquetes necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 1: Configurar el directorio de documentos

En primer lugar, debe especificar la ruta al directorio de sus documentos. Aquí se encuentra el archivo PDF de entrada y donde se guardará el archivo de salida.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Inicializar la fuente original

A continuación, deberás intentar encontrar la fuente original que podría faltar. En este caso, buscamos "AgencyFB".

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    //Falta la fuente en la máquina de destino
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Aquí, intentamos encontrar la fuente. Si no la encontramos, detectamos la excepción y la sustituimos por una fuente más común, "Arial". Esto garantiza que el documento se vea bien incluso si la fuente original no está disponible.

## Paso 3: Cargue el documento PDF

Ahora, carguemos el documento PDF que desea procesar. Deberá especificar la ruta del archivo de entrada.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 En este paso, creamos un nuevo`FileInfo` objeto para el archivo de salida y cargar el documento PDF de entrada en un nuevo`Document` objeto.

## Paso 4: Convertir el documento PDF

Antes de guardar el documento, es buena idea convertirlo a un formato PDF específico. En este caso, lo convertiremos al formato PDF/A-1B, que es un estándar para el archivado a largo plazo de documentos electrónicos.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Esta línea convierte el PDF y registra los errores en un archivo XML específico. Si hay algún problema durante la conversión, se registrará en "log.xml".

## Paso 5: Guarde el documento PDF actualizado

Finalmente, es el momento de guardar el documento PDF actualizado con las fuentes reemplazadas.

```csharp
pdf.Save(fileNew.FullName);
```

Esta línea guarda el PDF modificado en la ruta de archivo de salida especificada. ¡Y así, habrá reemplazado con éxito las fuentes faltantes en su documento PDF!

## Conclusión

Reemplazar fuentes faltantes en documentos PDF no tiene por qué ser una tarea abrumadora. Con Aspose.PDF para .NET, puede administrar fácilmente las sustituciones de fuentes y garantizar que sus documentos tengan el aspecto que deberían. Si sigue los pasos que se describen en este tutorial, podrá mantener la integridad de sus archivos PDF, incluso cuando ciertas fuentes no estén disponibles. De este modo, la próxima vez que se encuentre con un problema de fuente faltante, sabrá exactamente qué hacer.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
 Sí, Aspose ofrece una versión de prueba gratuita que puedes usar para evaluar la biblioteca. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Qué debo hacer si la fuente que necesito no está disponible?
Puede sustituir la fuente faltante por una más común utilizando la función de sustitución de fuentes en Aspose.PDF.

### ¿Es posible convertir archivos PDF a otros formatos?
¡Por supuesto! Aspose.PDF admite la conversión a varios formatos, incluidos PDF/A, DOCX y más.

### ¿Dónde puedo encontrar soporte para Aspose.PDF?
 Puede encontrar ayuda y hacer preguntas en el foro de Aspose[aquí](https://forum.aspose.com/c/pdf/10).