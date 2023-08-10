---
title: Mehrspaltige Absätze
linktitle: Mehrspaltige Absätze
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mit mehrspaltigen Absätzen in einem PDF-Dokument arbeiten.
type: docs
weight: 250
url: /de/net/programming-with-text/multicolumn-paragraphs/
---

In diesem Tutorial erklären wir, wie Sie mit mehrspaltigen Absätzen in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET arbeiten. Wir werden den Prozess der Bearbeitung und des Zugriffs auf mehrspaltige Absätze mithilfe des bereitgestellten C#-Quellcodes Schritt für Schritt durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zuerst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich Ihre Eingabe-PDF-Datei befindet. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir`Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das Eingabe-PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Schritt 3: Auf mehrspaltige Absätze zugreifen

 Wir benutzen das`ParagraphAbsorber`Klasse, um die Absätze im PDF-Dokument zu verstehen und zu lesen. Anschließend rufen wir die Seitenmarkierungen ab und greifen auf die mehrspaltigen Absätze zu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Schritt 4: Arbeiten Sie mit mehrspaltigen Absätzen

Wir greifen innerhalb der mehrspaltigen Struktur auf bestimmte Abschnitte und Absätze zu und drucken deren Text aus.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Zugriff auf den letzten Absatz in einem Abschnitt
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Zugriff auf den ersten Absatz in einem Abschnitt
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Mehrspaltige Absätze aktivieren
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Zugriff auf den letzten Absatz in einem Abschnitt, nachdem mehrspaltige Absätze aktiviert wurden
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Zugriff auf den ersten Absatz in einem Abschnitt nach Aktivierung mehrspaltiger Absätze
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Beispielquellcode für mehrspaltige Absätze mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET mit mehrspaltigen Absätzen in einem PDF-Dokument arbeiten. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie auf mehrspaltige Absätze in einem PDF-Dokument zugreifen und diese bearbeiten.