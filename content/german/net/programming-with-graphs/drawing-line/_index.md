---
title: Zeichnungslinie
linktitle: Zeichnungslinie
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Linien in ein PDF-Dokument zeichnen. Diese Schritt-für-Schritt-Anleitung behandelt das Einrichten Ihres Dokuments, das Hinzufügen von Linien und das Speichern der Datei.
type: docs
weight: 80
url: /de/net/programming-with-graphs/drawing-line/
---
## Einführung

Das Zeichnen von Linien in einem PDF-Dokument mag wie eine einfache Aufgabe erscheinen, kann aber ein leistungsstarkes Werkzeug zum Erstellen von visuellen Hilfsmitteln, Diagrammen und zum Hervorheben wichtiger Bereiche sein. In dieser Anleitung führen wir Sie durch den Prozess des Zeichnens von Linien in einem PDF-Dokument mit Aspose.PDF für .NET. Dieses Tutorial behandelt alles, vom Einrichten Ihrer Umgebung bis zum Ausführen des Codes zum Erstellen eines PDFs mit darüber gezeichneten Linien.

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, benötigen Sie einige Dinge:

1.  Aspose.PDF für .NET: Sie müssen Aspose.PDF für .NET installiert haben. Sie können es herunterladen von der[Aspose-Website](https://releases.aspose.com/pdf/net/).
2. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung für .NET-Anwendungen eingerichtet haben. Visual Studio ist hierfür eine gute Wahl.
3. Grundkenntnisse in C#: Kenntnisse in der C#-Programmierung sind hilfreich für das Verständnis der Codeausschnitte und Beispiele in diesem Tutorial.

## Pakete importieren

Um mit Aspose.PDF für .NET zu arbeiten, müssen Sie die entsprechenden Namespaces importieren. Fügen Sie oben in Ihrer C#-Datei die folgende using-Direktive hinzu:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die zum Bearbeiten von PDF-Dokumenten und Zeichnen von Formen erforderlich sind.

Lassen Sie uns den Vorgang des Linienzeichnens in eine Reihe von Schritten aufteilen. Jeder Schritt führt Sie durch einen bestimmten Teil des Codes, damit Sie verstehen, wie Sie das gewünschte Ergebnis erzielen.

## Schritt 1: Richten Sie Ihr Dokument und Ihre Seite ein

Der erste Schritt besteht darin, ein neues PDF-Dokument zu erstellen und ihm eine Seite hinzuzufügen. So können Sie das tun:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz erstellen
Document pDoc = new Document();

// Seite zur Seitensammlung des PDF-Dokuments hinzufügen
Page pg = pDoc.Pages.Add();
```

 Hier,`dataDir` ist der Pfad, in dem Ihr Ausgabe-PDF gespeichert wird.`Document` ist die Hauptklasse für die Handhabung von PDFs und`Page` stellt eine einzelne Seite im PDF-Dokument dar.

## Schritt 2: Seitenränder konfigurieren

Um sicherzustellen, dass Ihre Linien von Rand zu Rand reichen, müssen Sie die Seitenränder auf Null setzen:

```csharp
// Seitenrand auf allen Seiten auf 0 setzen
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

Dadurch werden alle Standardränder entfernt und Sie haben eine ganzseitige Leinwand zum Zeichnen.

## Schritt 3: Erstellen Sie das Graph-Objekt

 Erstellen Sie als Nächstes eine`Graph` Objekt, das den Abmessungen der Seite entspricht. Dieses Objekt dient als Container für Ihre Formen:

```csharp
// Erstellen Sie ein Graph-Objekt mit einer Breite und Höhe, die den Seitenmaßen entspricht
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 Der`Graph` Mit dem Objekt können Sie Formen auf der Seite hinzufügen und bearbeiten.

## Schritt 4: Zeichnen Sie die erste Linie

Jetzt ist es Zeit, Ihre erste Linie zu zeichnen. In diesem Beispiel wird eine Linie von der unteren linken Ecke zur oberen rechten Ecke der Seite gezeichnet:

```csharp
// Erstellen Sie das erste Zeilenobjekt von der unteren linken bis zur oberen rechten Ecke der Seite
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Linie zur Formensammlung des Graph-Objekts hinzufügen
graph.Shapes.Add(line);
```

 Der`Line` Klasse nimmt die Koordinaten für den Start- und Endpunkt der Linie. Hier,`pg.Rect.LLX` Und`pg.Rect.URY` stellen jeweils die untere linke und obere rechte Ecke der Seite dar.

## Schritt 5: Zeichnen Sie die zweite Linie

Für die zweite Linie zeichnen wir von der oberen linken Ecke zur unteren rechten Ecke:

```csharp
// Zeichnen Sie eine Linie von der oberen linken Ecke der Seite zur unteren rechten Ecke der Seite
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Linie zur Formensammlung des Graph-Objekts hinzufügen
graph.Shapes.Add(line2);
```

Diese Linie verläuft diagonal in die entgegengesetzte Richtung über die Seite.

## Schritt 6: Fügen Sie das Diagramm zur Seite hinzu

 Wenn die Linien gezeichnet sind, müssen Sie nun die`Graph` Einspruch gegen die Absatzsammlung der Seite erheben:

```csharp
// Graph-Objekt zur Absatzsammlung der Seite hinzufügen
pg.Paragraphs.Add(graph);
```

 Dieser Schritt integriert die`Graph` Objekt (mit Ihren Zeilen) in die PDF-Seite.

## Schritt 7: Speichern Sie das Dokument

Speichern Sie Ihr Dokument abschließend in einer Datei:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// PDF-Datei speichern
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 Dadurch wird das PDF mit den gezeichneten Linien gespeichert und die`Console.WriteLine` Anweisung bestätigt, dass der Vorgang erfolgreich war.

## Abschluss

Das Zeichnen von Linien in einem PDF-Dokument mit Aspose.PDF für .NET ist ein unkomplizierter Vorgang, wenn Sie ihn in überschaubare Schritte aufteilen. In diesem Tutorial haben Sie gelernt, wie Sie ein PDF-Dokument einrichten, Linien darin zeichnen und das Endprodukt speichern. Egal, ob Sie Diagramme erstellen, Text hervorheben oder einfach mit PDF-Manipulationen experimentieren, dieses Handbuch bietet eine solide Grundlage für die Arbeit mit Linien in PDFs.

 Wenn Sie Fragen haben oder weitere Hilfe benötigen, wenden Sie sich bitte an die[Aspose.PDF-Dokumentation](https://reference.aspose.com/pdf/net/) oder besuchen Sie die[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).

## Häufig gestellte Fragen

### Kann ich außer Linien auch andere Formen zeichnen?
 Ja, Sie können verschiedene Formen wie Rechtecke, Ellipsen und Polygone zeichnen mit dem`Aspose.Pdf.Drawing` Namespace.

### Wie passe ich die Farbe und Dicke der Linien an?
 Sie können die`Line` Objekt`StrokeColor` Und`LineWidth` Eigenschaften, um das Erscheinungsbild Ihrer Linien anzupassen.

### Ist es möglich, Linien auf bestimmte Bereiche einer Seite zu zeichnen?
 Absolut! Passen Sie einfach die Koordinaten des`Line` Objekt, um die Linien nach Bedarf zu positionieren.

### Kann ich den Zeilen Text hinzufügen?
 Ja, Sie können Text hinzufügen, indem Sie`TextFragment` Objekte und deren Platzierung im`Paragraphs` Sammlung der Seite.

### Was ist, wenn ich einer vorhandenen PDF-Datei Zeilen hinzufügen möchte, anstatt eine neue zu erstellen?
 Sie können eine vorhandene PDF-Datei laden mit`Document` und verwenden Sie dann ähnliche Methoden, um den vorhandenen Seiten Zeilen hinzuzufügen.