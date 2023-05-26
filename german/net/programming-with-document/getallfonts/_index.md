---
title: Holen Sie sich alle Schriftarten
linktitle: Holen Sie sich alle Schriftarten
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung und dem Beispielcode, wie Sie Aspose.PDF für .NET verwenden, um alle in einem PDF-Dokument verwendeten Schriftarten programmgesteuert abzurufen.
type: docs
weight: 160
url: /de/net/programming-with-document/getallfonts/
---

Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PDF-Dokumenten zu arbeiten. Eine der Funktionen, die es bietet, ist die Möglichkeit, alle in einem PDF-Dokument verwendeten Schriftarten abzurufen. Dies kann nützlich sein, wenn Sie die Schriftarten in einem PDF-Dokument programmgesteuert analysieren oder bearbeiten müssen.

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


