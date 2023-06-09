---
title: Formularfeld ändern
linktitle: Formularfeld ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Bearbeiten Sie Formularfelder in Ihren PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 190
url: /de/net/programming-with-forms/modify-form-field/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument bearbeiten. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

Laden Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Schritt 3: Holen Sie sich das Formularfeld

Holen Sie sich das Formularfeld, das Sie bearbeiten möchten:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Ändern Sie den Feldwert

Ändern Sie den Formularfeldwert:

```csharp
textBoxField.Value = "New Value";
```

## Schritt 5: Feldeigenschaften bearbeiten

Ändern Sie nach Bedarf weitere Formularfeldeigenschaften. Sie können es beispielsweise schreibgeschützt machen:

```csharp
textBoxField.ReadOnly = true;
```

## Schritt 6: Speichern Sie das bearbeitete Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Formularfeld ändern“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldwert ändern
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument bearbeitet. Wenn Sie diese Schritte befolgen, können Sie ganz einfach zu einem bestimmten Feld navigieren, seinen Wert ändern und seine Eigenschaften nach Bedarf anpassen.