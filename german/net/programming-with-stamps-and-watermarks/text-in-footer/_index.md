---
title: Text in der Fußzeile der PDF-Datei
linktitle: Text in der Fußzeile der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text in die Fußzeile einer PDF-Datei einfügen.
type: docs
weight: 180
url: /de/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET Text in die Fußzeile einer PDF-Datei einfügt. Folgen Sie den unteren Schritten:

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

### FAQs zum Text in der Fußzeile einer PDF-Datei

#### F: Welchen Zweck hat das Hinzufügen von Text in der Fußzeile eines PDF-Dokuments?

A: Durch das Hinzufügen von Text in der Fußzeile eines PDF-Dokuments können Sie wichtige Informationen wie Urheberrechtshinweise, Seitenzahlen, Dokumentversion oder jeden anderen Text einfügen, der am Ende jeder Seite einheitlich angezeigt werden soll.

#### F: Wie erreicht der bereitgestellte C#-Quellcode das Hinzufügen von Text in der Fußzeile eines PDF-Dokuments?

A: Der Code demonstriert den Vorgang des Öffnens eines vorhandenen PDF-Dokuments, des Erstellens eines Textstempels mit dem gewünschten Fußzeilentext, des Anpassens der Texteigenschaften, des Hinzufügens des Textstempels zu allen Seiten und schließlich des Speicherns des aktualisierten PDF-Dokuments mit dem hinzugefügten Fußzeilentext.

#### F: Kann ich das Erscheinungsbild des Fußzeilentexts ändern, z. B. Schriftart, Größe, Farbe und Ausrichtung?

 A: Ja, Sie können das Erscheinungsbild des Fußzeilentexts anpassen, indem Sie die Eigenschaften des ändern`TextStamp` Objekt. Das Codebeispiel umfasst das Festlegen von Eigenschaften wie unterem Rand, horizontaler Ausrichtung und vertikaler Ausrichtung. Sie können auch Schriftart, Größe, Farbe und andere textbezogene Eigenschaften anpassen.

#### F: Ist es möglich, der Fußzeile jeder Seite einen anderen Text hinzuzufügen?

 A: Ja, Sie können der Fußzeile jeder Seite unterschiedlichen Text hinzufügen, indem Sie einen separaten Text erstellen`TextStamp` Objekte mit unterschiedlichem Textinhalt oder unterschiedlichen Eigenschaften erstellen und sie dann nach Bedarf zu bestimmten Seiten hinzufügen.

#### F: Wie stelle ich sicher, dass der Fußzeilentext auf jeder Seite des PDF-Dokuments konsistent angezeigt wird?

A: Indem Sie eine Schleife verwenden, die alle Seiten des PDF-Dokuments durchläuft und jeder Seite den gleichen Textstempel hinzufügt, stellen Sie sicher, dass der Fußzeilentext auf jeder Seite konsistent angezeigt wird.

#### F: Kann ich mehrere Textzeilen hinzufügen oder den Fußzeilentext mit Zeilenumbrüchen formatieren?

 A: Ja, Sie können der Fußzeile mehrere Textzeilen hinzufügen, indem Sie Zeilenumbrüche in die Textzeichenfolge einfügen. Sie können beispielsweise die Escape-Sequenz verwenden`\n` um einen Zeilenumbruch im Text anzuzeigen.

#### F: Was passiert, wenn ich der Kopf- und Fußzeile desselben PDF-Dokuments unterschiedliche Inhalte hinzufügen möchte?

A: Um den Kopf- und Fußzeilenabschnitten unterschiedliche Inhalte hinzuzufügen, führen Sie für beide Abschnitte ähnliche Schritte aus. Der Code demonstriert das Hinzufügen von Text zur Fußzeile. Sie können einen ähnlichen Ansatz verwenden, um Text zur Kopfzeile hinzuzufügen.

#### F: Ist es mit diesem Ansatz möglich, Bilder oder andere Elemente neben dem Fußzeilentext hinzuzufügen?

A: Während der bereitgestellte Code speziell das Hinzufügen von Text zur Fußzeile demonstriert, können Sie den Ansatz mithilfe der Aspose.PDF-Bibliothek erweitern, um andere Elemente wie Bilder, Linien, Formen oder andere Inhalte zum Fußzeilenabschnitt hinzuzufügen.