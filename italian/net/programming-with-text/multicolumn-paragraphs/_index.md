---
title: Paragrafi multicolonna
linktitle: Paragrafi multicolonna
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come lavorare con paragrafi multicolonna in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 250
url: /it/net/programming-with-text/multicolumn-paragraphs/
---

In questo tutorial, spiegheremo come lavorare con paragrafi multicolonna in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Esamineremo il processo dettagliato di manipolazione e accesso ai paragrafi multicolonna utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre di quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, è necessario impostare il percorso della directory in cui si trova il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir`variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Successivamente, carichiamo il documento PDF di input utilizzando il file`Document` class dalla libreria Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Passaggio 3: accedere ai paragrafi multicolonna

 Noi usiamo il`ParagraphAbsorber`classe per assorbire e visitare i paragrafi nel documento PDF. Quindi recuperiamo i markup della pagina e accediamo ai paragrafi multicolonna.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Passaggio 4: lavorare con paragrafi multicolonna

Accediamo a sezioni e paragrafi specifici all'interno della struttura a più colonne e stampiamo il loro testo.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Accesso all'ultimo paragrafo di una sezione
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accesso al primo paragrafo di una sezione
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Abilitare i paragrafi multicolonna
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Accesso all'ultimo paragrafo di una sezione dopo aver abilitato i paragrafi a più colonne
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accesso al primo paragrafo in una sezione dopo aver abilitato i paragrafi multicolonna
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Esempio di codice sorgente per paragrafi multicolonna utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
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

## Conclusione

In questo tutorial, hai imparato a lavorare con paragrafi a più colonne in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida dettagliata ed eseguendo il codice C# fornito, è possibile accedere e manipolare paragrafi a più colonne in un documento PDF.