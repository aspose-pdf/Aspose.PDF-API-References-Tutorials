---
title: Formularfeld verschieben
linktitle: Formularfeld verschieben
second_title: Aspose.PDF für .NET API-Referenz
description: Verschieben Sie Formularfelder in Ihren PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 200
url: /de/net/programming-with-forms/move-form-field/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument verschieben. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

Laden Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Schritt 3: Holen Sie sich das Formularfeld

Holen Sie sich das Formularfeld, das Sie verschieben möchten:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Feldstandort ändern

Ändern Sie die Position des Formularfelds, indem Sie einen neuen rechteckigen Bereich definieren:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Schritt 5: Speichern Sie das bearbeitete Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Formularfeld verschieben“ mit Aspose.Words für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldstandort ändern
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Geändertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument verschiebt. Wenn Sie diese Schritte befolgen, können Sie ganz einfach zu einem bestimmten Feld navigieren und dessen Position nach Bedarf ändern.