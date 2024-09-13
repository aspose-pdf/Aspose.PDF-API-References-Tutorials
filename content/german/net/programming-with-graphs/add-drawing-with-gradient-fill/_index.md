---
title: Zeichnung mit Verlaufsfüllung hinzufügen
linktitle: Zeichnung mit Verlaufsfüllung hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET beeindruckende Verlaufszeichnungen in PDF-Dateien einfügen – ideal zum Verbessern der visuellen Darstellung von Dokumenten.
type: docs
weight: 20
url: /de/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
## Einführung

Das Erstellen optisch ansprechender Dokumente ist in der heutigen digitalen Welt unerlässlich. Eine beeindruckende Technik zum Verbessern Ihrer PDF-Dokumente ist das Hinzufügen von Zeichnungen mit Verlaufsfüllungen. Wenn Sie Ihre Fähigkeiten im Dokumentdesign verbessern möchten, sind Sie hier richtig! In dieser Anleitung werde ich Sie durch den Prozess der Verwendung von Aspose.PDF für .NET führen, um Ihrem PDF eine atemberaubende Zeichnung mit Verlaufsfüllung hinzuzufügen.

## Voraussetzungen

Bevor wir ins Detail gehen, hier ein paar Dinge, die Sie vorbereitet haben müssen:

1.  Aspose.PDF für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Sie erhalten sie von der[Downloadlink](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung wie Visual Studio ein, in der Sie Ihren Code schreiben und ausführen können.
3. Grundlegende Kenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie den Anweisungen leichter folgen.

Sobald Sie die oben genannten Voraussetzungen erfüllt haben, können wir mit der Implementierung beginnen!

## Pakete importieren

Zunächst müssen Sie die erforderlichen Pakete in Ihr Projekt importieren. So geht's:

- Öffnen Sie Ihr C#-Projekt in Visual Studio.
- Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek hinzu. Sie können dies über den NuGet-Paket-Manager tun:
  
```csharp
using Aspose.Pdf.Drawing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Lassen Sie uns den Prozess nun in leicht verständliche Schritte unterteilen. 

## Schritt 1: Einrichten des Dokumentverzeichnisses

Zunächst müssen Sie einen Pfad für Ihre Dokumente festlegen. So können Sie leichter organisieren, wo Sie die erstellten PDF-Dateien speichern.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihren Verzeichnispfad.
```
 Diese Codezeile erstellt eine Variable`dataDir` , das den Pfad zum Verzeichnis enthält, in dem die Ausgabe-PDF gespeichert wird. Stellen Sie sicher, dass Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch Ihren tatsächlichen Verzeichnispfad.

## Schritt 2: Ein neues PDF-Dokument erstellen

Als Nächstes erstellen wir mit der Aspose.PDF-Bibliothek ein neues PDF-Dokument.

```csharp
Document doc = new Document();
```
 Hier instantiieren wir ein`Document` Objekt. Dieses Objekt stellt Ihr PDF-Dokument dar und fungiert als Container für alle Elemente, die Sie hinzufügen möchten.

## Schritt 3: Dem Dokument eine Seite hinzufügen

Jetzt, da unser Dokument fertig ist, ist es Zeit, eine Seite hinzuzufügen.

```csharp
Page page = doc.Pages.Add();
```
Diese Zeile fügt Ihrem Dokument eine neue Seite hinzu. Sie bietet Platz für alle Grafiken und Texte, die Sie einfügen möchten.

## Schritt 4: Erstellen Sie ein Grafikobjekt

Um Formen zu zeichnen, müssen wir zuerst einen Grafikbereich auf der Seite erstellen.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300.0, 300.0);
page.Paragraphs.Add(graph);
```
In diesem Fall erstellen wir ein Grafikobjekt mit einer Breite und Höhe von 300 Einheiten. Indem wir es den Absätzen der Seite hinzufügen, legen wir die Grundlage für unsere Zeichnungen.

## Schritt 5: Definieren Sie eine rechteckige Form

Als Nächstes definieren wir eine rechteckige Form, die wir mit einer Verlaufsfarbe füllen möchten.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```
Hier erstellen wir ein Rechteck, das bei den Koordinaten (0,0) beginnt und sich über eine Breite und Höhe von 300 Einheiten erstreckt. Dieses Rechteck wird dann unserem Grafikobjekt hinzugefügt.

## Schritt 6: Farbverlaufsfüllung auf das Rechteck anwenden

Jetzt kommt der spaßige Teil! Wir werden unserem Rechteck eine Verlaufsfüllung hinzufügen.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
    PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
    {
        Start = new Point(0, 0),
        End = new Point(300, 300)
    }
};
```
 In diesem Codeblock legen wir fest, dass die Füllfarbe des Rechtecks ein Farbverlauf von Rot nach Blau sein soll.`GradientAxialShading`Die Klasse ermöglicht die Definition einer Verlaufsfüllung, wobei Sie Start- und Endpunkte angeben können, um einen sanften Übergang zwischen den Farben zu erzeugen.

## Schritt 7: Speichern Sie das PDF-Dokument

Abschließend müssen wir unser Dokument im angegebenen Verzeichnis speichern.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```
 Dieser Befehl speichert Ihr PDF unter einem bestimmten Namen im zuvor definierten`dataDir`Das Ergebnis ist eine schön gestaltete PDF-Datei mit einem mit einem Farbverlauf gefüllten Rechteck.

## Abschluss

Und da haben Sie es! Sie haben gerade gelernt, wie Sie mit Aspose.PDF für .NET eine Zeichnung mit Farbverlaufsfüllung zu Ihrem PDF-Dokument hinzufügen. Ist es nicht erstaunlich, wie ein paar Zeilen Code ein einfaches PDF in etwas visuell Beeindruckendes verwandeln können? Egal, ob Sie Berichte, Rechnungen oder andere Dokumente erstellen, die Verwendung von Grafiken kann das Leseerlebnis erheblich verbessern.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen und zu bearbeiten.

### Kann ich Aspose.PDF kostenlos nutzen?
 Sie können beginnen mit einem[Kostenlose Testversion](https://releases.aspose.com/) um die Funktionen zu erkunden, es kann jedoch zu Nutzungseinschränkungen kommen.

### Wo finde ich weitere Dokumentation?
Eine ausführliche Dokumentation finden Sie auf der[Aspose PDF Referenzseite](https://reference.aspose.com/pdf/net/).

### Wie kaufe ich Aspose.PDF?
 Sie können die Aspose.PDF-Bibliothek über deren[Kauflink](https://purchase.aspose.com/buy).

### Was ist, wenn ich Hilfe bei der Verwendung von Aspose.PDF benötige?
 Wenn Sie auf Probleme stoßen, können Sie Hilfe auf der[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).