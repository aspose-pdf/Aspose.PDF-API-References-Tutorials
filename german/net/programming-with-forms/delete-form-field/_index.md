---
title: Formularfeld löschen
linktitle: Formularfeld löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Entfernen Sie unerwünschte Formularfelder ganz einfach aus Ihren PDF-Dokumenten mit Aspose.PDF für .NET.
type: docs
weight: 50
url: /de/net/programming-with-forms/delete-form-field/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie ein Formularfeld mit Aspose.PDF für .NET löschen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Schritt 3: Löschen Sie ein bestimmtes Feld

Löschen Sie ein bestimmtes Formularfeld anhand seines Namens:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Schritt 4: Speichern Sie das bearbeitete Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Formularfeld löschen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Löschen Sie ein bestimmtes Feld nach Namen
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Geändertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man ein Formularfeld mit Aspose.PDF für .NET löscht. Wenn Sie diese Schritte befolgen, können Sie mithilfe von Aspose.PDF problemlos unerwünschte Formularfelder aus Ihren PDF-Dokumenten entfernen.