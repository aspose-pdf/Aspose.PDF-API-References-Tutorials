---
title: Extraer información de la firma
linktitle: Extraer información de la firma
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer firmas digitales e información de certificados de documentos PDF con Aspose.PDF para .NET. Una guía completa paso a paso para desarrolladores de C#.
type: docs
weight: 80
url: /es/net/programming-with-security-and-signatures/extract-signature-info/
---
## Introducción

En el mundo digital actual, garantizar la seguridad e integridad de los documentos es crucial. Uno de los métodos más comunes que se utilizan para proteger los archivos PDF es agregar una firma digital. Sin embargo, recuperar y verificar los detalles de la firma a veces puede ser un desafío, especialmente cuando se trata de varios certificados. En esta guía, lo guiaremos a través del proceso de extracción de información de firma de documentos PDF con Aspose.PDF para .NET, lo que hará que la tarea sea muy sencilla. Aprenderá a acceder a los campos de firma, extraer información del certificado y guardarla en un archivo.

## Prerrequisitos

Antes de comenzar, asegurémonos de que tienes todo listo para comenzar.

-  Biblioteca Aspose.PDF para .NET: Si aún no la tienes, puedes descargarla desde la[Página de descarga de Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/). 
- Entorno de desarrollo .NET: necesitará un IDE como Visual Studio.
- Conocimientos básicos de C#: estar familiarizado con C# es útil para comprender los fragmentos de código de este tutorial.
- Documento PDF con firma digital: para fines de prueba, asegúrese de tener un archivo PDF que contenga al menos una firma digital.

## Importación de los espacios de nombres necesarios

Antes de comenzar con el código, es importante importar los espacios de nombres necesarios. Estos espacios de nombres le permitirán acceder a la funcionalidad de Aspose.PDF y trabajar con documentos PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Ahora que ha configurado lo esencial, pasemos al proceso real de extracción de información de firma de un PDF.

## Paso 1: Configuración del directorio de documentos

 Antes de trabajar en un documento PDF, debe especificar la ubicación del archivo que utilizará. Puede reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real del directorio donde se almacenan sus PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Aquí especificamos el directorio que contiene el archivo PDF y el nombre del archivo. ¡Asegúrate de que el archivo exista en ese directorio!

## Paso 2: Cargar el documento PDF

 Ahora que ha configurado su directorio, el siguiente paso es cargar el documento PDF utilizando el`Document` clase de Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Procese el PDF aquí.
}
```

 Esta línea de código inicializa una`Document`objeto que representa el archivo PDF.`using` La declaración garantiza que los recursos se limpien después de procesar el documento.

## Paso 3: Acceder a los campos del formulario

En este paso, recorreremos todos los campos de formulario del documento PDF. Dado que las firmas suelen almacenarse como campos de formulario, este paso nos ayudará a identificar los campos de firma.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identifique los campos de firma aquí.
}
```

 Al iterar a través de la`Form` propiedad de la`Document` objeto, podemos examinar cada campo de formulario para verificar si es un campo de firma.

## Paso 4: Identificación de los campos de firma

 Una vez que haya accedido a los campos del formulario, el siguiente paso es identificar cuáles son campos de firma. Podemos hacer esto convirtiendo cada campo en un`SignatureField` objeto.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Extraer información de la firma.
}
```

 Aquí usamos el`as` Palabra clave para intentar convertir cada campo de formulario a un`SignatureField`Si el lanzamiento es exitoso, sabemos que el campo es una firma.

## Paso 5: Extracción del certificado

Ahora que ha identificado el campo de firma, la siguiente tarea es extraer el certificado de la firma. Los certificados contienen información crucial sobre el firmante y la validez de la firma.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 El`ExtractCertificate` El método devuelve un`Stream` objeto que contiene los datos del certificado. Esta secuencia se puede utilizar para guardar el certificado para su posterior análisis o almacenamiento.

## Paso 6: Guardar el certificado en un archivo

 Una vez que haya extraído el certificado, el paso final es guardarlo en un archivo. En este caso, guardaremos el certificado como un archivo`.cer` archivo.

```csharp
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

En este bloque de código, nosotros:

1. Compruebe si el flujo del certificado no es nulo.
2. Leer los datos del certificado en una matriz de bytes.
3.  Escribe la matriz de bytes en un`.cer` archivo en el directorio de documentos.

## Conclusión

Extraer firmas digitales y la información de certificado relacionada de documentos PDF con Aspose.PDF para .NET es bastante sencillo si se divide en pasos simples. Ya sea que esté auditando documentos, verificando firmas o simplemente almacenando certificados para su custodia, este tutorial le proporciona los conocimientos necesarios para hacerlo de manera eficiente. Recuerde que proteger y verificar documentos es fundamental en el mundo digital actual, y el uso de herramientas como Aspose.PDF para .NET hace que sea mucho más fácil de manejar.

## Preguntas frecuentes

### ¿Puedo extraer varias firmas de un PDF usando Aspose.PDF para .NET?
Sí, el código recorre todos los campos de formulario del documento, lo que le permite extraer múltiples firmas si existen.

### ¿Qué sucede si no se encuentra ninguna firma en el PDF?
Si no hay campos de firma presentes, el código simplemente los omitirá sin generar un error.

### ¿Puedo utilizar este enfoque para verificar la validez de una firma?
Si bien es posible extraer el certificado, verificar la validez de una firma requiere pasos adicionales, como verificar la cadena de confianza del certificado.

### ¿Es posible extraer otros datos de campos de formulario utilizando Aspose.PDF para .NET?
Sí, Aspose.PDF le permite acceder y manipular varios tipos de campos de formulario en un PDF, no solo campos de firma.

### ¿Cómo puedo ver los detalles del certificado extraído?
 Una vez que el certificado se guarda como`.cer` archivo, puede abrirlo usando cualquier visor de certificados o importarlo a un almacén de certificados del sistema para una inspección más detallada.