---
title: Firmar digitalmente con sello de tiempo en archivo PDF
linktitle: Firmar digitalmente con sello de tiempo en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a firmar digitalmente un PDF con una marca de tiempo mediante Aspose.PDF para .NET. Esta guía paso a paso cubre los requisitos previos, la configuración del certificado, la marca de tiempo y más.
type: docs
weight: 50
url: /es/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Introducción

¿Alguna vez ha necesitado firmar digitalmente un PDF e incluir una marca de tiempo para mayor seguridad? Ya sea que esté trabajando en documentos legales, contratos o cualquier cosa que requiera autenticación segura, una firma digital con una marca de tiempo agrega una capa adicional de credibilidad. En este tutorial, desglosaremos cómo puede usar Aspose.PDF para .NET para agregar una firma digital junto con una marca de tiempo a sus documentos PDF. ¡No se preocupe, lo explicaremos paso a paso!

## Prerrequisitos

Antes de sumergirnos en el código, hay algunas cosas que deberás configurar para seguir adelante. Aquí tienes una lista de verificación rápida de los requisitos previos para comenzar:

-  Biblioteca Aspose.PDF para .NET: necesitará la biblioteca Aspose.PDF para .NET instalada en su proyecto. Puede[Descargue la última versión aquí](https://releases.aspose.com/pdf/net/) o agréguelo a su proyecto a través de NuGet.
- Un documento PDF: necesitarás un archivo PDF de muestra con el que trabajar. Asegúrate de tener un archivo en el directorio de tu proyecto que quieras firmar.
-  Certificado digital (archivo PFX): asegúrese de tener un certificado digital (un`.pfx` archivo) para firmar digitalmente el documento.
- URL de sellado de tiempo: este es un servicio de sellado de tiempo en línea que se utilizará para adjuntar una marca de tiempo a la firma digital. 
- Conocimientos básicos de C#: no es necesario ser un experto, pero conocer los conceptos básicos de C# le ayudará a comprender y personalizar el código.

¡Una vez que hayas marcado todas estas casillas, estarás listo para comenzar a codificar!

## Importar paquetes

Para comenzar, deberá importar los siguientes espacios de nombres a su proyecto de C#. Esto le garantizará acceso a las clases y funciones Aspose.PDF relevantes.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Paso 1: Cargue el documento PDF

Lo primero que tenemos que hacer es cargar el documento PDF que queremos firmar. Para ello, lo hacemos de la siguiente manera:

```csharp
// Define la ruta al directorio de tus documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Este paso es bastante sencillo. Simplemente estamos definiendo la ruta al documento que queremos firmar.`Document` La clase de Aspose.PDF maneja la carga del archivo.

## Paso 2: Configurar la firma digital

A continuación, crearemos la firma digital utilizando la clase PKCS7 y cargaremos el archivo PFX. Este archivo PFX contiene su certificado y clave privada, que son necesarios para firmar el documento.

```csharp
// Ruta a su archivo .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Inicializar el objeto de firma
PdfFileSignature signature = new PdfFileSignature(document);

// Cargue el archivo PFX con una contraseña
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 En este punto, le estás indicando a Aspose que use tu certificado digital para firmar el documento.`PKCS7`object se encarga de todo el trabajo criptográfico para que usted no tenga que preocuparse por los detalles esenciales.

## Paso 3: Agregar la configuración de la marca de tiempo

Uno de los componentes clave de una firma digital sólida es el sello de tiempo. Esto garantiza que la firma del documento pueda verificarse incluso después de que el certificado haya expirado. Configuremos el sello de tiempo utilizando una autoridad de sellado de tiempo en línea.

```csharp
// Definir la configuración de la marca de tiempo
TimestampSettings timestampSettings = new TimestampSettings("https://su_url_de_marca_de_tiempo", "usuario:contraseña");

// Agregar configuraciones de marca de tiempo al objeto PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Aquí, se especifica la URL del servicio de sellado de tiempo, que proporcionará automáticamente una fecha y hora a la firma. Esto se puede hacer con o sin autenticación.

## Paso 4: Definir la ubicación y apariencia de la firma

Ahora definiremos dónde aparecerá la firma en el PDF y sus dimensiones. Puedes personalizar la posición del recuadro de la firma en la página, así como su tamaño.

```csharp
//Defina la apariencia y la ubicación de la firma (página 1, con el rectángulo especificado)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Aquí, definimos un rectángulo que posiciona la firma en las coordenadas (100, 100) en la primera página del PDF, con un ancho de 200 y una altura de 100. Puedes cambiar estos valores para que se ajusten a tu diseño.

## Paso 5: Firma el documento PDF

Una vez que todo está configurado, es momento de aplicar la firma digital al PDF. Este paso combina el certificado, la marca de tiempo y la posición en un solo comando simple.

```csharp
// Firme el documento en la primera página
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Esto es lo que está pasando:
- 1: Esto indica que la firma debe aplicarse en la primera página.
- "Motivo de la firma": aquí puede especificar por qué está firmando el documento.
- “Contacto”: Ingrese los datos de contacto del firmante.
- "Ubicación": especifique la ubicación del firmante.
- verdadero: este valor booleano indica si la firma es visible en el documento.
- rect: El rectángulo que definimos anteriormente especifica el tamaño y la posición de la firma.
- pkcs: El objeto PKCS7 contiene el certificado digital y la configuración de la marca de tiempo.

## Paso 6: Guarde el PDF firmado

Una vez firmado el documento, solo queda guardarlo. Puedes elegir un nuevo nombre de archivo para conservar tanto la versión original como la firmada.

```csharp
// Guardar el documento PDF firmado
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

¡Su PDF recién firmado y con marca de tiempo ahora está guardado en el directorio especificado!

## Conclusión

¡Y ya está! Has firmado digitalmente un PDF con una marca de tiempo usando Aspose.PDF para .NET. Este proceso garantiza la autenticidad e integridad de tus documentos, lo que te da tranquilidad a ti y al destinatario. Las firmas digitales son cada vez más esenciales en el mundo digital actual, por lo que dominar este proceso es definitivamente una habilidad que vale la pena tener.

## Preguntas frecuentes

### ¿Puedo utilizar un formato de archivo diferente para el certificado?  
Sí, pero el tutorial se centra en el uso de un archivo PFX, que es el formato más común para certificados digitales.

### ¿Necesito una conexión a Internet para aplicar la marca de tiempo?  
Sí, dado que la marca de tiempo se obtiene de una autoridad de sellado de tiempo en línea, necesitará acceso a Internet.

### ¿Puedo firmar varias páginas en un PDF?  
 ¡Por supuesto! Puedes modificar el`signature.Sign()` método para apuntar a varias páginas o recorrer todas las páginas.

### ¿Qué sucede si la contraseña del archivo PFX es incorrecta?  
Recibirás una excepción si la contraseña es incorrecta, así que asegúrate de ingresarla correctamente.

### ¿Puedo hacer la firma invisible?  
 Sí, puedes pasar`false` hacia`Sign` parámetro de visibilidad del método para hacer la firma invisible.