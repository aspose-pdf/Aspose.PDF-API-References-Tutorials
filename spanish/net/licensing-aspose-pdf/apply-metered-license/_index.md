---
title: Configurar licencia medida
linktitle: Configurar licencia medida
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar una licencia medida con Aspose.PDF para .NET y beneficiarse de funciones avanzadas.
type: docs
weight: 10
url: /es/net/licensing-aspose-pdf/configure-metered-license/
---

En este tutorial, lo guiaremos paso a paso sobre cómo configurar una licencia medida con Aspose.PDF para .NET. La licencia medida le permite utilizar las funciones avanzadas de Aspose.PDF en función de su consumo real.

### Paso 1: Configuración de claves de licencia

En el código fuente proporcionado, debe especificar las claves pública y privada de la licencia medida. Reemplace la "*****" valores con sus propias claves. Estas claves se le proporcionarán cuando compre una licencia medida de Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Paso 2: Cargar el documento

 Cargue el documento PDF desde el disco usando el`Document`clase de Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Paso 3: obtener el número de páginas del documento

 Utilizar el`Count` propiedad de la`Pages` colección para obtener el número total de páginas del documento.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Ejemplo de código fuente para Configurar licencia medida usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// establecer claves públicas y privadas medidas
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Acceda a la propiedad setMeteredKey y pase claves públicas y privadas como parámetros
metered.SetMeteredKey("*****", "*****");
// Cargue el documento desde el disco.
Document doc = new Document(dataDir + "input.pdf");
//Obtener el número de páginas del documento
Console.WriteLine(doc.Pages.Count);

```

## Conclusión

En este tutorial, explicamos cómo configurar una licencia medida con Aspose.PDF para .NET. Al utilizar una licencia medida, puede beneficiarse de las funciones avanzadas de Aspose.PDF en función de su uso real. Asegúrese de proporcionar claves de licencia válidas para usar Aspose.PDF con todas sus funciones.
