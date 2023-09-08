---
title: Formularfeld im PDF-Dokument ändern
linktitle: Formularfeld im PDF-Dokument ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Bearbeiten Sie Formularfelder in PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET.
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


### FAQs

#### F: Kann ich mit Aspose.PDF für .NET mehrere Formularfelder in einem einzelnen PDF-Dokument bearbeiten?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Formularfelder in einem einzigen PDF-Dokument bearbeiten. Wiederholen Sie den Vorgang einfach für jedes Formularfeld, das Sie ändern möchten.

#### F: Ist Aspose.PDF für .NET mit allen Versionen von .NET Framework kompatibel?

A: Ja, Aspose.PDF für .NET ist mit allen Versionen von .NET Framework kompatibel, einschließlich .NET Core und .NET Standard.

#### F: Kann ich mit Aspose.PDF für .NET andere Arten von Formularfeldern ändern, z. B. Kontrollkästchen oder Optionsfelder?

A: Ja, Aspose.PDF für .NET unterstützt das Ändern verschiedener Arten von Formularfeldern, einschließlich Kontrollkästchen, Optionsfeldern und mehr.

#### F: Wie kann ich mit Aspose.PDF für .NET neue Formularfelder zu einem PDF-Dokument hinzufügen?

 A: Um einem PDF-Dokument neue Formularfelder hinzuzufügen, können Sie das verwenden`Form` Eigentum der`Document` Klasse, um auf die zuzugreifen`Field` Sammlung und fügen Sie dann programmgesteuert neue Formularfelder hinzu.

#### F: Unterstützt Aspose.PDF für .NET neben C# auch andere Programmiersprachen?

A: Ja, Aspose.PDF für .NET unterstützt neben C# auch verschiedene Programmiersprachen wie VB.NET und ASP.NET.