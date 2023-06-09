---
title: descifrar
linktitle: descifrar
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a descifrar archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-security-and-signatures/decrypt/
---

En este tutorial, lo guiaremos a través del proceso de descifrado de un archivo PDF usando Aspose.PDF para .NET. Esta biblioteca le permite abrir un archivo PDF existente, descifrarlo y guardar la versión actualizada. Esta característica es útil cuando necesita eliminar la contraseña de un archivo PDF para facilitar el acceso.

## Paso 1: Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#
- Instalación de Visual Studio en su máquina
- Biblioteca Aspose.PDF para .NET instalada

## Paso 2: configuración del entorno

Para comenzar, siga estos pasos para configurar su entorno de desarrollo:

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Instale la biblioteca Aspose.PDF para .NET mediante el administrador de paquetes NuGet.
3. Importe los espacios de nombres requeridos en su archivo de código:

```csharp
using Aspose.Pdf;
```

## Paso 3: Abrir el documento PDF

El primer paso es abrir el documento PDF que desea descifrar. En este ejemplo, asumimos que tiene un archivo PDF llamado "Decrypt.pdf" en el directorio especificado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "Decrypt.pdf", "password");
```

Asegúrese de reemplazar los marcadores de posición con las ubicaciones reales y las contraseñas que desea usar.

## Paso 4: Descifrado de PDF

Una vez que haya abierto el documento PDF, puede descifrarlo usando el`Decrypt` método. No se requieren parámetros para este método.

```csharp
document. Decrypt();
```

## Paso 5: Guardar PDF actualizado

 Después de descifrar el PDF, debe guardar la versión actualizada del documento. Especifique la ruta del archivo de salida y use el`Save` método para guardar el documento.

```csharp
dataDir = dataDir + "Decrypt_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

El PDF actualizado se guardará en la ubicación especificada.

### Ejemplo de código fuente para Decrypt usando Aspose.PDF para .NET 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "Decrypt.pdf", "password");
// Descifrar PDF
document.Decrypt();
dataDir = dataDir + "Decrypt_out.pdf";
// Guardar PDF actualizado
document.Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha descifrado con éxito un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso desde abrir el documento hasta guardar la versión actualizada. Ahora puede usar esta función para eliminar contraseñas de sus archivos PDF.