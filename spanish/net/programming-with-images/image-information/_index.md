---
title: Información de la imagen
linktitle: Información de la imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Extraiga la información de la imagen en un archivo PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-images/image-information/
---

Esta guía lo guiará paso a paso sobre cómo extraer información sobre imágenes en un archivo PDF utilizando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Asegúrese de establecer el directorio de documentos correcto. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el archivo PDF de origen

 En este paso, cargaremos el archivo PDF de origen usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Paso 3: establece la resolución predeterminada

En este paso, estableceremos la resolución predeterminada para las imágenes. En el ejemplo, la resolución predeterminada se establece en 72.

```csharp
int defaultResolution = 72;
```

## Paso 4: inicializar objetos y contadores

En este paso, inicializaremos los objetos y contadores necesarios para recuperar la información de la imagen.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Paso 5: recorrer los operadores en la primera página del documento

En este paso, recorreremos los operadores en la primera página del documento para identificar las operaciones relacionadas con la imagen.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Paso 6: Administrar operadores y extraer información de imágenes

En este paso, gestionaremos los diferentes tipos de operadores y extraeremos la información sobre las imágenes.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Manejar operaciones GSave y GRestore para transformaciones
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Manejar la operación ConcatenateMatrix para transformaciones
else if (opCtm != null)
{
     // Aplicar la matriz de transformación
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Manejar la operación Do para imágenes
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Recuperar la imagen
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Recuperar las dimensiones de la imagen.
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calcule la resolución basándose en la información anterior
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Mostrar información de la imagen
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Ejemplo de código fuente para la información de la imagen usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue el archivo PDF de origen
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definir la resolución predeterminada para la imagen
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Defina el objeto de la lista de matrices que contendrá los nombres de las imágenes
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insertar un objeto para apilar
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Obtener todos los operadores en la primera página del documento
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilice los operadores GSave/GRestore para revertir las transformaciones a la configuración anterior
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Crea una instancia del objeto ConcatenateMatrix tal como define la matriz de transformación actual.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Crear operador Do que extrae objetos de los recursos. Dibuja objetos de forma y objetos de imagen.
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Guarde el estado anterior y coloque el estado actual en la parte superior de la pila
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Desechar el estado actual y restaurar el anterior
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Multiplique la matriz actual con la matriz de estado
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// En caso de que se trate de un operador de dibujo de imágenes
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Crear objeto XImage para contener imágenes de la primera página pdf
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Obtener dimensiones de la imagen
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Obtenga información sobre la altura y el ancho de la imagen
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Resolución de cálculo basada en la información anterior
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Mostrar información de dimensión y resolución de cada imagen
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusión

¡Felicidades! Ahora ha aprendido a extraer información de imágenes en un archivo PDF utilizando Aspose.PDF para .NET. Puede utilizar esta información para diversas tareas de procesamiento de imágenes en sus aplicaciones.