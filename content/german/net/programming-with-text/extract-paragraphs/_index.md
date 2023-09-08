---
title: Extrahieren Sie Absätze in einer PDF-Datei
linktitle: Extrahieren Sie Absätze in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Absätze in eine PDF-Datei extrahieren.
type: docs
weight: 160
url: /de/net/programming-with-text/extract-paragraphs/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Absätzen in eine PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie Absätze extrahieren möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit`Document`Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 5: Absätze extrahieren
 Instanziieren Sie die`ParagraphAbsorber` Klasse und verwenden Sie es`Visit` Methode zum Extrahieren von Absätzen aus dem Dokument.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Schritt 6: Durchgehen Sie die Absätze
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
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Öffnen Sie eine vorhandene PDF-Datei
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
Sie haben mit Aspose.PDF für .NET erfolgreich Absätze aus einem PDF-Dokument extrahiert. Die extrahierten Absätze wurden im Konsolenfenster angezeigt.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess des Extrahierens von Absätzen aus einer PDF-Datei mit Aspose.PDF für .NET führen. Der zugehörige C#-Quellcode bietet praktische Schritte zum Erreichen dieser Aufgabe.

#### F: Welche Namespaces sollte ich importieren?

A: Fügen Sie in der Codedatei, in die Sie Absätze extrahieren möchten, die folgenden using-Anweisungen am Anfang der Datei ein:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` im Code einfügen und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und stellt den Pfad zur Eingabe-PDF-Datei bereit.

#### F: Wie extrahiere ich Absätze aus dem Dokument?

 A: Schritt 5 umfasst das Erstellen einer Instanz von`ParagraphAbsorber` Klasse und deren Verwendung`Visit` Methode zum Extrahieren von Absätzen aus dem PDF-Dokument.

#### F: Wie kann ich die extrahierten Absätze durchlaufen?

A: Schritt 6 führt Sie durch das Durchlaufen der extrahierten Absätze. Verschachtelte Schleifen werden verwendet, um Abschnitte und Zeilen innerhalb jedes Absatzes zu durchlaufen und letztendlich auf den Textinhalt zuzugreifen und ihn anzuzeigen.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Absätze aus einem PDF-Dokument extrahieren. Die extrahierten Absätze wurden im Konsolenfenster angezeigt und bieten Ihnen wertvolle Einblicke in die Inhaltsstruktur des Dokuments.