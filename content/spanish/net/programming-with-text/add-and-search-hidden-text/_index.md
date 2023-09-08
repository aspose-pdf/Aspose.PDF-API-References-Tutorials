---
title: Agregar y buscar texto oculto en un archivo PDF
linktitle: Agregar y buscar texto oculto en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para agregar y buscar texto oculto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-text/add-and-search-hidden-text/
---
En este tutorial, le explicaremos cómo agregar y buscar texto oculto en un archivo PDF usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

## 1. Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro entorno de desarrollo instalado y configurado.
- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede descargarlo desde el sitio web oficial de Aspose.

## 2. Creando el documento PDF con texto oculto

Para comenzar, use el siguiente código para crear un nuevo documento PDF que contenga texto oculto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Crear un documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Establecer propiedad de texto: invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Asegúrese de proporcionar la ruta y el nombre de archivo deseados para el documento PDF.

## 3. Buscar texto en el documento.

A continuación, buscaremos el texto oculto en el documento PDF. Utilice el siguiente código:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Haz algo con los fragmentos.
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Esto buscará el texto oculto en la segunda página del documento PDF y mostrará la información relevante.

### Código fuente de muestra para agregar y buscar texto oculto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Crear documento con texto oculto
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Establecer propiedad de texto: invisible
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Buscar texto en el documento.
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Haz algo con fragmentos
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusión

¡Enhorabuena! Ha agregado y encontrado con éxito texto oculto en un documento PDF utilizando Aspose.PDF para .NET. Ahora puedes aplicar este método a tus propios proyectos para manipular y buscar texto oculto en archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una biblioteca sólida que permite a los desarrolladores crear, manipular y transformar documentos PDF dentro de aplicaciones .NET.

#### P: ¿Se puede utilizar texto oculto para fines de marcas de agua?

R: ¡Absolutamente! El texto oculto puede servir como un medio eficaz para poner marcas de agua en documentos PDF, añadiendo una capa adicional de seguridad.

#### P: ¿Es posible revelar texto oculto en un documento PDF?

R: Sí, el proceso de buscar y revelar texto oculto dentro de un documento PDF se puede lograr utilizando las técnicas descritas en este tutorial.

#### P: ¿Qué otras funcionalidades ofrece Aspose.PDF para .NET?

R: Más allá de la manipulación de texto oculto, Aspose.PDF para .NET proporciona una amplia gama de funciones, que incluyen generación, conversión, cifrado y más de PDF.