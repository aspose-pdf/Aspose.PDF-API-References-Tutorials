---
title: Formularfeld ausfüllen
linktitle: Formularfeld ausfüllen
second_title: Aspose.PDF für .NET API-Referenz
description: Füllen Sie mit Aspose.PDF für .NET ganz einfach Formularfelder in Ihren PDF-Dokumenten aus.
type: docs
weight: 80
url: /de/net/programming-with-forms/fill-form-field/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie ein Formularfeld mit Aspose.PDF für .NET füllen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Schritt 3: Feld abrufen

Rufen Sie das gewünschte Formularfeld ab (in diesem Beispiel verwenden wir das Feld „textbox1“):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Ändern Sie den Feldwert

Ändern Sie den Feldwert mit dem gewünschten Wert:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Formularfeld ausfüllen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldwert ändern
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man ein Formularfeld mit Aspose.PDF für .NET ausfüllt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach Formularfeldwerte in Ihren PDF-Dokumenten ändern.