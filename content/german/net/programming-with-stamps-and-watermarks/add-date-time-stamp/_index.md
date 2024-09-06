---
title: Datums-/Zeitstempel zur PDF-Datei hinzufügen
linktitle: Datums-/Zeitstempel zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach einen Datums- und Zeitstempel in eine PDF-Datei einfügen.
type: docs
weight: 10
url: /de/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In diesem Artikel zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen Datums- und Zeitstempel in eine PDF-Datei einfügen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einer vorhandenen PDF-Datei einen Datums- und Zeitstempel hinzufügen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 1: Einrichten der Umgebung

Bevor Sie einem PDF-Dokument einen Datums- und Zeitstempel hinzufügen können, müssen Sie Ihre Entwicklungsumgebung einrichten. Hier sind die folgenden Schritte:

1. Öffnen Sie Ihre bevorzugte IDE (Integrated Development Environment).
2. Erstellen Sie ein neues C#-Projekt.
3. Stellen Sie sicher, dass Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

## Schritt 2: Hinzufügen der Aspose.PDF-Bibliothek

Die Aspose.PDF-Bibliothek für .NET wird zum Arbeiten mit PDF-Dokumenten in Ihrem Projekt benötigt.

## Schritt 3: Laden des PDF-Dokuments

Der erste Schritt zum Hinzufügen eines Datums- und Zeitstempels besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 4: Datums- und Zeitstempel erstellen

Nachdem Sie das Dokument hochgeladen haben

  PDF können Sie den hinzuzufügenden Datums- und Zeitstempel erstellen. So geht's:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Erstellen eines Textpuffers
TextStamp textStamp = new TextStamp(annotationText);
```

Der obige Code erstellt einen neuen Textpuffer, der das aktuelle Datum und die aktuelle Uhrzeit enthält.

## Schritt 5: Stempeleigenschaften konfigurieren

Bevor Sie den Stempel zum PDF-Dokument hinzufügen, können Sie verschiedene Eigenschaften des Stempels konfigurieren, wie etwa Rand, horizontale und vertikale Ausrichtung usw. So gehen Sie vor:

```csharp
// Puffereigenschaften festlegen
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Sie können diese Eigenschaften Ihren Bedürfnissen entsprechend anpassen.

## Schritt 6: Stempel zum PDF hinzufügen

Nachdem der Datums- und Zeitstempel nun fertig ist, können Sie ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. So geht's:

```csharp
// Den Stempel zur Stempelsammlung der Seite hinzufügen
pdfDocument.Pages[1].AddStamp(textStamp);
```

Der obige Code fügt den Stempel der ersten Seite des PDF-Dokuments hinzu. Sie können bei Bedarf eine andere Seite angeben.

## Schritt 7: Speichern des Ausgabedokuments

Nachdem Sie Datum und Zeitstempel hinzugefügt haben, können Sie das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern des Ausgabedokuments
pdfDocument.Save(dataDir);
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode zum Hinzufügen eines Datums-/Zeitstempels mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Textstempel erstellen
TextStamp textStamp = new TextStamp(annotationText);

// Eigenschaften des Stempels festlegen
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Briefmarke zur Briefmarkensammlung hinzufügen
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

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen Datums- und Zeitstempel hinzufügen. Jetzt können Sie dieses Wissen in Ihren eigenen Projekten anwenden, um Datums- und Zeitstempel zu PDF-Dokumenten hinzuzufügen.

### FAQs zum Hinzufügen eines Datums-/Zeitstempels in einer PDF-Datei

#### F: Was ist der Zweck des Hinzufügens eines Datums- und Zeitstempels zu einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Hinzufügen eines Datums- und Zeitstempels zu einem PDF-Dokument wird dessen Informationswert erhöht, da dadurch angezeigt wird, wann das Dokument geändert oder erstellt wurde. Diese Funktion ist nützlich, um Dokumentänderungen zu verfolgen und einen Referenzpunkt für den Dokumentverlauf bereitzustellen.

#### F: Kann ich das Format des Datums- und Zeitstempels an bestimmte Anforderungen anpassen?

 A: Ja, Sie können das Format des Datums- und Zeitstempels nach Ihren Wünschen anpassen. Der bereitgestellte C#-Quellcode verwendet das`DateTime.Now.ToString()` Methode, um den Zeitstempel in einem bestimmten Format zu generieren. Sie können diesen Code ändern, um den Zeitstempel nach Bedarf zu formatieren.

#### F: Ist es möglich, an einer bestimmten Stelle auf einer PDF-Seite einen Datums- und Zeitstempel hinzuzufügen?

 A: Natürlich. Sie können die Platzierung des Datums- und Zeitstempels auf der PDF-Seite anpassen, indem Sie die Eigenschaften des`TextStamp` Objekt. Der im Tutorial bereitgestellte Code zeigt, wie Eigenschaften wie Rand, Ausrichtung und vertikale Positionierung festgelegt werden.

#### F: Kann ich verschiedenen Seiten desselben PDF-Dokuments mehrere Datums- und Zeitstempel hinzufügen?

 A: Ja, Sie können mehrere Datums- und Zeitstempel auf verschiedenen Seiten desselben PDF-Dokuments hinzufügen. Wiederholen Sie einfach den Vorgang zum Erstellen eines`TextStamp` -Objekt und Konfigurieren seiner Eigenschaften für jede gewünschte Seite.

#### F: Wie kann ich die Schriftart, Größe oder Farbe des Datums- und Zeitstempeltextes ändern?

 A: Um die Schriftart, Größe oder Farbe des Datums- und Zeitstempeltextes zu ändern, können Sie die Eigenschaften des`DefaultAppearance` Objekt zum Erstellen des`TextStamp`. Passen Sie den Schriftnamen, die Größe und die Farbwerte an, um das gewünschte Erscheinungsbild zu erzielen.

#### F: Ist es möglich, mit Aspose.PDF für .NET einem PDF-Dokument andere Arten von Anmerkungen oder Stempeln hinzuzufügen?

A: Ja, Aspose.PDF für .NET bietet eine breite Palette von Anmerkungstypen, die Sie zu PDF-Dokumenten hinzufügen können, darunter Textanmerkungen, Stempel, Linien, Formen und mehr. Weitere Einzelheiten zum Arbeiten mit Anmerkungen finden Sie in der Aspose.PDF-Dokumentation.

#### F: Gibt es Einschränkungen oder Überlegungen beim Hinzufügen eines Datums- und Zeitstempels zu einem PDF-Dokument?

A: Das Hinzufügen eines Datums- und Zeitstempels ist zwar unkompliziert, berücksichtigen Sie jedoch Faktoren wie das Layout des Dokuments und den vorhandenen Inhalt. Stellen Sie sicher, dass die Platzierung des Stempels keine wichtigen Informationen verdeckt oder die Lesbarkeit des Dokuments beeinträchtigt.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren, um PDF-Dokumente mit Datums- und Zeitstempeln zu versehen?

A: Um diese Methode zu integrieren, folgen Sie den angegebenen Schritten und passen Sie den Code an die Struktur Ihres Projekts an. Sie können vorhandenen PDF-Dokumenten Datums- und Zeitstempel hinzufügen, um ihre Nützlichkeit zu verbessern und eine klare Zeitleiste der Änderungen bereitzustellen.

#### F: Kann ich das Hinzufügen von Datums- und Zeitstempeln zu mehreren PDF-Dokumenten automatisieren?

A: Ja, Sie können das Hinzufügen von Datums- und Zeitstempeln zu mehreren PDF-Dokumenten automatisieren, indem Sie ein Skript oder Programm erstellen, das eine Liste von Dokumenten durchläuft und auf jedes Dokument denselben Stempelvorgang anwendet.