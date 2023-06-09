---
title: Determinar la contraseña correcta
linktitle: Determinar la contraseña correcta
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a determinar la contraseña correcta para un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-security-and-signatures/determine-correct-password/
---

En este tutorial, lo guiaremos a través del proceso de determinación de la contraseña correcta para un archivo PDF usando Aspose.PDF para .NET. Esta función le permite comprobar si un archivo PDF está protegido con contraseña y encontrar la contraseña correcta en una lista predefinida.

## Paso 1: Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#
- Instalación de Visual Studio en su máquina
- Biblioteca Aspose.PDF para .NET instalada

## Paso 2: configuración del entorno

Para comenzar, siga estos pasos para configurar su entorno de desarrollo:

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Importe los espacios de nombres requeridos en su archivo de código:

```csharp
using Aspose.Pdf;
```

## Paso 3: cargando el archivo PDF de origen

El primer paso es cargar el archivo PDF de origen que desea verificar. En este ejemplo, asumimos que tiene un archivo PDF llamado "IsPasswordProtected.pdf" en el directorio especificado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Asegúrese de reemplazar los marcadores de posición con las ubicaciones reales de su archivo PDF.

## Paso 4: Determinar el cifrado de PDF de origen

 Una vez que haya cargado el archivo PDF de origen, puede determinar si está encriptado usando el`IsEncrypted` metodo de la`PdfFileInfo` objeto.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Esta declaración muestra si el archivo PDF está protegido con contraseña o no.

## Paso 5: encontrar la contraseña correcta

continuación, buscaremos la contraseña correcta utilizando una lista predefinida de contraseñas. Revisamos cada contraseña en la lista e intentamos cargar el documento PDF con esa contraseña.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Este ciclo prueba cada palabra de paso de la lista. Si la contraseña es correcta, se muestra el número de páginas del documento. De lo contrario, se muestra un mensaje que indica que la contraseña no es correcta.


### Ejemplo de código fuente para determinar la contraseña correcta mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Cargar archivo PDF de origen
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Determinar si el PDF de origen está encriptado
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Conclusión

¡Felicidades! Ha determinado con éxito la contraseña correcta para un archivo PDF utilizando Aspose.PDF para .NET. Este tutorial cubrió el proceso paso a paso, desde verificar el cifrado de archivos hasta encontrar la contraseña correcta de una lista predefinida. Ahora puede usar esta función para verificar y encontrar la contraseña correcta de sus archivos PDF.