---
title: Holen Sie sich alle Schriftarten in eine PDF-Datei
linktitle: Holen Sie sich alle Schriftarten in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung und dem Beispielcode, wie Sie Aspose.PDF für .NET verwenden, um alle in einer PDF-Datei verwendeten Schriftarten programmgesteuert abzurufen.
type: docs
weight: 160
url: /de/net/programming-with-document/getallfonts/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PDF-Dateien zu arbeiten. Eine der Funktionen, die es bietet, ist die Möglichkeit, alle in einer PDF-Datei verwendeten Schriftarten abzurufen. Dies kann nützlich sein, wenn Sie die Schriftarten in einer PDF-Datei programmgesteuert analysieren oder bearbeiten müssen.

In diesem Tutorial besprechen wir, wie Sie Aspose.PDF für .NET verwenden, um alle in einem PDF-Dokument verwendeten Schriftarten abzurufen. Wir stellen Ihnen dazu eine Schritt-für-Schritt-Anleitung sowie einen Beispielquellcode zur Verfügung.

## Schritt 1: Erstellen Sie eine neue C#-Konsolenanwendung
Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Visual Studio. Sie können es beliebig benennen. Sobald das Projekt erstellt ist, müssen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzufügen.

## Schritt 2: Importieren Sie den Aspose.PDF-Namespace
Fügen Sie oben in Ihrer C#-Datei die folgende Codezeile hinzu, um den Aspose.PDF-Namespace zu importieren:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden Sie das PDF-Dokument
Laden Sie das PDF-Dokument, aus dem Sie die Schriftarten erhalten möchten:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Holen Sie sich alle Schriftarten
Holen Sie sich alle im PDF-Dokument verwendeten Schriftarten:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Schritt 5: Drucken Sie alle Schriftarten
Drucken Sie alle im PDF-Dokument verwendeten Schriftarten:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Beispielquellcode für „Get All Fonts“ mit Aspose.PDF für .NET
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Abschluss
In diesem Tutorial haben wir besprochen, wie Sie mit Aspose.PDF für .NET alle in einem PDF-Dokument verwendeten Schriftarten abrufen. Das Abrufen aller in einem PDF-Dokument verwendeten Schriftarten kann hilfreich sein, wenn Sie die Schriftarten in einem PDF-Dokument programmgesteuert analysieren oder bearbeiten müssen. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API für die Arbeit mit PDF-Dokumenten, einschließlich des Abrufens aller in einem PDF-Dokument verwendeten Schriftarten.

### FAQs

#### F: Warum sollte ich alle in einem PDF-Dokument verwendeten Schriftarten benötigen?

A: Das Abrufen aller in einem PDF-Dokument verwendeten Schriftarten kann nützlich sein, wenn Sie die Schriftarten für verschiedene Zwecke programmgesteuert analysieren oder bearbeiten müssen, beispielsweise zum Ersetzen oder Anpassen von Schriftarten.

#### F: Wie kann ich mit Aspose.PDF für .NET alle in einem PDF-Dokument verwendeten Schriftarten abrufen?

 A: Sie können alle in einem PDF-Dokument verwendeten Schriftarten mit Aspose.PDF für .NET abrufen, indem Sie die aufrufen`GetAllFonts` Methode der`FontUtilities` Klasse. Diese Methode gibt ein Array von zurück`Aspose.Pdf.Text.Font` Objekte, die die im PDF-Dokument verwendeten Schriftarten darstellen.

#### F: Kann ich Schriftarten nach bestimmten Kriterien filtern?

A: Ja, Sie können Schriftarten anhand bestimmter Kriterien filtern, indem Sie Aspose.PDF für .NET verwenden. Nachdem Sie alle Schriftarten erhalten haben, können Sie die Schriftarten programmgesteuert analysieren und nach Bedarf Filterlogik anwenden.

#### F: Ist Aspose.PDF für .NET mit verschiedenen Schriftformaten kompatibel?

A: Ja, Aspose.PDF für .NET ist mit verschiedenen Schriftformaten kompatibel, darunter TrueType-, OpenType- und Type-1-Schriftarten. Es kann mit verschiedenen Schriftformaten arbeiten und diese bei der Bearbeitung von PDF-Dokumenten verarbeiten.