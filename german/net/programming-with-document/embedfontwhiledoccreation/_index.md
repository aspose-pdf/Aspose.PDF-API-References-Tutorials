---
title: Betten Sie Schriftarten bei der Dokumenterstellung ein
linktitle: Betten Sie Schriftarten bei der Dokumenterstellung ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Erstellen eines PDF-Dokuments mit Aspose.PDF für .NET eine Schriftart einbetten. Sorgen Sie für eine korrekte Anzeige auf verschiedenen Geräten.
type: docs
weight: 140
url: /de/net/programming-with-document/embedfontwhiledoccreation/
---

In diesem Tutorial besprechen wir, wie Sie beim Erstellen eines PDF-Dokuments mit Aspose.PDF für .NET eine Schriftart einbetten. Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und bearbeiten können. Diese Bibliothek bietet zahlreiche Funktionen für die Arbeit mit PDF-Dokumenten, darunter das Hinzufügen von Text, Bildern, Tabellen und vielem mehr. Das Einbetten von Schriftarten beim Erstellen eines PDF-Dokuments ist eine häufige Anforderung für Entwickler, die sicherstellen möchten, dass das PDF-Dokument auf verschiedenen Geräten korrekt angezeigt wird, unabhängig davon, ob die erforderlichen Schriftarten auf diesen Geräten installiert sind oder nicht.

## Schritt 1: Erstellen Sie eine neue C#-Konsolenanwendung
Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Visual Studio. Sie können es beliebig benennen. Sobald das Projekt erstellt ist, müssen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzufügen.

## Schritt 2: Importieren Sie den Aspose.PDF-Namespace
Fügen Sie oben in Ihrer C#-Datei die folgende Codezeile hinzu, um den Aspose.PDF-Namespace zu importieren:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Instanziieren Sie ein PDF-Objekt
Instanziieren Sie ein PDF-Objekt, indem Sie seinen leeren Konstruktor aufrufen:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Schritt 4: Erstellen Sie einen Abschnitt im PDF-Objekt
Erstellen Sie einen Abschnitt im PDF-Objekt:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 5: Fügen Sie dem Abschnitt Text hinzu
Fügen Sie dem Abschnitt Text hinzu:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Schritt 6: Legen Sie die Schriftart fest und betten Sie sie ein
Legen Sie die Schriftart fest und betten Sie sie ein:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Schritt 7: Speichern Sie das PDF-Dokument
Nachdem Sie die Schriftart beim Erstellen des PDF-Dokuments eingebettet haben, müssen Sie das Dokument speichern:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
```

### Beispielquellcode zum Einbetten von Schriftarten bei der Dokumenterstellung mit Aspose.PDF für .NET

```csharp

            
            // Der Pfad zum Dokumentenverzeichnis.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instanziieren Sie ein PDF-Objekt, indem Sie seinen leeren Konstruktor aufrufen
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Erstellen Sie einen Abschnitt im PDF-Objekt
            Aspose.Pdf.Page page = doc.Pages.Add();

            Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

            Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
            Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
            ts.Font = FontRepository.FindFont("Arial");
            ts.Font.IsEmbedded = true;
            segment.TextState = ts;
            fragment.Segments.Add(segment);
            page.Paragraphs.Add(fragment);

            dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
            // PDF-Dokument speichern
            doc.Save(dataDir);
            
            
        
```

## Abschluss
In diesem Tutorial haben wir besprochen, wie man beim Erstellen eines PDF-Dokuments mit Aspose.PDF für .NET eine Schriftart einbettet. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API für die Arbeit mit PDF-Dokumenten, einschließlich des Hinzufügens und Einbettens von Schriftarten. Das Einbetten von Schriftarten beim Erstellen eines PDF-Dokuments ist ein wichtiger Schritt, um sicherzustellen, dass das Dokument auf verschiedenen Geräten korrekt angezeigt wird, unabhängig davon, ob die erforderlichen Schriftarten auf diesen Geräten installiert sind oder nicht.

