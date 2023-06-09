---
title: Formularfeld-Schriftart 14
linktitle: Formularfeld-Schriftart 14
second_title: Aspose.PDF für .NET API-Referenz
description: Konfigurieren Sie ganz einfach die Schriftart von Formularfeldern in Ihren PDF-Dokumenten mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/programming-with-forms/form-field-font-14/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Schriftart eines Formularfelds mit Aspose.PDF für .NET konfigurieren. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Schritt 3: Holen Sie sich ein bestimmtes Formularfeld

Rufen Sie das gewünschte Formularfeld ab (in diesem Beispiel verwenden wir das Feld „textbox1“):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Schritt 4: Erstellen Sie ein Schriftartobjekt

Erstellen Sie ein Schriftartobjekt für die neue Schriftart, die Sie verwenden möchten (z. B. „ComicSansMS“):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Schritt 5: Konfigurieren Sie Schriftartinformationen für das Formularfeld

Konfigurieren Sie die Schriftartinformationen für das Formularfeld mithilfe der zuvor erstellten Schriftart:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Schritt 6: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Beispielquellcode für Form Field Font 14 mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
//Holen Sie sich ein bestimmtes Formularfeld aus dem Dokument
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Schriftartobjekt erstellen
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Legen Sie die Schriftartinformationen für das Formularfeld fest
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man die Schriftart eines Formularfelds mit Aspose.PDF für .NET konfiguriert. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Schriftart und Schriftgröße für Formularfelder in Ihren PDF-Dokumenten festlegen.