---
title: Alle Schriftarten in der PDF-Datei abrufen
linktitle: Alle Schriftarten in der PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung und dem Beispielcode, wie Sie mit Aspose.PDF für .NET alle in einer PDF-Datei verwendeten Schriftarten programmgesteuert abrufen.
type: docs
weight: 160
url: /de/net/programming-with-document/getallfonts/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PDF-Dateien zu arbeiten. Eine der Funktionen, die sie bietet, ist die Möglichkeit, alle in einer PDF-Datei verwendeten Schriftarten abzurufen. Dies kann nützlich sein, wenn Sie die Schriftarten in einer PDF-Datei programmgesteuert analysieren oder bearbeiten müssen.

In diesem Tutorial besprechen wir, wie Sie mit Aspose.PDF für .NET alle in einem PDF-Dokument verwendeten Schriftarten abrufen können. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung sowie Beispielquellcode zur Verfügung.

## Schritt 1: Erstellen einer neuen C#-Konsolenanwendung
Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Visual Studio. Sie können sie beliebig benennen. Sobald das Projekt erstellt ist, müssen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzufügen.

## Schritt 2: Importieren Sie den Aspose.PDF-Namespace
Fügen Sie die folgende Codezeile oben in Ihrer C#-Datei hinzu, um den Aspose.PDF-Namespace zu importieren:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden Sie das PDF-Dokument
Laden Sie das PDF-Dokument, aus dem Sie die Schriftarten übernehmen möchten:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Alle Schriftarten abrufen
Holen Sie sich alle im PDF-Dokument verwendeten Schriftarten:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Schritt 5: Alle Schriftarten drucken
Drucken Sie alle im PDF-Dokument verwendeten Schriftarten:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Beispielquellcode für „Get All Fonts“ mit Aspose.PDF für .NET
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Abschluss
In diesem Tutorial haben wir besprochen, wie Sie mit Aspose.PDF für .NET alle in einem PDF-Dokument verwendeten Schriftarten abrufen können. Das Abrufen aller in einem PDF-Dokument verwendeten Schriftarten kann nützlich sein, wenn Sie die Schriftarten in einem PDF-Dokument programmgesteuert analysieren oder bearbeiten müssen. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API zum Arbeiten mit PDF-Dokumenten, einschließlich des Abrufens aller in einem PDF-Dokument verwendeten Schriftarten.

### Häufig gestellte Fragen

#### F: Warum muss ich alle in einem PDF-Dokument verwendeten Schriftarten abrufen?

A: Das Abrufen aller in einem PDF-Dokument verwendeten Schriftarten kann nützlich sein, wenn Sie die Schriftarten für verschiedene Zwecke, beispielsweise zum Ersetzen oder Anpassen von Schriftarten, programmgesteuert analysieren oder bearbeiten müssen.

#### F: Wie kann ich mit Aspose.PDF für .NET alle in einem PDF-Dokument verwendeten Schriftarten abrufen?

 A: Sie können alle in einem PDF-Dokument verwendeten Schriftarten mit Aspose.PDF für .NET abrufen, indem Sie den`GetAllFonts` Methode der`FontUtilities` Klasse. Diese Methode gibt ein Array von`Aspose.Pdf.Text.Font` Objekte, die die im PDF-Dokument verwendeten Schriftarten darstellen.

#### F: Kann ich Schriftarten nach bestimmten Kriterien filtern?

A: Ja, Sie können Schriftarten mit Aspose.PDF für .NET nach bestimmten Kriterien filtern. Nachdem Sie alle Schriftarten erhalten haben, können Sie diese programmgesteuert analysieren und bei Bedarf Filterlogik anwenden.

#### F: Ist Aspose.PDF für .NET mit verschiedenen Schriftformaten kompatibel?

A: Ja, Aspose.PDF für .NET ist mit verschiedenen Schriftformaten kompatibel, darunter TrueType-, OpenType- und Type 1-Schriftarten. Es kann mit verschiedenen Schriftformaten arbeiten und diese bei der Bearbeitung von PDF-Dokumenten verarbeiten.