---
title: Rahmen in PDF-Datei extrahieren
linktitle: Rahmen in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Ränder aus einer PDF-Datei extrahieren und als Bild speichern. Schritt-für-Schritt-Anleitung mit Codebeispielen und Tipps für den Erfolg.
type: docs
weight: 80
url: /de/net/programming-with-tables/extract-border/
---
## Einführung

Beim Arbeiten mit PDFs kann das Extrahieren bestimmter Elemente wie Ränder oder grafische Pfade eine entmutigende Aufgabe sein. Aber mit Aspose.PDF für .NET können Sie problemlos Ränder oder Formen aus einer PDF-Datei extrahieren und als Bild speichern. In diesem Tutorial tauchen wir in den Prozess des Extrahierens eines Rands aus einer PDF-Datei und des Speicherns als PNG-Bild ein. Machen Sie sich bereit, die Kontrolle über die grafischen Inhalte Ihrer PDF-Datei zu übernehmen!

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass Sie alles eingerichtet haben:

1.  Aspose.PDF für .NET: Wenn Sie die Aspose.PDF-Bibliothek noch nicht installiert haben, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/). Sie müssen außerdem die Lizenz beantragen, entweder über die kostenlose Testversion oder eine erworbene Lizenz.
2. IDE-Setup: Richten Sie ein C#-Projekt in Visual Studio oder einer anderen .NET-IDE ein. Stellen Sie sicher, dass Sie die erforderlichen Verweise zur Aspose.PDF-Bibliothek hinzugefügt haben.
3. PDF-Eingabedatei: Halten Sie eine PDF-Datei bereit, aus der Sie die Ränder extrahieren. Dieses Tutorial bezieht sich auf eine Datei namens`input.pdf`.

## Importieren erforderlicher Pakete

Beginnen wir mit dem Importieren der erforderlichen Namespaces. Diese Pakete bieten die erforderlichen Tools zum Bearbeiten des PDF-Inhalts.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Nachdem wir nun die Grundlagen abgedeckt haben, fahren wir mit der Schritt-für-Schritt-Anleitung fort, in der wir jeden Teil des Codes aufschlüsseln, um ihn im Detail zu erklären.


## Schritt 1: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das PDF-Dokument zu laden, das den Rahmen enthält, den Sie extrahieren möchten. Stellen Sie es sich so vor, als würden Sie ein Buch öffnen, bevor Sie mit dem Lesen beginnen – Sie müssen auf den Inhalt zugreifen können!

 Wir beginnen mit der Angabe des Verzeichnisses, in dem Ihre PDF-Datei gespeichert ist, und laden das Dokument mit dem`Aspose.Pdf.Document` Klasse.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Dieser Code lädt die`input.pdf` Datei aus dem angegebenen Verzeichnis. Stellen Sie sicher, dass der Dateipfad korrekt ist, da Sie sonst möglicherweise die Fehlermeldung „Datei nicht gefunden“ erhalten.

## Schritt 2: Einrichten von Grafiken und Bitmap

Bevor wir mit dem Extrahieren beginnen, müssen wir eine Leinwand zum Zeichnen erstellen. In der Welt von .NET bedeutet dies, dass wir Bitmap- und Grafikobjekte einrichten müssen. Das Bitmap stellt das Bild dar und das Grafikobjekt ermöglicht es uns, aus der PDF-Datei extrahierte Formen wie z. B. Ränder zu zeichnen.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Hier ist eine Aufschlüsselung:
- Wir erstellen ein Bitmap-Bild in der Größe der ersten Seite des PDF.
- GraphicsPath wird zum Definieren von Formen (in diesem Fall Rändern) verwendet.
- Die Matrix definiert, wie Grafiken transformiert werden. Wir benötigen eine Inversionsmatrix, da PDF und .NET unterschiedliche Koordinatensysteme haben.

## Schritt 3: PDF-Inhalte verarbeiten


Die PDF-Datei besteht aus einer Reihe von Zeichenbefehlen und wir müssen jeden dieser Befehle verarbeiten, um die Randinformationen zu identifizieren und zu extrahieren.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Verarbeiten von Befehlen wie Speichern/Wiederherstellen des Zustands, Zeichnen von Linien, Füllen von Formen usw.
}
```

Der Code durchläuft alle Zeichenoperatoren im Inhaltsstrom der PDF-Datei. Jeder Operator kann eine Linie, ein Rechteck oder eine andere grafische Anweisung darstellen.

## Schritt 4: Umgang mit PDF-Operatoren

Jeder Operator in der PDF-Datei steuert eine Aktion. Um den Rahmen zu extrahieren, müssen wir Befehle wie „Verschieben zu“, „Linie zu“ und „Rechteck zeichnen“ identifizieren. Die folgenden Operatoren handhaben diese Aktionen:

- MoveTo: Bewegt den Cursor zu einem Startpunkt.
- LineTo: Zeichnet eine Linie vom aktuellen Punkt zu einem neuen Punkt.
- Betreff: Zeichnet ein Rechteck (dies könnte Teil des Rahmens sein).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
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
```

In diesem Schritt:
- Wir erfassen die Punkte für jede gezeichnete Linie oder Form.
- Für Rechtecke (`opRe` ), fügen wir sie direkt dem`graphicsPath`, das wir später zum Zeichnen der Grenze verwenden werden.

## Schritt 5: Den Rand zeichnen

Sobald wir die Linien und Rechtecke identifiziert haben, die den Rahmen bilden, müssen wir sie tatsächlich auf das Bitmap-Objekt zeichnen. Hier kommt das Grafikobjekt ins Spiel.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Wir erstellen ein Grafikobjekt basierend auf der Bitmap.
- SmoothingMode.HighQuality stellt sicher, dass wir ein schönes, glattes Bild erhalten.
- Schließlich verwenden wir DrawPath, um den Rahmen zu zeichnen.

## Schritt 6: Speichern des extrahierten Rahmens

Nachdem wir den Rahmen extrahiert haben, ist es an der Zeit, ihn als Bilddatei zu speichern. Dadurch wird der Rahmen als PNG gespeichert.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Die Bitmap wird als PNG-Bild gespeichert.
- Sie können dieses Bild jetzt öffnen, um den extrahierten Rand anzuzeigen.

## Abschluss

Das Extrahieren von Rändern aus einer PDF-Datei mit Aspose.PDF für .NET mag zunächst schwierig erscheinen, aber wenn man es einmal aufschlüsselt, wird es ganz einfach. Wenn Sie die Zeichenoperatoren in einer PDF-Datei verstehen und die leistungsstarken .NET-Bibliotheken nutzen, können Sie grafische Inhalte effizient bearbeiten und extrahieren. Dieses Handbuch bietet Ihnen eine solide Grundlage für den Einstieg in die PDF-Bearbeitung!

## Häufig gestellte Fragen

### Wie gehe ich mit mehreren Seiten im PDF um?  
 Sie können jede Seite im Dokument durchgehen, indem Sie iterieren über`doc.Pages` statt Hardcoding`doc.Pages[1]`.

### Kann ich mit demselben Ansatz andere Elemente, etwa Text, extrahieren?  
Ja, Aspose.PDF bietet umfangreiche APIs zum Extrahieren von Text, Bildern und anderen Inhalten aus PDF-Dateien.

### Wie wende ich eine Lizenz an, um Einschränkungen zu vermeiden?  
 Du kannst[eine Lizenz beantragen](https://purchase.aspose.com/temporary-license/) durch Laden über die`License` Klasse bereitgestellt von Aspose.

### Was ist, wenn meine PDF keine Ränder hat?  
Wenn Ihr PDF keine sichtbaren Ränder enthält, liefert der Grafikextraktionsprozess möglicherweise kein Ergebnis. Stellen Sie sicher, dass der PDF-Inhalt zeichenbare Ränder enthält.

### Kann ich die Ausgabe in anderen Formaten als PNG speichern?  
 Ja, ändern Sie einfach die`ImageFormat.Png` in ein anderes unterstütztes Format wie`ImageFormat.Jpeg`.