---
title: Seitenzahlenstempel
linktitle: Seitenzahlenstempel
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Seitenzahlenstempel zu einem PDF-Dokument hinzufügen.
type: docs
weight: 160
url: /de/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen von Seitenzahlstempeln zu einem PDF-Dokument mit Aspose.PDF für .NET. Wir verwenden den bereitgestellten C#-Quellcode, um ein vorhandenes PDF-Dokument zu öffnen, einen Seitenzahlstempel zu erstellen, seine Eigenschaften festzulegen und ihn einer bestimmten Seite im PDF-Dokument hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des vorhandenen PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen und Konfigurieren des Seitennummerierungsstempels

Nachdem das PDF-Dokument nun geladen ist, können wir einen Seitennummerierungspuffer erstellen und ihn entsprechend unseren Anforderungen konfigurieren. Hier ist wie:

```csharp
// Erstellen Sie einen Seitenzahlpuffer
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Legen Sie fest, ob der Puffer im Hintergrund läuft oder nicht
pageNumberStamp.Background = false;

// Format des Seitennummerierungspuffers
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Unterer Rand des Seitennummerierungspuffers
pageNumberStamp.BottomMargin = 10;

// Horizontale Ausrichtung des Seitennummerierungspuffers
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Startnummer der Seitennummerierung
pageNumberStamp.StartingNumber = 1;

// Legen Sie die Texteigenschaften für den Seitenzahlpuffer fest
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Der obige Code erstellt einen Seitenzahlenstempel mit Eigenschaften wie Seitenzahlenformat, unterer Rand, horizontale Ausrichtung, Startzahl und Texteigenschaften.

## Schritt 4: Hinzufügen des Seitenzahlstempels zu einer bestimmten Seite

Sobald der Seitenzahlstempel konfiguriert ist, können wir ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
// Fügen Sie den Seitenzahlpuffer einer bestimmten Seite hinzu
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Der obige Code fügt den Seitenzahlstempel zur ersten Seite des PDF-Dokuments hinzu. Sie können die Seitenzahl nach Bedarf ändern.

## Schritt 5: Speichern des geänderten PDF-Dokuments

Sobald der Seitenzahlstempel zum PDF-Dokument hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das bearbeitete PDF-Dokument speichern möchten.

### Beispielquellcode für Seitenzahlstempel mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Erstellen Sie einen Seitenzahlstempel
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

// Stempel zu einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Seitenzahlenstempel zu einem PDF-Dokument hinzufügen. Sie können Ihre PDF-Dokumente jetzt personalisieren, indem Sie klare und informative Seitenzahlen hinzufügen.
