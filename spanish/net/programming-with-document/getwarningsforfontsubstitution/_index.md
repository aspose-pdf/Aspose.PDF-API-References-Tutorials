---
title: Obtenga advertencias para la sustitución de fuentes
linktitle: Obtenga advertencias para la sustitución de fuentes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar la función GetWarningsForFontSubstitution de Aspose.PDF para .NET para detectar advertencias de sustitución de fuentes al abrir un documento PDF.
type: docs
weight: 190
url: /es/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF para .NET es una popular biblioteca de manipulación de PDF que permite a los desarrolladores crear, editar y convertir archivos PDF en sus aplicaciones .NET. Una de las características que ofrece esta biblioteca es la capacidad de detectar advertencias de sustitución de fuentes cuando se abre un documento PDF. Este tutorial lo guiará a través de los pasos para usar el`GetWarningsForFontSubstitution` función de Aspose.PDF para .NET para detectar advertencias de sustitución de fuente al abrir un documento PDF.

## Paso 1: Instale Aspose.PDF para .NET

 Para usar Aspose.PDF para .NET en sus aplicaciones .NET, primero debe instalar la biblioteca. Puede descargar la última versión de la biblioteca desde el[Página de descarga de Aspose.PDF para .NET](https://relases.aspose.com/pdf/net).

Una vez que haya descargado la biblioteca, extraiga el contenido del archivo ZIP en una carpeta de su computadora. Luego deberá agregar una referencia a Aspose.PDF para .NET DLL en su proyecto .NET.

## Paso 2: Cargue el documento PDF

 Una vez que haya instalado Aspose.PDF para .NET y haya agregado una referencia a la DLL en su proyecto .NET, puede comenzar a usar el`GetWarningsForFontSubstitution` función para detectar advertencias de sustitución de fuente al abrir un documento PDF.

El primer paso para usar esta función es cargar el documento PDF para el que desea detectar advertencias de sustitución de fuentes. Para hacer esto, puede usar el siguiente código:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abre el documento PDF
Document doc = new Document(dataDir + "input.pdf");
```

 En el código anterior, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se encuentra su documento PDF. Este código cargará el documento PDF en un`Document` objeto, que luego puede usar para detectar advertencias de sustitución de fuente.

## Paso 3: Detectar advertencias de sustitución de fuentes

Para detectar advertencias de sustitución de fuentes al abrir un documento PDF, puede utilizar el siguiente código:

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

 En el código anterior,`OnFontSubstitution` es un método que se llamará cada vez que se detecte una advertencia de sustitución de fuente. Puede personalizar este método para manejar la advertencia de sustitución de fuente de la forma que desee.

 Aquí hay un ejemplo de implementación del`OnFontSubstitution` método:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

 En el código anterior, el`OnFontSubstitution` El método simplemente envía el nombre de la fuente original y el nombre de la fuente sustituida a la consola cada vez que se detecta una advertencia de sustitución de fuente. Puede personalizar este método para manejar la advertencia de sustitución de fuente de la forma que desee.

### Código fuente de ejemplo para Obtener advertencias para la sustitución de fuentes usando Aspose.NET para PDF

 Aquí está el código fuente completo para detectar advertencias de sustitución de fuentes al abrir un documento PDF usando el`GetWarningsForFontSubstitution` característica de Aspose.PDF para .NET:

```csharp
// La ruta al documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abre el documento PDF
Document doc = new Document(dataDir + "input.pdf");

// Detectar advertencias de sustitución de fuentes
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// Manejar la advertencia de sustitución de fuente
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```