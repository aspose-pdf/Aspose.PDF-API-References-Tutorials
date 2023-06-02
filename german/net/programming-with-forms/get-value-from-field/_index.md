---
title: Wert aus Feld abrufen
linktitle: Wert aus Feld abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Ermitteln Sie ganz einfach den Wert eines Formularfelds in Ihren PDF-Dokumenten mit Aspose.PDF für .NET.
type: docs
weight: 140
url: /de/net/programming-with-forms/get-value-from-field/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET den Wert eines Formularfelds ermitteln. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert und den Pfad zu Ihrem Dokumentenverzeichnis festgelegt haben:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Schritt 3: Feld abrufen

Rufen Sie das gewünschte Formularfeld ab (in diesem Beispiel verwenden wir das Feld „textbox1“):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Feldwert abrufen

 Rufen Sie den Feldwert mithilfe von ab`Value` Eigentum:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Beispielquellcode für „Get Value From Field“ mit Aspose.Words für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldwert abrufen
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET den Wert eines Formularfelds ermittelt. Wenn Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach den Wert eines bestimmten Formularfelds in Ihren PDF-Dokumenten extrahieren.