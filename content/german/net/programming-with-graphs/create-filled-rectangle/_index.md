---
title: Gefülltes Rechteck erstellen
linktitle: Gefülltes Rechteck erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET ein gefülltes Rechteck in einer PDF-Datei erstellen. Perfekt für Entwickler aller Niveaus.
type: docs
weight: 50
url: /de/net/programming-with-graphs/create-filled-rectangle/
---
## Einführung

Wollten Sie schon immer visuell ansprechende PDFs programmgesteuert erstellen? Dann sind Sie hier genau richtig! In diesem Tutorial tauchen wir in die Welt von Aspose.PDF für .NET ein, einer leistungsstarken Bibliothek, mit der Sie PDF-Dokumente ganz einfach bearbeiten können. Heute konzentrieren wir uns auf das Erstellen eines gefüllten Rechtecks in einer PDF-Datei. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Anleitung führt Sie auf freundliche und ansprechende Weise durch jeden Schritt. Also, schnappen Sie sich Ihren Programmierhut und legen Sie los!

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen einige Dinge bereitstehen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Es ist eine fantastische IDE für die .NET-Entwicklung.
2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie finden sie[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Ein wenig Vertrautheit mit der C#-Programmierung hilft Ihnen, die Codeausschnitte besser zu verstehen.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

### Neues Projekt erstellen

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt. Der Einfachheit halber können Sie eine Konsolenanwendung wählen.

### Aspose.PDF-Referenz hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nachdem wir nun alles eingerichtet haben, tauchen wir in den Code ein!

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen Sie den Pfad angeben, in dem Ihre PDF-Datei gespeichert wird. Dies ist wichtig, da es dem Programm mitteilt, wo die Datei erstellt werden soll.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad auf Ihrem Computer, in dem Sie die PDF-Datei speichern möchten.

## Schritt 2: Erstellen einer Dokumentinstanz

 Als nächstes erstellen wir eine Instanz des`Document`Klasse. Diese Klasse stellt das PDF-Dokument dar, mit dem Sie arbeiten werden.

```csharp
// Dokumentinstanz erstellen
Document doc = new Document();
```

Diese Zeile initialisiert ein neues PDF-Dokument, das wir bearbeiten können.

## Schritt 3: Dem Dokument eine Seite hinzufügen

Fügen wir nun unserem Dokument eine Seite hinzu. Jedes PDF benötigt mindestens eine Seite, oder?

```csharp
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
```

Dieser Code fügt dem Dokument eine neue Seite hinzu, auf der wir Formen zeichnen können.

## Schritt 4: Erstellen einer Graph-Instanz

 Um Formen zu zeichnen, müssen wir eine`Graph` Beispiel. Stellen Sie sich ein Diagramm als eine Leinwand vor, auf der Sie verschiedene Formen zeichnen können.

```csharp
// Graph-Instanz erstellen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Hier erstellen wir ein Diagramm mit einer Breite von 100 und einer Höhe von 400.

## Schritt 5: Fügen Sie das Diagramm zur Seite hinzu

Da wir nun unser Diagramm haben, fügen wir es der Seite hinzu, die wir zuvor erstellt haben.

```csharp
// Fügen Sie der Absatzsammlung der Seiteninstanz ein Diagrammobjekt hinzu
page.Paragraphs.Add(graph);
```

Diese Linie verbindet das Diagramm mit der Seite und macht es bereit zum Zeichnen.

## Schritt 6: Erstellen Sie eine Rechteckinstanz

Als nächstes erstellen wir ein Rechteck, das wir mit Farbe füllen möchten.

```csharp
// Rechteckinstanz erstellen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

In diesem Code definieren wir die Position und Größe des Rechtecks. Die Parameter stellen die x- und y-Koordinaten, Breite und Höhe dar.

## Schritt 7: Füllfarbe festlegen

Wählen wir nun eine Farbe für unser Rechteck. Für dieses Beispiel füllen wir es mit Rot.

```csharp
// Füllfarbe für Graph-Objekt festlegen
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Diese Zeile setzt die Füllfarbe des Rechtecks auf Rot. Sie können jede beliebige Farbe wählen!

## Schritt 8: Fügen Sie dem Diagramm das Rechteck hinzu

Nachdem unser Rechteck fertig ist, ist es Zeit, es dem Diagramm hinzuzufügen.

```csharp
// Fügen Sie der Formensammlung des Graph-Objekts ein rechteckiges Objekt hinzu
graph.Shapes.Add(rect);
```

Dieser Code fügt dem Diagramm das Rechteck hinzu und macht es zu einem Teil unserer Zeichnung.

## Schritt 9: Speichern Sie das PDF-Dokument

Schließlich müssen wir unser Dokument im angegebenen Verzeichnis speichern.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
```

 Dieser Code speichert die PDF-Datei unter dem Namen`CreateFilledRectangle_out.pdf` in dem Verzeichnis, das Sie zuvor angegeben haben.

## Schritt 10: Bestätigungsnachricht

Damit wir wissen, dass alles reibungslos geklappt hat, können wir eine Bestätigungsnachricht ausdrucken.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Diese Zeile gibt eine Meldung in der Konsole aus, die bestätigt, dass das ausgefüllte Rechteck erfolgreich erstellt wurde.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich ein ausgefülltes Rechteck in einem PDF-Dokument mit Aspose.PDF für .NET erstellt. Diese leistungsstarke Bibliothek eröffnet eine Welt voller Möglichkeiten zur PDF-Manipulation und ermöglicht Ihnen die programmgesteuerte Erstellung atemberaubender Dokumente. Egal, ob Sie Berichte, Rechnungen oder andere PDF-Typen erstellen, Aspose.PDF bietet alles, was Sie brauchen.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen der Bibliothek erkunden können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Gibt es eine Möglichkeit, Support für Aspose.PDF zu erhalten?
 Absolut! Sie können Unterstützung über das Aspose-Forum erhalten[Hier](https://forum.aspose.com/c/pdf/10).

### Wie kann ich Aspose.PDF kaufen?
 Sie können Aspose.PDF kaufen, indem Sie die Kaufseite besuchen[Hier](https://purchase.aspose.com/buy).

### Welche Arten von Formen kann ich mit Aspose.PDF erstellen?
Mit der Aspose.PDF-Bibliothek können Sie verschiedene Formen erstellen, darunter Rechtecke, Kreise, Linien und mehr.