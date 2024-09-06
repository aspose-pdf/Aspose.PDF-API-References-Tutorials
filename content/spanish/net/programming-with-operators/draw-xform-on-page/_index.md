---
title: Dibujar XForm en la página
linktitle: Dibujar XForm en la página
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para dibujar un formulario XForm en una página PDF con Aspose.PDF para .NET. Agregue y ubique el formulario en la página.
type: docs
weight: 10
url: /es/net/programming-with-operators/draw-xform-on-page/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo dibujar un XForm en una página utilizando Aspose.PDF para .NET. Aspose.PDF es una potente biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Con los operadores proporcionados por Aspose.PDF, puede agregar y colocar un formulario XForm en una página PDF existente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca desde el sitio web oficial de Aspose e instalarla en su equipo.

## Paso 2: Importar los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Paso 3: Configuración de rutas de archivos

Defina las rutas de archivo para la imagen de fondo, el archivo PDF de entrada y el archivo PDF de salida:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Asegúrese de especificar las rutas de archivo reales en su máquina.

## Paso 4: Cargar el archivo PDF de entrada

Utilice el siguiente código para cargar el archivo PDF de entrada:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// El siguiente código utiliza los operadores GSave/GRestore
// El código utiliza el operador ContatenateMatrix para posicionar el XForm
// El código utiliza el operador Do para dibujar el XForm en la página.
// Los operadores GSave/GRestore envuelven el contenido existente
//Esto se hace para obtener el estado gráfico inicial al final del contenido existente.
// De lo contrario, pueden quedar transformaciones no deseadas al final de la cadena de operadores existentes.
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Agregue el operador GSave para restablecer correctamente el estado de los gráficos después de nuevos comandos
pageContents. Add(new GSave());

// Crear el XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Establezca el ancho y la altura de la imagen.
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Cargar la imagen en una secuencia
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Agregue la imagen a la colección de imágenes de recursos de XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Usando el operador Do: este operador dibuja la imagen
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Coloque el XForm en las coordenadas x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Dibuje la XForm con el operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Coloque el XForm en las coordenadas x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Dibuje la XForm con el operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Restaurar el estado de los gráficos con GRestore después de GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Asegúrese de especificar las rutas de archivo reales y ajustar el número de página y las posiciones de XForm según sea necesario.

### Código fuente de muestra para dibujar XForm en una página usando Aspose.PDF para .NET
 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// La muestra demuestra
	// Uso de operadores GSave/GRestore
	// Uso del operador ContatenateMatrix para posicionar xForm
	//¿Se utiliza el operador para dibujar xForm en la página?
	// Envuelva los contenidos existentes con el par de operadores GSave/GRestore
	// Esto es para obtener el estado gráfico inicial al final del contenido existente.
	// De lo contrario, podrían quedar algunas transformaciones indeseables al final de la cadena de operadores existentes.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Agregar operador de guardar estado de gráficos para borrar correctamente el estado de gráficos después de nuevos comandos
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Crear xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definir el ancho y alto de la imagen
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Cargar imagen en la secuencia
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Agregar imagen a la colección de imágenes de los recursos de XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Uso del operador Do: este operador dibuja una imagen
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Coloque la forma en las coordenadas x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Dibujar formulario con operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Coloque la forma en las coordenadas x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Dibujar formulario con operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Restaurar el estado de los gráficos con GRestore después de GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusión

En este tutorial, aprendió a dibujar un formulario XForm en una página PDF utilizando Aspose.PDF para .NET. Si sigue los pasos descritos, podrá agregar y ubicar un formulario XForm en una página existente, lo que le dará más flexibilidad a sus documentos PDF.

### Preguntas frecuentes sobre el dibujo de XForm en la página

#### P: ¿Qué es un XForm en Aspose.PDF?

R: Un XForm es un objeto gráfico reutilizable en un documento PDF. Permite definir y dibujar gráficos, imágenes o textos complejos que se pueden reutilizar varias veces en distintas páginas.

#### P: ¿Cómo importo los espacios de nombres necesarios para Aspose.PDF?

 A: En su archivo de código C#, utilice el`using` Directiva para importar los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### P: ¿Cuál es el propósito de los operadores GSave y GRestore?

 A: El`GSave` y`GRestore` Los operadores de Aspose.PDF se utilizan para guardar y restaurar el estado de los gráficos. Ayudan a garantizar que las transformaciones y configuraciones aplicadas a una sección del contenido no afecten a las secciones posteriores.

#### P: ¿Cómo defino un XForm usando Aspose.PDF?

 A: Para crear un XForm, utilice el`XForm.CreateNewForm` método y agregarlo al`Resources.Forms` Colección de una página específica. Luego, puede agregar contenido a XForm.`Contents` propiedad.

#### P: ¿Cómo puedo dibujar una imagen dentro de un XForm?

A: Cargue la imagen en una secuencia y agréguela a la`Resources.Images` Colección de XForm. Utilice el`Do` operador dentro del XForm`Contents` Para dibujar la imagen.

#### P: ¿Cómo coloco un XForm en una página PDF?

 A: Para posicionar un XForm en una página, utilice el`ConcatenateMatrix` operador dentro de la página`Contents`. Ajuste los parámetros de la matriz para especificar la traducción (posición) y la escala del XForm.

#### P: ¿Puedo dibujar varios XForms en la misma página?

 R: Sí, puedes dibujar múltiples XForms en la misma página ajustando el`ConcatenateMatrix` parámetros para posicionar cada XForm en diferentes coordenadas.

#### P: ¿Puedo modificar el contenido de un XForm después de crearlo?

 R: Sí, puede modificar el contenido de un XForm después de su creación agregando operadores adicionales a su`Contents` propiedad.

#### P: ¿Qué sucede si omito los operadores GSave y GRestore?

R: Omitir los operadores GSave y GRestore puede provocar que se apliquen transformaciones o configuraciones no deseadas al contenido posterior. Su uso ayuda a mantener un estado gráfico limpio.

#### P: ¿Puedo reutilizar XForms en diferentes páginas del documento PDF?

 R: Sí, puede reutilizar XForms en varias páginas agregando el mismo XForm a la`Resources.Forms` Colección de diferentes páginas.

#### P: ¿Existe un límite en la cantidad de XForms que puedo crear?

R: Si bien no existe un límite estricto para la cantidad de XForms que puede crear, tenga en cuenta que demasiados XForms pueden afectar el rendimiento y el uso de memoria. Úselos con prudencia.

#### P: ¿Puedo rotar un XForm o aplicar otras transformaciones?

 A: Sí, puedes utilizar el`ConcatenateMatrix` operador para aplicar transformaciones como rotación, escala y traslación a un XForm.
