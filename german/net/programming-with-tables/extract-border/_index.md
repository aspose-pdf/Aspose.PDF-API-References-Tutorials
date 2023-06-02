---
title: Rand extrahieren
linktitle: Rand extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den Rand aus einem PDF-Dokument extrahieren.
type: docs
weight: 80
url: /de/net/programming-with-tables/extract-border/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET den Rahmen aus einem PDF-Dokument extrahieren. Wir erklären Ihnen Schritt für Schritt den Quellcode in C#. Am Ende dieses Tutorials erfahren Sie, wie Sie den Rand aus einem PDF-Dokument extrahieren und als Bild speichern. Lasst uns beginnen!

## Schritt 1: Einrichten der Umgebung
Stellen Sie zunächst sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Fügen Sie den Verweis zur Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Laden des PDF-Dokuments
In diesem Schritt laden wir das PDF-Dokument aus der angegebenen Datei.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch das tatsächliche Verzeichnis ersetzen, in dem sich Ihre PDF-Datei befindet.

## Schritt 3: Kantenextraktion
Wir extrahieren den Rand aus dem PDF-Dokument, indem wir die im Dokument enthaltenen Vorgänge durchlaufen.

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
     // Verarbeiten Sie alle Inhaltsvorgänge
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Überprüfen Sie die Art der Operation
         // ...
         // Fügen Sie Code hinzu, um jeden Vorgang zu verarbeiten
     }
}
```

 Wir erstellen ein`graphicsState` Stapel zum Speichern von Grafikzuständen, ein Bitmap-Bild zum Erfassen des extrahierten Randes, a`GraphicsPath` Objekt zum Speichern von Zeichenpfaden und anderen Variablen zum Verfolgen von Status und Farben.

## Schritt 4: Transaktionsverarbeitung
In diesem Schritt verarbeiten wir jeden Vorgang des Dokuments, um den Rand zu extrahieren.

```csharp
// Überprüfen Sie die Art der Operation
if (opSaveState != null)
{
     // Speichern Sie den vorherigen Status und verschieben Sie den aktuellen Status an die Spitze des Stapels
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Löschen Sie den aktuellen Status und stellen Sie den vorherigen Status wieder her
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Rufen Sie die aktuelle Transformationsmatrix ab
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Multiplizieren Sie die aktuelle Matrix mit der Zustandsmatrix
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Aktualisieren Sie den letzten Zeichnungspunkt
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Verarbeiten Sie das Zeichnen einer Linie
     // ...
     // Fügen Sie Code hinzu, um das Zeichnen einer Linie zu handhaben
}
// ...
// Fügen Sie else if-Blöcke für andere Vorgänge hinzu
```

Wir überprüfen die Art der Operation anhand von Bedingungen und führen für jede Operation den entsprechenden Code aus.

## Schritt 5: Backup-Image
Abschließend speichern wir das Bitmap-Bild mit dem extrahierten Rand in einer angegebenen Datei.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Stellen Sie sicher, dass Sie das richtige Verzeichnis und den richtigen Dateinamen angeben, um das Ausgabebild zu speichern.

### Beispielquellcode für Extract Border mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Der Standardwert der CTM-Matrix ist 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Das System.Drawing-Koordinatensystem basiert auf der oberen linken Seite, während das PDF-Koordinatensystem auf der unteren linken Seite basiert. Daher müssen wir die Inversionsmatrix anwenden
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Verarbeiten Sie alle Inhaltsbefehle
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
			// Vorherigen Status speichern und aktuellen Status an die Spitze des Stapels verschieben
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Den aktuellen Zustand verwerfen und den vorherigen wiederherstellen
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

			// Aktuelle Matrix mit der Zustandsmatrix multiplizieren
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

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET den Rahmen aus einem PDF-Dokument extrahiert. Mit dieser Schritt-für-Schritt-Anleitung können Sie Ränder aus anderen PDF-Dokumenten extrahieren.