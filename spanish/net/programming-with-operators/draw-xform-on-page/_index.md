---
title: Dibujar XForm en la página
linktitle: Dibujar XForm en la página
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para dibujar un formulario XForm en una página PDF utilizando Aspose.PDF para .NET. Agregue y coloque el formulario en la página.
type: docs
weight: 10
url: /es/net/programming-with-operators/draw-xform-on-page/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo dibujar un XForm en una página usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Con los operadores proporcionados por Aspose.PDF, puede agregar y colocar un formulario XForm en una página PDF existente.

## requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos en su lugar:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca del sitio web oficial de Aspose e instalarla en su máquina.

## Paso 2: importa los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Paso 3: Configuración de rutas de archivo

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
// El siguiente código usa los operadores GSave/GRestore
// El código usa el operador ContatenateMatrix para posicionar el XForm
// El código usa el operador Do para dibujar el XForm en la página
// Los operadores GSave/GRestore envuelven el contenido existente
// esto se hace para obtener el estado de gráficos inicial al final del contenido existente
// de lo contrario, pueden quedar transformaciones no deseadas al final de la cadena de operadores existentes
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Agregue el operador GSave para restablecer correctamente el estado de los gráficos después de nuevos comandos
pageContents. Add(new GSave());

// Crear el formulario X
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Establecer el ancho y alto de la imagen.
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Cargue la imagen en una secuencia
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Agregar la imagen a la colección de imágenes de recursos de XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Usando el operador Do: este operador dibuja la imagen
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Coloque el XForm en las coordenadas x=100 e y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Dibuja el XForm con el operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Coloque el XForm en las coordenadas x=100 e y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Dibuja el XForm con el operador Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Restaura el estado de los gráficos con GRestore después de GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Asegúrese de especificar las rutas de archivo reales y ajuste el número de página y las posiciones de XForm según sea necesario.

### Ejemplo de código fuente para Draw XForm On Page usando Aspose.PDF para .NET
 
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
	// Uso de los operadores GSave/GRestore
	// Uso del operador ContatenateMatrix para posicionar xForm
	// Hacer uso del operador para dibujar xForm en la página
	// Envuelva los contenidos existentes con el par de operadores GSave/GRestore
	// esto es para obtener el estado de los gráficos iniciales en el y de los contenidos existentes
	// de lo contrario, podrían quedar algunas transformaciones no deseadas al final de la cadena de operadores existente
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Agregue el operador Guardar estado de gráficos para borrar correctamente el estado de gráficos después de nuevos comandos
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Crear formulario x
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definir el ancho y alto de la imagen
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Cargar imagen en flujo
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Agregar imagen a la colección de imágenes de los recursos de XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Usando el operador Do: este operador dibuja la imagen
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Forma de lugar a las coordenadas x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Dibujar formulario con el operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Forma de lugar a las coordenadas x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Dibujar formulario con el operador Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Restaure el estado de los gráficos con GRestore después de GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusión

En este tutorial, aprendió a dibujar un formulario XForm en una página PDF usando Aspose.PDF para .NET. Siguiendo los pasos descritos, podrá agregar y colocar un formulario XForm en una página existente, dando así más flexibilidad a sus documentos PDF.

### Preguntas frecuentes para dibujar XForm en la página

#### P: ¿Qué es un XForm en Aspose.PDF?

R: Un XForm es un objeto gráfico reutilizable en un documento PDF. Le permite definir y dibujar gráficos, imágenes o texto complejos que se pueden reutilizar varias veces en diferentes páginas.

#### P: ¿Cómo importo los espacios de nombres necesarios para Aspose.PDF?

 R: En su archivo de código C#, use el`using` directiva para importar los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### P: ¿Cuál es el propósito de los operadores GSave y GRestore?

 R: El`GSave` y`GRestore`Los operadores en Aspose.PDF se utilizan para guardar y restaurar el estado de los gráficos. Ayudan a garantizar que las transformaciones y configuraciones aplicadas a una sección del contenido no afecten a las secciones posteriores.

#### P: ¿Cómo defino un XForm usando Aspose.PDF?

 R: Para crear un XForm, use el`XForm.CreateNewForm` y agréguelo al`Resources.Forms` colección de una página específica. A continuación, puede agregar contenido a la XForm`Contents` propiedad.

#### P: ¿Cómo puedo dibujar una imagen dentro de un XForm?

 R: Cargue la imagen en un flujo y agréguela al`Resources.Images` colección del XForm. Utilizar el`Do` operador dentro del XForm`Contents` para dibujar la imagen.

#### P: ¿Cómo coloco un XForm en una página PDF?

 R: Para colocar un XForm en una página, utilice el`ConcatenateMatrix` operador dentro de la página`Contents`. Ajuste los parámetros de la matriz para especificar la traducción (posición) y la escala del XForm.

#### P: ¿Puedo dibujar múltiples XForms en la misma página?

 R: Sí, puede dibujar múltiples XForms en la misma página ajustando el`ConcatenateMatrix`parámetros para posicionar cada XForm en diferentes coordenadas.

#### P: ¿Puedo modificar el contenido de un XForm después de crearlo?

 R: Sí, puede modificar el contenido de un XForm después de la creación agregando operadores adicionales a su`Contents` propiedad.

#### P: ¿Qué sucede si omito los operadores GSave y GRestore?

R: Omitir los operadores GSave y GRestore puede provocar que se apliquen transformaciones o configuraciones no deseadas al contenido posterior. Su uso ayuda a mantener un estado de gráficos limpio.

#### P: ¿Puedo reutilizar XForms en diferentes páginas del documento PDF?

 R: Sí, puede reutilizar XForms en varias páginas agregando el mismo XForm al`Resources.Forms` colección de diferentes páginas.

#### P: ¿Existe un límite en la cantidad de XForms que puedo crear?

R: Si bien no existe un límite estricto para la cantidad de XForms que puede crear, tenga en cuenta que demasiados XForms pueden afectar el rendimiento y el uso de la memoria. Úselos juiciosamente.

#### P: ¿Puedo rotar un XForm o aplicar otras transformaciones?

 R: Sí, puede utilizar el`ConcatenateMatrix`operador para aplicar transformaciones como rotación, escalado y traducción a un XForm.
