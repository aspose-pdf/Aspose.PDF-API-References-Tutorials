---
title: Strichlänge
linktitle: Strichlänge
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie Strichmuster in PDFs mit Aspose.PDF für .NET anpassen. Perfekt, um Ihren Dokumenten Stil zu verleihen.
type: docs
weight: 70
url: /de/net/programming-with-graphs/dash-length/
---
## Einführung

Möchten Sie Ihren PDF-Dokumenten einen Hauch von Kreativität verleihen, indem Sie Linien mit verschiedenen Strichmustern anpassen? Mit Aspose.PDF für .NET können Sie Linienstile ganz einfach an die Anforderungen Ihres Dokuments anpassen. In diesem Tutorial erfahren Sie, wie Sie die Strichlänge von Linien in einem PDF-Dokument mit Aspose.PDF für .NET anpassen. Egal, ob Sie eine gestrichelte Linie oder ein gepunktetes Muster anstreben, diese Anleitung bietet Ihnen die erforderlichen Tools und Schritte, um das gewünschte Ergebnis zu erzielen.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, benötigen Sie Folgendes:

1. Aspose.PDF für .NET: Stellen Sie sicher, dass Sie Aspose.PDF für .NET installiert haben. Wenn Sie es noch nicht installiert haben, können Sie es hier herunterladen:[Aspose.PDF für .NET](https://releases.aspose.com/pdf/net/).
2. Grundkenntnisse in C#: Dieses Tutorial setzt voraus, dass Sie über Grundkenntnisse in der C#-Programmierung verfügen. Wenn Sie neu bei C# sind, sollten Sie zunächst die Grundlagen auffrischen.
3. Visual Studio: Sie können zwar jede beliebige IDE verwenden, in diesem Handbuch wird jedoch davon ausgegangen, dass Sie Visual Studio zum Schreiben und Ausführen Ihres C#-Codes verwenden.
4.  Aspose-Konto: Für zusätzliche Ressourcen und Support stellen Sie sicher, dass Sie ein Konto bei Aspose haben. Sie können sich für ein[Kostenlose Testversion](https://releases.aspose.com/) oder eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy).

## Pakete importieren

Um mit Aspose.PDF für .NET arbeiten zu können, müssen Sie die entsprechenden Namespaces importieren. So können Sie das tun:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Diese Namespaces umfassen die Klassen und Methoden, die zum Arbeiten mit PDF-Dokumenten, Zeichnungen und Linien erforderlich sind.

## Schritt 1: Richten Sie Ihr Projekt ein

Bevor Sie mit dem Codieren beginnen, richten Sie in Visual Studio ein neues C#-Projekt ein. Fügen Sie Ihrem Projekt die Bibliothek Aspose.PDF für .NET über NuGet oder durch manuelles Verweisen auf die DLL hinzu. 

## Schritt 2: Initialisieren Sie das Dokument

Erstellen Sie zunächst ein neues PDF-Dokument und fügen Sie ihm eine Seite hinzu. Dies ist die Leinwand, auf der Sie Ihre Linien zeichnen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz instantiieren
Document doc = new Document();

// Seite zur Seitensammlung des Dokumentobjekts hinzufügen
Page page = doc.Pages.Add();
```

 Hier erstellen wir eine`Document` Objekt und fügen Sie ein neues`Page` dazu. Dies bildet die Grundlage für das Zeichnen Ihrer Linie.

## Schritt 3: Erstellen Sie das Zeichenobjekt

 Erstellen Sie als Nächstes eine`Graph` Objekt, das den Bereich darstellt, in dem Sie zeichnen werden. Definieren Sie die Abmessungen entsprechend Ihren Anforderungen.

```csharp
// Zeichenobjekt mit bestimmten Abmessungen erstellen
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Zeichenobjekt zur Absatzsammlung der Seiteninstanz hinzufügen
page.Paragraphs.Add(canvas);
```

 Der`Graph` Objekt fungiert als Container für Ihre Zeichenelemente. Hier ist es auf eine Breite von 100 Einheiten und eine Höhe von 400 Einheiten eingestellt.

## Schritt 4: Definieren Sie die Linie

 Jetzt ist es an der Zeit, die`Line`Objekt. Geben Sie die Start- und Endpunkte der Linie an und passen Sie ihren Stil an.

```csharp
// Linienobjekt erstellen
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Diese Linie beginnt bei den Koordinaten (100, 100) und endet bei (200, 100). Sie können diese Koordinaten Ihren spezifischen Anforderungen entsprechend anpassen.

## Schritt 5: Den Linienstil anpassen

Legen Sie die Farbe und das Strichmuster der Linie fest. So können Sie dafür sorgen, dass Ihre Linie hervorsticht.

```csharp
// Farbe für Linienobjekt festlegen
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Strich-Array für Linienobjekt festlegen
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Festlegen der Strichphase für die Linieninstanz
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Legt die Farbe der Linie fest. In diesem Fall ist sie rot.
- `line.GraphInfo.DashArray` : Definiert das Strichmuster. Hier`{ 0, 1, 0 }` stellt ein gestricheltes Muster dar.
- `line.GraphInfo.DashPhase`: Passt den Startpunkt des Strichmusters an.

## Schritt 6: Fügen Sie der Zeichnung die Linie hinzu

 Fügen Sie Ihre gestaltete Linie zum`Graph` Objekt.

```csharp
// Linie zur Formensammlung des Zeichenobjekts hinzufügen
canvas.Shapes.Add(line);
```

Dadurch wird die Linie in Ihre Zeichenfläche integriert.

## Schritt 7: Speichern Sie das Dokument

Speichern Sie Ihr Dokument abschließend in einem angegebenen Pfad. Dort wird die PDF-Datei erstellt.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// PDF-Dokument speichern
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Diese Codezeile speichert das PDF-Dokument und gibt eine Bestätigungsmeldung aus, die angibt, wo die Datei gespeichert wurde.

## Abschluss

Durch Anpassen der Linienstile in PDF-Dokumenten können Sie Ihren Berichten, Präsentationen und anderen Dokumenten eine professionelle Note verleihen. In diesem Tutorial haben Sie gelernt, wie Sie die Strichlänge von Linien mit Aspose.PDF für .NET anpassen. Egal, ob Sie einfache gestrichelte Linien oder komplexere Muster erstellen, Aspose.PDF bietet die Flexibilität, die Sie benötigen, um Ihre Dokumente hervorzuheben. Experimentieren Sie mit verschiedenen Strichmustern und Farben, um den Stil zu finden, der Ihren Anforderungen am besten entspricht.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.PDF für .NET?
 Sie können es über NuGet in Visual Studio installieren oder von herunterladen[Asposes Website](https://releases.aspose.com/pdf/net/).

### Kann ich Aspose.PDF für .NET kostenlos nutzen?
 Ja, Aspose bietet eine[Kostenlose Testversion](https://releases.aspose.com/) So können Sie die Funktionen testen, bevor Sie eine Lizenz erwerben.

### Welche anderen Anpassungen kann ich an Zeilen in einer PDF-Datei vornehmen?
 Sie können Linienstärke, Farbe und Strichmuster anpassen. Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Details.

### Wie kann ich Unterstützung erhalten, wenn ich auf Probleme stoße?
 Sie erhalten Support über das[Aspose Forum](https://forum.aspose.com/c/pdf/10).

### Wo kann ich eine Lizenz für Aspose.PDF für .NET erwerben?
Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy).