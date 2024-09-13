---
title: Recibir advertencias por sustitución de fuentes
linktitle: Recibir advertencias por sustitución de fuentes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar la función GetWarningsForFontSubstitution de Aspose.PDF para .NET para detectar advertencias de sustitución de fuentes al abrir un documento PDF.
type: docs
weight: 190
url: /es/net/programming-with-document/getwarningsforfontsubstitution/
---
## Introducción

En el mundo del procesamiento de documentos, es fundamental garantizar que los archivos PDF tengan el aspecto deseado. ¿Alguna vez ha abierto un PDF y se ha dado cuenta de que las fuentes no son las correctas? Esto puede suceder cuando las fuentes originales utilizadas en el documento no están disponibles en el sistema en el que se visualiza el PDF. Afortunadamente, Aspose.PDF para .NET ofrece una solución sólida para detectar advertencias de sustitución de fuentes, lo que le permite mantener la integridad de sus documentos. En esta guía, le explicaremos los pasos para configurar la detección de sustitución de fuentes en sus documentos PDF mediante Aspose.PDF para .NET.

## Prerrequisitos

Antes de sumergirte en el código, hay algunas cosas que debes tener en cuenta:

1. Visual Studio: asegúrate de tener Visual Studio instalado en tu equipo. Aquí es donde escribirás y ejecutarás tu código .NET.
2.  Aspose.PDF para .NET: Necesita tener la biblioteca Aspose.PDF. Puede descargarla desde el sitio web[sitio](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.
4. Un documento PDF: tenga listo un documento PDF de muestra que pueda usar para probar la detección de sustitución de fuentes.

## Importar paquetes

Para comenzar, debe importar los paquetes necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

### Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de C#. Puede elegir una aplicación de consola para simplificar el proceso.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.PDF" e instale la última versión.

### Importar el espacio de nombres

En la parte superior de su archivo C#, importe el espacio de nombres Aspose.PDF:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ahora que tiene todo configurado, dividamos el proceso de detección de advertencias de sustitución de fuentes en pasos manejables.

## Paso 1: Definir la ruta del documento

En primer lugar, debe especificar la ruta de su documento PDF. Aquí es donde Aspose.PDF buscará el archivo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde se encuentra su archivo PDF.

## Paso 2: Abra el documento PDF

 A continuación, abrirá el documento PDF utilizando el`Document` clase proporcionada por Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Esta línea de código inicializa un nuevo`Document` objeto con su archivo PDF.

## Paso 3: Configurar la detección de sustitución de fuentes

 Ahora es el momento de configurar el controlador de eventos que detectará las advertencias de sustitución de fuentes. Deberá suscribirse a`FontSubstitution` evento de la`Document` clase.

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

Esta línea conecta el evento a su método personalizado, que definiremos a continuación.

## Paso 4: Gestionar las advertencias de sustitución de fuentes

Debe crear un método que se encargue de las advertencias de sustitución de fuentes. Este método se llamará siempre que se produzca una sustitución de fuentes.

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

Con este método, puedes registrar el nombre de la fuente original y el nombre de la fuente sustituida en la consola. De esta manera, sabrás exactamente qué cambios se realizaron.

## Paso 5: Ejecutar el código

Por último, puedes ejecutar tu aplicación. Si hay alguna sustitución de fuentes en tu documento PDF, verás las advertencias impresas en la consola.

## Conclusión

Detectar advertencias de sustitución de fuentes en documentos PDF es esencial para mantener la integridad visual de sus archivos. Con Aspose.PDF para .NET, este proceso es sencillo y eficiente. Si sigue los pasos que se describen en esta guía, podrá configurar fácilmente la detección de sustitución de fuentes y asegurarse de que sus archivos PDF tengan el aspecto que desea.

## Preguntas frecuentes

### ¿Qué es la sustitución de fuentes?
La sustitución de fuentes ocurre cuando la fuente original utilizada en un documento no está disponible y se utiliza una fuente diferente en su lugar.

### ¿Cómo puedo evitar la sustitución de fuentes?
Para evitar la sustitución de fuentes, asegúrese de que todas las fuentes utilizadas en su PDF estén incrustadas en el documento.

### ¿Puedo utilizar Aspose.PDF gratis?
Sí, Aspose.PDF ofrece una prueba gratuita que puedes usar para probar sus funciones.

### ¿Dónde puedo encontrar más documentación?
 Puede encontrar documentación detallada en Aspose.PDF para .NET[aquí](https://reference.aspose.com/pdf/net/).

### ¿Cómo puedo obtener soporte para Aspose.PDF?
 Puede obtener ayuda visitando el sitio[Foro de soporte de Aspose](https://forum.aspose.com/c/pdf/10).