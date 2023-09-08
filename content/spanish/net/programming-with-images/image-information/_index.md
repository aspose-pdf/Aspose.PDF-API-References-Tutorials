---
title: Información de imagen en archivo PDF
linktitle: Información de imagen en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Extraiga información de la imagen en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-images/image-information/
---
Esta guía le mostrará paso a paso cómo extraer información sobre imágenes en un archivo PDF usando Aspose.PDF para .NET. Asegúrese de haber configurado su entorno y siga los pasos a continuación:

## Paso 1: definir el directorio de documentos

 Asegúrese de configurar el directorio de documentos correcto. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el archivo PDF de origen

 En este paso, cargaremos el archivo PDF de origen usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Paso 3: establecer la resolución predeterminada

En este paso, configuraremos la resolución predeterminada para las imágenes. En el ejemplo, la resolución predeterminada está establecida en 72.

```csharp
int defaultResolution = 72;
```

## Paso 4: Inicializar objetos y contadores

En este paso, inicializaremos los objetos y contadores necesarios para recuperar la información de la imagen.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Paso 5: recorrer los operadores en la primera página del documento

En este paso, recorreremos los operadores en la primera página del documento para identificar operaciones relacionadas con imágenes.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Paso 6: administrar operadores y extraer información de la imagen

En este paso gestionaremos los diferentes tipos de operadores y extraeremos la información de las imágenes.

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
     // Aplicar la matriz de transformación.
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
         // recuperar la imagen
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Recuperar las dimensiones de la imagen.
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calcule la resolución basándose en la información anterior.
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

### Código fuente de muestra para información de imagen usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue el archivo PDF de origen
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definir la resolución predeterminada para la imagen.
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definir un objeto de lista de matriz que contendrá los nombres de las imágenes
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insertar un objeto para apilar
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Obtenga todos los operadores en la primera página del documento.
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilice los operadores GSave/GRestore para revertir las transformaciones a las configuraciones anteriores
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Cree una instancia del objeto ConcatenateMatrix tal como define la matriz de transformación actual.
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
		// Multiplicar la matriz actual por la matriz de estado.
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// En caso de que se trate de un operador de dibujo de imágenes
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Cree un objeto XImage para contener imágenes de la primera página en PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Obtener dimensiones de la imagen
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Obtener información de alto y ancho de la imagen
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Resolución de cálculo basada en la información anterior
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Mostrar información de dimensión y resolución de cada imagen.
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusión

¡Enhorabuena! Ahora ha aprendido cómo extraer información de imagen en un archivo PDF usando Aspose.PDF para .NET. Puede utilizar esta información para diversas tareas de procesamiento de imágenes en sus aplicaciones.

### Preguntas frecuentes sobre información de imágenes en archivos PDF

#### P: ¿Cuál es el propósito de extraer información de imagen de un documento PDF usando Aspose.PDF para .NET?

R: Extraer información de la imagen de un documento PDF proporciona información sobre las dimensiones, la resolución y otros atributos de las imágenes dentro del documento. Esta información se puede utilizar para tareas de procesamiento, análisis u optimización de imágenes.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a extraer información de imagen de un documento PDF?

R: Aspose.PDF para .NET proporciona herramientas para acceder y analizar el contenido de un documento PDF, incluidas sus imágenes. El código proporcionado demuestra cómo extraer y mostrar información de la imagen utilizando varios operadores.

#### P: ¿Qué tipo de información de imagen se puede extraer con este método?

R: Este método le permite extraer y mostrar información como dimensiones escaladas, resolución y nombres de imágenes dentro de un documento PDF.

#### P: ¿Cómo identifica y procesa el código los operadores relacionados con imágenes dentro de un documento PDF?

R: El código recorre en iteración los operadores en una página específica del documento PDF. Identifica y procesa operadores relacionados con operaciones, transformaciones y renderizado de imágenes.

#### P: ¿Cuál es el significado de la resolución predeterminada y cómo se utiliza en el código?

R: La resolución predeterminada se utiliza como punto de referencia para calcular la resolución real de las imágenes. El código calcula la resolución de cada imagen en función de sus dimensiones y la configuración de resolución predeterminada.

#### P: ¿Cómo se puede utilizar la información de la imagen extraída en escenarios del mundo real?

R: La información de la imagen extraída se puede utilizar para tareas como evaluación de la calidad de la imagen, optimización de la imagen, generación de miniaturas de imágenes y facilitación de procesos de toma de decisiones relacionados con las imágenes.

#### P: ¿Puedo modificar el código para extraer atributos adicionales relacionados con la imagen?

R: Sí, puedes personalizar el código para extraer atributos adicionales de las imágenes, como el espacio de color, la profundidad de píxeles o el tipo de imagen.

#### P: ¿El proceso de extracción de información de la imagen consume mucho tiempo o recursos?

R: El proceso de extracción de información de imágenes es eficiente y está optimizado para el rendimiento, lo que garantiza un impacto mínimo en el uso de recursos y el tiempo de procesamiento.

#### P: ¿Cómo pueden beneficiarse los desarrolladores al identificar y extraer información de imágenes de documentos PDF?

R: Los desarrolladores pueden obtener información sobre las características de las imágenes dentro de los documentos PDF, lo que les permite tomar decisiones informadas con respecto a la manipulación, el procesamiento y la optimización de las imágenes.

#### P: ¿Se puede utilizar este método para el procesamiento por lotes de documentos PDF que contienen imágenes?

R: Sí, este método se puede ampliar para el procesamiento por lotes iterando a través de varias páginas o documentos, extrayendo información de la imagen y realizando tareas relacionadas con la imagen.