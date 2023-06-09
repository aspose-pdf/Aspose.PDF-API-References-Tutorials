---
title: Text in der Fußzeile
linktitle: Text in der Fußzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text in die Fußzeile eines PDF-Dokuments einfügen.
type: docs
weight: 180
url: /de/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET Text in die Fußzeile eines PDF-Dokuments einfügt. Folgen Sie den unteren Schritten:

## Schritt 1: Projektvorbereitung

Stellen Sie sicher, dass Sie Aspose.PDF für .NET installiert und ein C#-Projekt erstellt haben.

## Schritt 2: Namespaces importieren

Fügen Sie Ihrer C#-Quelldatei die folgenden Namespaces hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Öffnen des Dokuments

Öffnen Sie das vorhandene PDF-Dokument über den angegebenen Pfad:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 4: Fußzeilentext erstellen

Erstellen Sie einen neuen Textstempel mit dem Text, den Sie in der Fußzeile hinzufügen möchten:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Sie können den Text anpassen, indem Sie seine Eigenschaften wie den unteren Rand, die horizontale Ausrichtung und die vertikale Ausrichtung ändern.

## Schritt 5: Fußzeilentext zu allen Seiten hinzufügen

Gehen Sie alle Seiten des PDF-Dokuments durch und fügen Sie den Textstempel in der Fußzeile ein:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Schritt 6: Speichern des PDF-Dokuments

Sobald der Fußzeilentext auf allen Seiten hinzugefügt wurde, speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Ersetzen Sie unbedingt „VERZEICHNIS IHRER DOKUMENTE“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

### Beispielquellcode für Textin Footer mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Fußzeile erstellen
TextStamp textStamp = new TextStamp("Footer Text");

// Legen Sie die Eigenschaften des Stempels fest
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Fußzeile auf allen Seiten hinzufügen
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Text in die Fußzeile eines PDF-Dokuments einfügen. Sie können jetzt Ihre Fußzeilen anpassen, indem Sie Ihren PDF-Dokumenten zusätzlichen Text hinzufügen.
