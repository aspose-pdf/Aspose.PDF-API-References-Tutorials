---
title: Seite redigieren
linktitle: Seite redigieren
second_title: Aspose.PDF für .NET API-Referenz
description: In diesem Artikel wird erläutert, wie Sie eine PDF-Seite mit Aspose.PDF für .NET redigieren, einschließlich Schritt-für-Schritt-Anleitungen und Beispielquellcode.
type: docs
weight: 120
url: /de/net/annotations/redactpage/
---
Wenn Sie sensible Informationen aus einem PDF-Dokument mit Aspose.PDF für .NET entfernen möchten, haben Sie Glück! Hier ist eine Schritt-für-Schritt-Anleitung für den Einstieg:

## Legen Sie im Code den Pfad zu dem Verzeichnis fest, in dem sich Ihr PDF-Dokument befindet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Öffnen Sie das PDF-Dokument:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Erstellen Sie eine RedactionAnnotation-Instanz für einen bestimmten Seitenbereich:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Legen Sie die Füllfarbe, Rahmenfarbe und Textfarbe der Schwärzungsanmerkung fest:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Legen Sie den Text fest, der auf der Schwärzungsanmerkung gedruckt werden soll, und seine Ausrichtung:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Wiederholen Sie den Overlay-Text über der Schwärzungsanmerkung:

```csharp
annot.Repeat = true;
```

## Fügen Sie die Anmerkung zur Anmerkungssammlung der ersten Seite hinzu:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Reduzieren Sie die Anmerkung und redigieren Sie den Seiteninhalt, d. h. entfernen Sie Text und Bilder unter der redigierten Anmerkung:

```csharp
annot.Redact();
```

## Legen Sie den Pfad und Namen der Ausgabe-PDF-Datei fest:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Speichern Sie das PDF-Dokument mit der redigierten Seite:

```csharp
doc.Save(dataDir);
```

Das ist es! Sie haben eine Seite Ihres PDF-Dokuments erfolgreich mit Aspose.PDF für .NET redigiert.

### Beispielquellcode für Redact Page mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");

// Erstellen Sie eine RedactionAnnotation-Instanz für einen bestimmten Seitenbereich
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Text, der auf der Schwärzungsanmerkung gedruckt werden soll
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repat Overlay-Text über redigierte Anmerkung
annot.Repeat = true;
// Anmerkung zur Anmerkungssammlung der ersten Seite hinzufügen
doc.Pages[1].Annotations.Add(annot);
// Reduziert Anmerkungen und redigiert Seiteninhalte (d. h. entfernt Text und Bilder).
// Unter redigierter Anmerkung)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```