---
title: Está protegido por contraseña
linktitle: Está protegido por contraseña
second_title: Referencia de API de Aspose.PDF para .NET
description: Compruebe fácilmente si un documento PDF está protegido con contraseña con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-security-and-signatures/is-password-protected/
---

menudo es importante saber si un documento PDF está protegido con contraseña antes de procesarlo. Con Aspose.PDF para .NET, puede verificar fácilmente si un documento PDF está protegido utilizando el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea verificar. Reemplazar`"YOUR DOCUMENTS DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Cargue el documento PDF de origen

Ahora cargaremos el documento PDF de origen y comprobaremos si está protegido con contraseña utilizando el siguiente código:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## Paso 4: Comprueba si el PDF está protegido

 En este paso, determinaremos si el documento PDF está protegido con contraseña usando el`IsEncrypted` metodo de la`PdfFileInfo` objeto. Aquí está el código correspondiente:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## Paso 5: Ver el estado del cifrado

 Finalmente, podemos mostrar el estado de cifrado actual del PDF usando el`Console.WriteLine` método. Aquí está el código correspondiente:

```csharp
Console.WriteLine(encrypted.ToString());
```

El mensaje que se muestra indicará si el documento PDF está protegido con contraseña o no.

### Ejemplo de código fuente para ¿Está protegido con contraseña usando Aspose.PDF para .NET? 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el documento PDF de origen
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Determinar que el archivo PDF de origen está cifrado con contraseña
bool encrypted = fileInfo.IsEncrypted;
// MessageBox muestra el estado actual relacionado con el cifrado de PDF
Console.WriteLine(encrypted.ToString());
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para verificar si un documento PDF está protegido con contraseña usando Aspose.PDF para .NET. Puede integrar este código en sus propios proyectos para realizar operaciones específicas según el estado de protección del PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de administración de contraseñas y seguridad de documentos PDF.