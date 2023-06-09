---
title: cifrar
linktitle: cifrar
second_title: Referencia de API de Aspose.PDF para .NET
description: Cifre de forma segura sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-security-and-signatures/encrypt/
---

El cifrado de archivos PDF es una medida de seguridad importante para proteger la información confidencial. Con Aspose.PDF para .NET puede cifrar fácilmente sus archivos PDF utilizando el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí están las directivas de importación necesarias:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que se cifrará. Reemplazar`"YOUR DOCUMENTS DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 3: Abra el documento PDF

A continuación, debe abrir el documento PDF que desea cifrar. Use el siguiente código para cargar el documento:

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## Paso 4: Cifrar PDF

Ahora puedes encriptar el PDF usando el siguiente código:

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

En este ejemplo, estamos utilizando el algoritmo de cifrado RC4x128 con las contraseñas de "usuario" y "propietario". Puede cambiar esta configuración según sea necesario.

## Paso 5: copia de seguridad de PDF cifrado

Finalmente, puede guardar el PDF encriptado en la ubicación especificada usando el siguiente código:

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Asegúrese de especificar la ruta y el nombre de archivo deseados para el PDF cifrado.

### Ejemplo de código fuente para Encrypt usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "Encrypt.pdf");
// Cifrar PDF
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Guardar PDF actualizado
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una descripción general paso a paso del cifrado de archivos PDF con Aspose.PDF para .NET. Puede incrustar este código en sus propios proyectos para proteger sus archivos PDF con facilidad.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre funciones avanzadas de cifrado y seguridad.