---
title: Absätze in PDF-Datei extrahieren
linktitle: Absätze in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Absätze aus PDF-Dateien extrahieren.
type: docs
weight: 160
url: /de/net/programming-with-text/extract-paragraphs/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Absätzen in PDF-Dateien mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, aus der Sie Absätze extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 5: Absätze extrahieren
 Instanziieren Sie den`ParagraphAbsorber` Klasse und verwenden Sie deren`Visit` Methode zum Extrahieren von Absätzen aus dem Dokument.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Schritt 6: Absätze durchlaufen
Durchlaufen Sie die extrahierten Absätze, um auf den Textinhalt zuzugreifen. Verwenden Sie verschachtelte Schleifen, um Abschnitte und Zeilen innerhalb jedes Absatzes zu durchlaufen.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Beispielquellcode zum Extrahieren von Absätzen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öffnen einer vorhandenen PDF-Datei
Document doc = new Document(dataDir + "input.pdf");
// ParagraphAbsorber instanziieren
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Abschluss
Sie haben erfolgreich Absätze aus einem PDF-Dokument mit Aspose.PDF für .NET extrahiert. Die extrahierten Absätze wurden im Konsolenfenster angezeigt.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess des Extrahierens von Absätzen aus einer PDF-Datei mit Aspose.PDF für .NET führen. Der zugehörige C#-Quellcode bietet praktische Schritte zum Erledigen dieser Aufgabe.

#### F: Welche Namespaces soll ich importieren?

A: Fügen Sie in der Codedatei, aus der Sie Absätze extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven ein:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie die Linie`string dataDir = "YOUR DOCUMENT DIRECTORY";` im Code und ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Bereitstellung des Pfads zur Eingabe-PDF-Datei.

#### F: Wie extrahiere ich Absätze aus dem Dokument?

 A: Schritt 5 umfasst das Erstellen einer Instanz des`ParagraphAbsorber` Klasse und unter Verwendung ihrer`Visit` Methode zum Extrahieren von Absätzen aus dem PDF-Dokument.

#### F: Wie durchlaufe ich die extrahierten Absätze?

A: Schritt 6 führt Sie durch die Schleife der extrahierten Absätze. Verschachtelte Schleifen werden verwendet, um Abschnitte und Zeilen innerhalb jedes Absatzes zu durchlaufen und schließlich auf den Textinhalt zuzugreifen und ihn anzuzeigen.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Absätze aus einem PDF-Dokument extrahieren. Die extrahierten Absätze wurden im Konsolenfenster angezeigt und geben Ihnen wertvolle Einblicke in die Inhaltsstruktur des Dokuments.