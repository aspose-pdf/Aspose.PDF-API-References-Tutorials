---
title: PDF a SVG
linktitle: PDF a SVG
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para convertir PDF a SVG usando Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/document-conversion/pdf-to-svg/
---
En este tutorial, lo guiaremos a través del proceso de convertir un PDF a formato SVG usando Aspose.PDF para .NET. SVG (Scalable Vector Graphics) es un formato de imagen vectorial que ayuda a mantener la calidad y el escalado de los gráficos. Siguiendo los pasos a continuación, podrá convertir un archivo PDF al formato SVG.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargar el documento PDF
En este paso cargaremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: creación de instancias de las opciones de guardado de SVG
Después de cargar el archivo PDF, crearemos una instancia de las opciones de guardado de SVG. Utilice el siguiente código:

```csharp
// Crear una instancia de un objeto SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// No comprima la imagen SVG en un archivo Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Paso 3: guardar el archivo SVG resultante
Ahora guardaremos el archivo PDF convertido en formato SVG. Utilice el siguiente código:

```csharp
// Guardar la salida en archivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 El código anterior guarda el PDF convertido a formato SVG con el nombre del archivo`"PDFToSVG_out.svg"`.

### Código fuente de ejemplo para PDF a SVG usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document doc = new Document(dataDir + "input.pdf");
// Crear una instancia de un objeto de SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// No comprima la imagen SVG en un archivo Zip
saveOptions.CompressOutputToZipArchive = false;
// Guarde la salida en archivos SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato SVG usando Aspose.PDF para .NET. Si sigue las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF al formato SVG. Esta función es útil cuando desea mantener la calidad y la escala de los gráficos al convertir a imágenes vectoriales.

### Preguntas frecuentes

#### P: ¿Puedo controlar la resolución o el tamaño de los archivos SVG resultantes durante la conversión de PDF a SVG?

 R: Sí, puede controlar la resolución o el tamaño de los archivos SVG resultantes durante la conversión de PDF a SVG usando Aspose.PDF para .NET. El`SvgSaveOptions` clase proporciona propiedades como`PageSavingCallback` y`SaveFormat` que le permiten configurar la resolución, el tamaño de página u otros parámetros relacionados con la salida SVG. Puede personalizar estas opciones según sus requisitos para controlar la calidad y el tamaño de los archivos SVG.

#### P: ¿Aspose.PDF para .NET admite la conversión de archivos PDF cifrados o protegidos con contraseña a SVG?

R: Sí, Aspose.PDF para .NET admite la conversión de archivos PDF cifrados o protegidos con contraseña al formato SVG. Cuando carga un PDF protegido con contraseña, puede proporcionar la contraseña utilizando el`Document` constructor de clase o estableciendo el`Password` propiedad antes de cargar el PDF. Aspose.PDF para .NET se encargará del descifrado durante el proceso de conversión de PDF a SVG.

#### P: ¿Puedo convertir sólo páginas específicas del PDF a SVG en lugar del documento completo?

R: Sí, puede convertir solo páginas específicas del PDF a SVG en lugar de todo el documento usando Aspose.PDF para .NET. Antes de guardar el resultado como archivos SVG, puede seleccionar las páginas que desea convertir especificando sus números de página o rangos. De esta manera, puede extraer y convertir solo las páginas deseadas del formato PDF a SVG.

#### P: ¿Aspose.PDF para .NET es compatible con todas las versiones de SVG?

R: Aspose.PDF para .NET está diseñado para ser compatible con la especificación SVG 1.1 (Gráficos vectoriales escalables). Admite la generación de archivos SVG según el estándar SVG 1.1. Sin embargo, tenga en cuenta que SVG 2.0 se introdujo como la última versión de la especificación SVG. Si bien Aspose.PDF para .NET aún puede funcionar bien con SVG 2.0 en muchos casos, se recomienda verificar la compatibilidad y las posibles limitaciones con las funciones SVG específicas que desea utilizar.