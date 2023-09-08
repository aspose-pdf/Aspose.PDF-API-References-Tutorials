---
title: Extraer borde en archivo PDF
linktitle: Extraer borde en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer el borde de un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-tables/extract-border/
---
En este tutorial, aprenderemos cómo extraer el borde de un archivo PDF usando Aspose.PDF para .NET. Explicaremos el código fuente en C# paso a paso. Al final de este tutorial, sabrás cómo extraer el borde de un documento PDF y guardarlo como una imagen. ¡Empecemos!

## Paso 1: configurar el entorno
Primero, asegúrese de haber configurado su entorno de desarrollo C# con Aspose.PDF para .NET. Agregue la referencia a la biblioteca e importe los espacios de nombres necesarios.

## Paso 2: cargar el documento PDF
En este paso, cargamos el documento PDF desde el archivo especificado.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con el directorio real donde se encuentra su archivo PDF.

## Paso 3: Extracción de bordes
Extraeremos el borde del documento PDF iterando sobre las operaciones contenidas en el documento.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Procesar todas las operaciones de contenido
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Consulta el tipo de operación
         // ...
         // Agregar código para procesar cada operación
     }
}
```

 Creamos un`graphicsState` pila para almacenar estados de gráficos, una imagen de mapa de bits para capturar el borde extraído, una`GraphicsPath` objeto para almacenar rutas de dibujo y otras variables para realizar un seguimiento del estado y los colores.

## Paso 4: Procesamiento de transacciones
En este paso procesamos cada operación del documento para extraer el borde.

```csharp
// Consulta el tipo de operación
if (opSaveState != null)
{
     // Guarde el estado anterior y coloque el estado actual en la parte superior de la pila
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Eliminar el estado actual y restaurar el estado anterior
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Recuperar la matriz de transformación actual.
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Multiplica la matriz actual por la matriz de estado.
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Actualizar el último punto de dibujo.
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Procesar el dibujo de una línea.
     // ...
     // Agregar código para manejar el dibujo de una línea
}
// ...
// Agregue bloques else if para otras operaciones
```

Verificamos el tipo de operación usando condiciones y ejecutamos el código apropiado para cada operación.

## Paso 5: imagen de respaldo
Finalmente, guardamos la imagen de mapa de bits que contiene el borde extraído en un archivo específico.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Asegúrese de especificar el directorio y el nombre de archivo correctos para guardar la imagen de salida.

### Código fuente de ejemplo para extraer borde usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// El valor predeterminado de la matriz ctm es 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.El sistema de coordenadas de dibujo se basa en la parte superior izquierda, mientras que el sistema de coordenadas pdf se basa en la parte inferior izquierda, por lo que tenemos que aplicar la matriz de inversión.
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Procesar todos los comandos de contenido.
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Guarde el estado anterior y coloque el estado actual en la parte superior de la pila
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Desechar el estado actual y restaurar el anterior
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, aprendimos cómo extraer el borde de un documento PDF usando Aspose.PDF para .NET. Puede utilizar esta guía paso a paso para extraer el borde de otros documentos PDF.

### Preguntas frecuentes para extraer el borde en un archivo PDF

#### P: ¿Cuál es el propósito de extraer el borde de un archivo PDF?

R: Extraer el borde de un archivo PDF puede resultar útil para diversos fines. Permite aislar y analizar los elementos estructurales del documento, como tablas, diagramas o elementos gráficos. Puede utilizar el borde extraído para identificar el diseño, las dimensiones y la posición del contenido dentro del documento PDF.

#### P: ¿Puedo extraer el borde de páginas o áreas específicas dentro del documento PDF?

R: Sí, puede modificar el código fuente de C# proporcionado para extraer el borde de páginas o regiones específicas dentro del documento PDF. Al manipular el`doc.Pages` colección y especificando criterios personalizados, puede optar por extraer el borde de páginas o áreas de interés particulares.

#### P: ¿Cómo puedo personalizar el formato y la calidad de la imagen de salida?

 R: En el código C# proporcionado, el borde extraído se guarda como una imagen PNG. Si desea cambiar el formato de la imagen de salida, puede modificar el`ImageFormat.Png` parámetro en el`bitmap.Save` método a otros formatos de imagen compatibles, como JPEG, BMP o GIF. Además, puede ajustar la calidad de la imagen o la configuración de compresión según sus requisitos.

#### P: ¿Qué otras operaciones puedo realizar en la frontera extraída?

R: Una vez que haya extraído el borde como imagen, puede procesarlo aún más utilizando bibliotecas o algoritmos de procesamiento de imágenes. Puede analizar la imagen, aplicar filtros de imagen, detectar patrones o realizar OCR (reconocimiento óptico de caracteres) para extraer texto de la imagen si es necesario.

#### P: ¿Existe alguna limitación o consideración al extraer bordes de documentos PDF complejos?

R: El proceso de extracción puede variar según la complejidad del documento PDF. Los archivos PDF complejos con múltiples capas, transparencia o gráficos avanzados pueden requerir procesamiento o ajustes adicionales para extraer el borde con precisión. Es esencial probar exhaustivamente el proceso de extracción en varios documentos PDF para garantizar resultados confiables.