---
title: Verschiedene Header hinzufügen
linktitle: Verschiedene Header hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach unterschiedliche Kopfzeilen zu jeder Seite Ihrer PDF-Dokumente hinzufügen.
type: docs
weight: 30
url: /de/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET verschiedene Kopfzeilen zu einem PDF-Dokument hinzufügen. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um benutzerdefinierte Kopfzeilen zu jeder Seite des PDF-Dokuments hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Quelldokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Header-Puffer erstellen

Nachdem Sie das PDF-Dokument hochgeladen haben, können Sie die hinzuzufügenden Kopfstempel erstellen. Hier ist wie:

```csharp
// Erstellen Sie drei Header-Puffer
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Der obige Code erstellt drei neue Header-Puffer, die den angegebenen Text enthalten.

## Schritt 4: Header-Puffereigenschaften konfigurieren

Bevor Sie die Kopfzeilenstempel zum PDF-Dokument hinzufügen, können Sie für jeden Stempel verschiedene Eigenschaften konfigurieren, wie z. B. Ausrichtung, Größe, Farbe usw. So geht's:

```csharp
// Konfigurieren Sie den ersten Header-Puffer
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Konfiguration des zweiten Header-Puffers
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Konfigurieren Sie den dritten Header-Puffer
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Sie können diese Eigenschaften für jeden Header-Puffer nach Bedarf anpassen.

## Schritt 5: Kopfstempel zum PDF hinzufügen

Da die Kopfzeilenstempel nun fertig sind, können Sie sie auf jeder einzelnen Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
// Fügen Sie Header-Puffer zu bestimmten Seiten hinzu
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Der obige Code fügt jeden Kopfzeilenstempel zur entsprechenden Seite des PDF-Dokuments hinzu.

## Schritt 6: Speichern Sie das Ausgabedokument

Sobald Sie die Kopfstempel hinzugefügt haben, können Sie das bearbeitete PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode zum Hinzufügen verschiedener Header mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open-Source-Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Erstellen Sie drei Stempel
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Stempelausrichtung festlegen (Stempel oben auf der Seite platzieren, horizontal zentriert)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Geben Sie den Schriftstil als Fett an
stamp1.TextState.FontStyle = FontStyles.Bold;

// Legen Sie die Informationen zur Hintergrundfarbe des Textes auf Rot fest
stamp1.TextState.ForegroundColor = Color.Red;

// Geben Sie die Schriftgröße als 14 an
stamp1.TextState.FontSize = 14;

// Jetzt müssen wir die vertikale Ausrichtung des 2. Stempelobjekts auf „Oben“ festlegen
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Legen Sie die horizontalen Ausrichtungsinformationen für den Stempel auf „Mittig ausgerichtet“ fest
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Legen Sie den Zoomfaktor für das Stempelobjekt fest
stamp2.Zoom = 10;

// Legen Sie die Formatierung des 3. Stempelobjekts fest
// Geben Sie die vertikalen Ausrichtungsinformationen für das Stempelobjekt als OBEN an
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Legen Sie die Informationen zur horizontalen Ausrichtung für das Stempelobjekt auf „Mittig ausgerichtet“ fest
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Legen Sie den Drehwinkel für das Stempelobjekt fest
stamp3.RotateAngle = 35;

// Stellen Sie Rosa als Hintergrundfarbe für den Stempel ein
stamp3.TextState.BackgroundColor = Color.Pink;

// Ändern Sie die Schriftartinformationen für den Stempel in „Verdana“.
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Der erste Stempel wird auf der ersten Seite hinzugefügt.
doc.Pages[1].AddStamp(stamp1);

// Der zweite Stempel ist auf der zweiten Seite hinzugefügt;
doc.Pages[2].AddStamp(stamp2);

// Der dritte Stempel wird auf der dritten Seite hinzugefügt.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Speichern Sie das aktualisierte Dokument
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET jeder Seite eines PDF-Dokuments unterschiedliche Kopfzeilen hinzufügen. Sie können dieses Wissen nun auf Ihre eigenen Projekte anwenden, um Kopfzeilen für Ihre PDF-Dokumente anzupassen.
