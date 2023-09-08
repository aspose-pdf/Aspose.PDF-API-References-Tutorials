---
title: Fügen Sie einen Datums- und Zeitstempel in der PDF-Datei hinzu
linktitle: Fügen Sie einen Datums- und Zeitstempel in der PDF-Datei hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach einen Datums- und Zeitstempel in eine PDF-Datei einfügen.
type: docs
weight: 10
url: /de/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In diesem Artikel zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen Datums- und Zeitstempel in eine PDF-Datei einfügen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einen Datums- und Zeitstempel zu einer vorhandenen PDF-Datei hinzufügen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 1: Einrichten der Umgebung

Bevor Sie einem PDF-Dokument einen Datums- und Zeitstempel hinzufügen können, müssen Sie Ihre Entwicklungsumgebung einrichten. Hier sind die Schritte, die Sie befolgen müssen:

1. Öffnen Sie Ihre bevorzugte IDE (Integrated Development Environment).
2. Erstellen Sie ein neues C#-Projekt.
3. Stellen Sie sicher, dass Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

## Schritt 2: Hinzufügen der Aspose.PDF-Bibliothek

Für die Arbeit mit PDF-Dokumenten in Ihrem Projekt ist die Aspose.PDF-Bibliothek für .NET erforderlich.

## Schritt 3: Laden des PDF-Dokuments

Der erste Schritt zum Hinzufügen eines Datums- und Zeitstempels besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 4: Erstellen des Datums- und Zeitstempels

Nachdem Sie das Dokument hochgeladen haben

  PDF können Sie den hinzuzufügenden Datums- und Zeitstempel erstellen. So geht's:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Erstellen Sie einen Textpuffer
TextStamp textStamp = new TextStamp(annotationText);
```

Der obige Code erstellt einen neuen Textpuffer, der das aktuelle Datum und die aktuelle Uhrzeit enthält.

## Schritt 5: Stempeleigenschaften konfigurieren

Bevor Sie den Stempel zum PDF-Dokument hinzufügen, können Sie verschiedene Eigenschaften des Stempels konfigurieren, wie z. B. Rand, horizontale und vertikale Ausrichtung usw. So geht's:

```csharp
// Puffereigenschaften festlegen
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen.

## Schritt 6: Stempel zum PDF hinzufügen

Da der Datums- und Zeitstempel nun fertig ist, können Sie ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
// Fügen Sie den Stempel zur Briefmarkensammlung der Seite hinzu
pdfDocument.Pages[1].AddStamp(textStamp);
```

Der obige Code fügt den Stempel auf der ersten Seite des PDF-Dokuments hinzu. Bei Bedarf können Sie eine andere Seite angeben.

## Schritt 7: Speichern Sie das Ausgabedokument

Sobald Sie den Datums- und Zeitstempel hinzugefügt haben, können Sie das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für das Hinzufügen eines Datums-/Zeitstempels mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Textstempel erstellen
TextStamp textStamp = new TextStamp(annotationText);

// Legen Sie die Eigenschaften des Stempels fest
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Stempel zur Briefmarkensammlung hinzufügen
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen Datums- und Zeitstempel hinzufügen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden, um PDF-Dokumenten Datums- und Zeitstempel hinzuzufügen.

### FAQs zum Hinzufügen eines Datums-/Zeitstempels in einer PDF-Datei

#### F: Was ist der Zweck des Hinzufügens eines Datums- und Zeitstempels zu einem PDF-Dokument mit Aspose.PDF für .NET?

A: Das Hinzufügen eines Datums- und Zeitstempels zu einem PDF-Dokument erhöht seinen Informationswert, indem es anzeigt, wann das Dokument geändert oder erstellt wurde. Diese Funktion ist nützlich, um Dokumentänderungen zu verfolgen und einen Referenzpunkt für den Dokumentverlauf bereitzustellen.

#### F: Kann ich das Format des Datums- und Zeitstempels an bestimmte Anforderungen anpassen?

 A: Ja, Sie können das Format des Datums- und Zeitstempels nach Ihren Wünschen anpassen. Der bereitgestellte C#-Quellcode verwendet die`DateTime.Now.ToString()` Methode zum Generieren des Zeitstempels in einem bestimmten Format. Sie können diesen Code ändern, um den Zeitstempel nach Bedarf zu formatieren.

#### F: Ist es möglich, den Datums- und Zeitstempel an einer bestimmten Stelle auf einer PDF-Seite hinzuzufügen?

 A: Auf jeden Fall können Sie die Platzierung des Datums- und Zeitstempels auf der PDF-Seite anpassen, indem Sie die Eigenschaften der Seite ändern`TextStamp` Objekt. Der im Tutorial bereitgestellte Code zeigt, wie Eigenschaften wie Rand, Ausrichtung und vertikale Positionierung festgelegt werden.

#### F: Kann ich verschiedenen Seiten desselben PDF-Dokuments mehrere Datums- und Zeitstempel hinzufügen?

 A: Ja, Sie können verschiedenen Seiten desselben PDF-Dokuments mehrere Datums- und Zeitstempel hinzufügen. Wiederholen Sie einfach den Vorgang zum Erstellen eines`TextStamp` Objekt und Konfigurieren seiner Eigenschaften für jede gewünschte Seite.

#### F: Wie kann ich die Schriftart, Größe oder Farbe des Datums- und Zeitstempeltexts ändern?

 A: Um die Schriftart, Größe oder Farbe des Datums- und Zeitstempeltexts zu ändern, können Sie die Eigenschaften des anpassen`DefaultAppearance` Objekt, das zum Erstellen des verwendet wird`TextStamp`. Passen Sie den Namen, die Größe und die Farbwerte der Schriftart an, um das gewünschte Erscheinungsbild zu erzielen.

#### F: Ist es möglich, mit Aspose.PDF für .NET andere Arten von Anmerkungen oder Stempeln zu einem PDF-Dokument hinzuzufügen?

A: Ja, Aspose.PDF für .NET bietet eine breite Palette an Anmerkungstypen, die Sie zu PDF-Dokumenten hinzufügen können, darunter Textanmerkungen, Stempel, Linien, Formen und mehr. Weitere Informationen zum Arbeiten mit Anmerkungen finden Sie in der Aspose.PDF-Dokumentation.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen beim Hinzufügen eines Datums- und Zeitstempels zu einem PDF-Dokument?

A: Das Hinzufügen eines Datums- und Zeitstempels ist zwar unkompliziert, berücksichtigen Sie jedoch Faktoren wie das Layout des Dokuments und den vorhandenen Inhalt. Stellen Sie sicher, dass die Platzierung des Stempels keine wichtigen Informationen verdeckt oder die Lesbarkeit des Dokuments beeinträchtigt.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren, um PDF-Dokumenten Datums- und Zeitstempel hinzuzufügen?

A: Um diese Methode zu integrieren, befolgen Sie die bereitgestellten Schritte und passen Sie den Code an die Struktur Ihres Projekts an. Sie können vorhandenen PDF-Dokumenten Datums- und Zeitstempel hinzufügen, um deren Nützlichkeit zu erhöhen und eine klare Zeitleiste für Änderungen bereitzustellen.

#### F: Kann ich das Hinzufügen von Datums- und Zeitstempeln zu mehreren PDF-Dokumenten automatisieren?

A: Ja, Sie können den Prozess des Hinzufügens von Datums- und Zeitstempeln zu mehreren PDF-Dokumenten automatisieren, indem Sie ein Skript oder Programm erstellen, das eine Liste von Dokumenten durchläuft und auf jedes einzelne den gleichen Stempelprozess anwendet.