---
title: Agregar y buscar texto oculto en un archivo PDF
linktitle: Agregar y buscar texto oculto en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar y buscar texto oculto en documentos PDF con Aspose.PDF para .NET. Guía paso a paso con ejemplos de código incluidos.
type: docs
weight: 20
url: /es/net/programming-with-text/add-and-search-hidden-text/
---
## Introducción

En este tutorial, le mostraremos paso a paso cómo agregar y buscar texto oculto en un archivo PDF con Aspose.PDF para .NET. Ya sea que sea un desarrollador experimentado o un principiante que busca mejorar sus habilidades de programación, este artículo le brindará la información que necesita para incorporar la función de texto oculto en sus aplicaciones.

## Prerrequisitos

Antes de sumergirnos en la parte de codificación, hay algunos requisitos previos que debes tener en cuenta:

### Lista de verificación de requisitos
- Visual Studio: asegúrese de tener instalado Visual Studio. En este tutorial se supone que está utilizando .NET Framework.
-  Aspose.PDF para .NET: Necesita tener la biblioteca Aspose.PDF para .NET. Puede descargarla[aquí](https://releases.aspose.com/pdf/net/).
- Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.

## Importar paquetes

Antes de comenzar a trabajar con el código, debe asegurarse de importar los espacios de nombres Aspose.PDF necesarios. A continuación, le indicamos cómo hacerlo:

### Configura tu proyecto
1. Abra Visual Studio y cree un nuevo proyecto de C# o utilice uno existente.
2.  Instale Aspose.PDF agregando el paquete NuGet. Puede hacerlo navegando al Administrador de paquetes NuGet y buscando`Aspose.PDF`. 
3.  Alternativamente, puede descargar directamente la biblioteca desde[aquí](https://releases.aspose.com/pdf/net/) y agregarlo como referencia en tu proyecto.

### Importar espacios de nombres requeridos
En la parte superior de su archivo C#, importe los siguientes espacios de nombres:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Este paso es crucial ya que estos espacios de nombres contienen las clases y los métodos necesarios para manipular documentos PDF.

## Cómo crear un documento PDF con texto oculto

Ahora que está configurado, veamos los pasos para crear un documento PDF que contenga texto visible e invisible.

### Paso 1: Definir el directorio de documentos
En primer lugar, deberás configurar la ruta en la que se guardará el PDF. ¡Aquí es donde comienza la magia!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Cambie esto a su directorio
```

 Esta línea define dónde se almacenará el PDF generado. No olvides reemplazar`YOUR DOCUMENT DIRECTORY` con tu camino actual.

### Paso 2: Crear un documento PDF
A continuación, crearemos un nuevo documento PDF y le agregaremos páginas.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Aquí, estamos inicializando un nuevo documento y agregando una página donde colocaremos nuestros fragmentos de texto.

### Paso 3: Agregar texto visible y oculto
Ahora agregaremos texto visible e invisible a nuestro PDF.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 En este fragmento,`frag1` será visible, mientras que`frag2` se establecerá como invisible a continuación.

### Paso 4: Establezca el texto como invisible
 Para hacer el texto de`frag2` invisible, simplemente modificas su`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Al establecer esta propiedad, cualquier texto asociado con`frag2` No se mostrará cuando se visualice el PDF.

### Paso 5: Agregar fragmentos de texto a la página
Finalmente, agregamos estos fragmentos de texto a la página y guardamos el PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Esta parte del código agrega nuestros fragmentos de texto a la página. Después, guardamos y eliminamos el documento correctamente.

## Búsqueda de texto oculto en el PDF

Ahora que hemos creado nuestro PDF con texto visible y oculto, ¿cómo buscamos ese texto oculto? Vamos a desglosarlo.

### Paso 1: Cargue el documento PDF
Para buscar texto dentro del PDF, primero debemos cargar el documento que acabamos de crear.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Paso 2: Crear un absorbedor de fragmentos de texto
 Nosotros lo usaremos`TextFragmentAbsorber` para capturar todos los fragmentos de texto en el PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Aquí especificamos que queremos absorber todos los fragmentos de texto de la primera página.

### Paso 3: Iterar a través de los fragmentos
Ahora, podemos iterar a través de los fragmentos de texto recopilados para descubrir cuáles son visibles y cuáles están ocultos.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Este bucle comprueba cada fragmento de texto e imprime su contenido junto con su posición y estado de visibilidad.`fragment.TextState.Invisible` se establece en verdadero, significa que el texto está oculto.

### Paso 4: Desechar el documento
Por último, recuerda desechar nuevamente el documento una vez que hayas terminado.

```csharp
doc.Dispose();
```

## Conclusión

En este tutorial, repasamos el apasionante proceso de agregar y buscar texto oculto en archivos PDF con Aspose.PDF para .NET. Aprendimos a crear un documento PDF con texto visible y oculto, así como a buscar dicho texto oculto mediante programación. Esta capacidad puede resultar increíblemente útil en diversas aplicaciones, ya sea que necesite almacenar información confidencial o brindar una experiencia de usuario única dentro de sus documentos.

A medida que se familiarice con ASPose.PDF, las posibilidades se harán infinitas. ¡Siga experimentando y ampliando los límites de lo que puede lograr con sus documentos PDF!

## Preguntas frecuentes

### ¿Puede Aspose.PDF manejar archivos PDF cifrados?  
Sí, Aspose.PDF admite el cifrado y descifrado de documentos PDF. Puede proteger fácilmente sus archivos PDF con contraseñas.

### ¿Hay una versión de prueba disponible para Aspose.PDF?  
 ¡Por supuesto! Puedes descargar la versión de prueba gratuita desde[aquí](https://releases.aspose.com/).

### ¿Qué lenguajes de programación admite Aspose.PDF?  
Aspose.PDF proporciona soporte para varios lenguajes, incluidos C#, Java y Python.

### ¿Dónde puedo encontrar la documentación de Aspose.PDF?  
 Puedes acceder a la documentación[aquí](https://reference.aspose.com/pdf/net/).

### ¿Cómo puedo obtener ayuda si encuentro problemas?  
 Para obtener ayuda, puede visitar los foros de Aspose[aquí](https://forum.aspose.com/c/pdf/10).