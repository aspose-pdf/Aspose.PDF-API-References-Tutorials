---
title: Seitenzahlstempel in der PDF-Datei
linktitle: Seitenzahlstempel in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Seitenzahlenstempel in PDF-Dateien einfügen.
type: docs
weight: 160
url: /de/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Seitenzahlenstempel in PDF-Dateien einfügen. Wir verwenden den bereitgestellten C#-Quellcode, um ein vorhandenes PDF-Dokument zu öffnen, einen Seitenzahlenstempel zu erstellen, seine Eigenschaften festzulegen und ihn einer bestimmten Seite in der PDF-Datei hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Vorhandenes PDF-Dokument laden

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen und Konfigurieren des Seitennummerierungsstempels

Nachdem das PDF-Dokument geladen ist, können wir einen Seitennummerierungspuffer erstellen und ihn nach unseren Anforderungen konfigurieren. So geht's:

```csharp
// Erstellen eines Seitenzahlenpuffers
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definieren Sie, ob der Puffer im Hintergrund ist oder nicht
pageNumberStamp.Background = false;

// Format des Seitennummerierungspuffers
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Unterer Rand des Seitennummerierungspuffers
pageNumberStamp.BottomMargin = 10;

// Horizontale Ausrichtung des Seitennummerierungspuffers
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Startzahl der Seitennummerierung
pageNumberStamp.StartingNumber = 1;

// Festlegen der Texteigenschaften für den Seitenzahlenpuffer
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Der obige Code erstellt einen Seitenzahlenstempel mit Eigenschaften wie Seitenzahlenformat, unterem Rand, horizontaler Ausrichtung, Startnummer und Texteigenschaften.

## Schritt 4: Hinzufügen des Seitenzahlenstempels zu einer bestimmten Seite

Sobald der Seitenzahlenstempel konfiguriert ist, können wir ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. So geht's:

```csharp
// Den Seitenzahlenpuffer einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Der obige Code fügt der ersten Seite des PDF-Dokuments den Seitenzahlenstempel hinzu. Sie können die Seitenzahl nach Bedarf ändern.

## Schritt 5: Speichern des geänderten PDF-Dokuments

Sobald der Seitenzahlenstempel zum PDF-Dokument hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das bearbeitete PDF-Dokument speichern möchten.

### Beispiel-Quellcode für Seitenzahlstempel mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Seitenzahlenstempel erstellen
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Ob der Stempel Hintergrund ist
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Texteigenschaften festlegen
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Einer bestimmten Seite einen Stempel hinzufügen
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einem PDF-Dokument Seitenzahlenstempel hinzufügen. Sie können Ihre PDF-Dokumente jetzt personalisieren, indem Sie klare und informative Seitenzahlen hinzufügen.

### FAQs zu Seitenzahlenstempeln in PDF-Dateien

#### F: Was ist ein Seitenzahlstempel und wie wird er verwendet, um einer PDF-Datei Seitenzahlen hinzuzufügen?

A: Ein Seitenzahlstempel ist eine Funktion in Aspose.PDF, mit der Sie bestimmten Seiten eines PDF-Dokuments dynamische Seitenzahlen hinzufügen können. In diesem Tutorial wird dies erreicht, indem ein PageNumberStamp-Objekt erstellt, seine Eigenschaften konfiguriert und es einer bestimmten Seite hinzugefügt wird.

#### F: Wie ermöglicht der bereitgestellte C#-Quellcode das Hinzufügen von Seitenzahlenstempeln zu einer PDF-Datei?

A: Der Code zeigt, wie man ein vorhandenes PDF-Dokument lädt, einen Seitennummernstempel erstellt, verschiedene Eigenschaften (wie Format, Schriftart, Ausrichtung usw.) festlegt und dann den Stempel einer bestimmten Seite hinzufügt. Der Stempel berechnet automatisch die Gesamtseitenzahl und fügt die richtigen Seitenzahlen ein.

#### F: Kann ich das Erscheinungsbild der Seitenzahl, beispielsweise Schriftart, Farbe und Größe, anpassen?

A: Auf jeden Fall. Sie können das Erscheinungsbild des Seitenzahlenstempels anpassen, indem Sie Eigenschaften wie Schriftart, Schriftgröße, Schriftstil (fett, kursiv usw.) und Textfarbe anpassen.

#### F: Ist es möglich, mehreren Seiten in einem PDF-Dokument Seitenzahlenstempel hinzuzufügen?

A: Ja, Sie können mehreren Seiten Seitenzahlenstempel hinzufügen, indem Sie mehrere PageNumberStamp-Objekte erstellen und jedes zu den gewünschten Seiten hinzufügen.

#### F: Kann ich wählen, ob der Seitenzahlenstempel als Teil des Seiteninhalts oder als Hintergrundelement angezeigt wird?

 A: Ja, Sie können steuern, ob der Seitenzahlenstempel als Teil des Seiteninhalts oder als Hintergrundelement angezeigt wird, indem Sie die`Background` Eigenschaft des PageNumberStamp.

#### F: Wie gebe ich das Format der Seitenzahl einschließlich der Gesamtseitenzahl an?

 A: Der Code verwendet die`Format`Eigenschaft des PageNumberStamp, um das Format der Seitenzahl anzugeben. Das Makro „# of“ wird verwendet, um die Gesamtzahl der Seiten darzustellen.

#### F: Was passiert, wenn ich mehreren Seiten denselben Seitenzahlenstempel hinzufüge?

A: Wenn Sie die gleiche PageNumberStamp-Instanz zu mehreren Seiten hinzufügen, werden für jede Seite die richtigen Seitenzahlen angezeigt. Der Stempel passt die Seitenzahl und die Gesamtseitenzahl automatisch an.

#### F: Kann ich den Kopf- und Fußzeilenabschnitten eines PDF-Dokuments Seitenzahlenstempel hinzufügen?

A: Während PageNumberStamps normalerweise direkt zum Inhalt der Seite hinzugefügt werden, können Sie FloatingBox oder andere Techniken verwenden, um sie in Kopf- oder Fußzeilenabschnitten zu positionieren.

#### F: Wie lege ich die Position des Seitenzahlenstempels auf der Seite fest?

 A: Die`BottomMargin` Und`HorizontalAlignment` Mit den Eigenschaften von PageNumberStamp können Sie die Position des Stempels innerhalb der Seite steuern.

#### F: Was passiert, wenn ich die Seitennummerierung mit einer anderen Zahl als 1 beginnen möchte?

 A: Sie können die`StartingNumber`-Eigenschaft des PageNumberStamp, um die Startseitenzahl anzugeben.