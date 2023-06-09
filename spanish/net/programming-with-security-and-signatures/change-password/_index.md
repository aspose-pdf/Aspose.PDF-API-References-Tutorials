---
title: Cambiar la contraseña
linktitle: Cambiar la contraseña
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a cambiar la contraseña de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-security-and-signatures/change-password/
---

En este tutorial, lo guiaremos a través del proceso de cambio de contraseña de un documento PDF utilizando Aspose.PDF para .NET. La biblioteca le permite abrir un archivo PDF existente, modificar su contraseña y guardar la versión actualizada. Esta función resulta útil cuando necesita proteger sus documentos PDF cambiando la contraseña.

## Paso 1: Requisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#
- Visual Studio instalado en su máquina
- Aspose.PDF para la biblioteca .NET instalada

## Paso 2: Configuración del entorno

Para comenzar, siga estos pasos para configurar su entorno de desarrollo:

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Instale la biblioteca Aspose.PDF para .NET mediante NuGet Package Manager.
3. Importe los espacios de nombres requeridos en su archivo de código:

```csharp
using Aspose.Pdf;
```

## Paso 3: Cargar el documento PDF

El primer paso es cargar el documento PDF para el que desea cambiar la contraseña. En este ejemplo, asumimos que tiene un archivo PDF llamado "ChangePassword.pdf" en el directorio especificado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## Paso 4: Cambiar la contraseña

 Una vez que haya cargado el documento PDF, puede cambiar su contraseña usando el`ChangePasswords`método. El método requiere tres parámetros: la contraseña del propietario actual, la contraseña del nuevo usuario y la contraseña del nuevo propietario.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

Asegúrese de reemplazar los marcadores de posición con las contraseñas reales que desea configurar.

## Paso 5: Guardar el PDF actualizado

 Después de cambiar la contraseña, debe guardar el documento PDF actualizado. Especifique la ruta del archivo de salida y use el`Save` método para guardar el documento.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

El PDF actualizado se guardará en la ubicación especificada.

### Ejemplo de código fuente para Cambiar contraseña usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// Cambiar la contraseña
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// Guardar PDF actualizado
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha cambiado con éxito la contraseña de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso, desde cargar el documento hasta guardar la versión actualizada. Ahora puede utilizar esta función para proteger sus archivos PDF con nuevas contraseñas.