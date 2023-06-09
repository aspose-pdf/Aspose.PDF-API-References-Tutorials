---
title: MCG a PDF
linktitle: MCG a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente archivos CGM a PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/document-conversion/cgm-to-pdf/
---

En este tutorial, lo guiaremos paso a paso para convertir CGM a PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# proporcionado y proporcionaremos instrucciones paso a paso para ayudarlo a seguirlo fácilmente.

## Introducción

La conversión de un archivo CGM a PDF le permite compartir y ver sus dibujos técnicos universalmente. Con Aspose.PDF para .NET, puede realizar fácilmente esta conversión y obtener archivos PDF de alta calidad.

## Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para trabajar con Aspose.PDF para .NET. Siga los pasos a continuación:

1. Instale Visual Studio u otro IDE compatible con el desarrollo de C#.
2. Cree un nuevo proyecto de C#.
3. Instale el paquete Aspose.PDF para .NET a través de NuGet para agregar las dependencias necesarias.

## Convertir archivo CGM a PDF

Para convertir un archivo CGM a PDF, siga estos pasos:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea una instancia de un objeto LoadOption usando CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Crear una instancia de un objeto de documento
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Guarde el documento PDF resultante
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 En el código anterior, asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real al directorio donde se encuentra su archivo CGM para convertir. Este código carga el archivo CGM usando el`CgmLoadOptions` clase, luego crea un documento PDF usando el`Document` objeto. Finalmente, se guarda el documento PDF resultante.

### Código fuente de ejemplo para CGM a PDF usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea una instancia del objeto LoadOption usando CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instanciar objeto de documento
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Guarde el documento PDF resultante
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Conclusión

¡Felicidades! Ahora sabe cómo convertir un archivo CGM a PDF usando Aspose.PDF para .NET. Hemos pasado por cada paso del proceso, desde inicializar las opciones de carga de CGM hasta guardar el documento PDF resultante. Utilice los ejemplos de código proporcionados para integrar esta funcionalidad en sus propios proyectos. Experimente con Aspose.PDF para .NET y descubra las posibilidades ampliadas que ofrece para manipular archivos PDF.
