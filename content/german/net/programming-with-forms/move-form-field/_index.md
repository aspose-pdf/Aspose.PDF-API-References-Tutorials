---
title: Formularfeld verschieben
linktitle: Formularfeld verschieben
second_title: Aspose.PDF für .NET API-Referenz
description: Verschieben Sie Formularfelder in Ihren PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
type: docs
weight: 200
url: /de/net/programming-with-forms/move-form-field/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument verschieben. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Vorgang zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument einlegen

Laden Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Schritt 3: Formularfeld abrufen

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

### Beispielquellcode für „Formularfeld verschieben“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldposition ändern
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Geändertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Formularfeld in einem PDF-Dokument verschiebt. Indem Sie diese Schritte befolgen, können Sie problemlos zu einem bestimmten Feld navigieren und dessen Position nach Bedarf ändern.


### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET mehrere Formularfelder innerhalb eines einzelnen PDF-Dokuments verschieben?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Formularfelder innerhalb eines einzelnen PDF-Dokuments verschieben. Wiederholen Sie den Vorgang einfach für jedes Formularfeld, das Sie verschieben möchten.

#### F: Hat das Verschieben eines Formularfelds Auswirkungen auf die zugehörigen Daten oder Funktionen?

A: Nein, das Verschieben eines Formularfelds hat keine Auswirkungen auf die zugehörigen Daten oder Funktionen. Das Formularfeld behält alle seine Eigenschaften und Werte, nachdem es an einen neuen Ort verschoben wurde.

#### F: Wie kann ich die genauen Koordinaten für den neuen Standort des Formularfeldes ermitteln?

 A: Sie können den neuen Standort angeben mit dem`Aspose.Pdf.Rectangle` Klasse, in der Sie die X- und Y-Koordinaten der oberen linken Ecke und die X- und Y-Koordinaten der unteren rechten Ecke des rechteckigen Bereichs definieren.

#### F: Ist Aspose.PDF für .NET sowohl mit Windows- als auch mit Linux-Umgebungen kompatibel?

A: Ja, Aspose.PDF für .NET ist sowohl mit Windows- als auch mit Linux-Umgebungen kompatibel und bietet Entwicklern die Flexibilität, in ihren bevorzugten Betriebssystemen zu arbeiten.