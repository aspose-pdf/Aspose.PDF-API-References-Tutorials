---
title: Convertir de RGB a escala de grises
linktitle: Convertir de RGB a escala de grises
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a convertir archivos PDF de RGB a escala de grises con Aspose.PDF para .NET. Mejore la calidad de impresión y reduzca el tamaño del archivo.
type: docs
weight: 60
url: /es/net/programming-with-document/convertfromrgbtograyscale/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un documento PDF de espacio de color RGB a escala de grises usando Aspose.PDF para .NET. Esta conversión puede ser útil para varios propósitos, como reducir el tamaño del archivo o preparar documentos para imprimir. Siga la guía paso a paso a continuación:

## Paso 1: Cargue el archivo PDF de origen

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // Tu código aquí...
}
```

## Paso 2: Establezca la estrategia de conversión

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## Paso 3: Convierte cada página a escala de grises

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## Paso 4: Guarde el archivo resultante

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

¡Felicidades! Ha convertido con éxito el documento PDF de RGB a escala de grises utilizando Aspose.PDF para .NET.

### Ejemplo de código fuente para convertir de RGB a escala de grises usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar archivo PDF de origen
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

Ahora puede convertir fácilmente sus documentos PDF de RGB a escala de grises usando Aspose.PDF para .NET.

