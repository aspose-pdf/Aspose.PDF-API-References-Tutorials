---
title: Testo nell'intestazione
linktitle: Testo nell'intestazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere testo nell'intestazione di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-stamps-and-watermarks/text-in-header/
---
In questo tutorial impareremo come aggiungere testo nell'intestazione di un documento PDF utilizzando Aspose.PDF per .NET. Segui i passaggi seguenti:

## Fase 1: preparazione del progetto

Assicurati di aver installato Aspose.PDF per .NET e di aver creato un progetto C#.

## Passaggio 2: importazione degli spazi dei nomi

Aggiungi i seguenti spazi dei nomi al file di origine C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: apertura del documento

Apri il documento PDF esistente utilizzando il percorso fornito:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 4: creazione del testo dell'intestazione

Crea un nuovo timbro di testo con il testo che desideri aggiungere nell'intestazione:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Puoi personalizzare il testo modificandone le proprietà come margine superiore, allineamento orizzontale e allineamento verticale.

## Passaggio 5: aggiungi il testo dell'intestazione a tutte le pagine

Scorri tutte le pagine del documento PDF e aggiungi il timbro di testo nell'intestazione:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Passaggio 6: salvare il documento PDF

Una volta aggiunto il testo dell'intestazione su tutte le pagine, salvare il documento PDF aggiornato:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Esempio di codice sorgente per Textin Header utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Crea intestazione
TextStamp textStamp = new TextStamp("Header Text");

// Imposta le proprietà del timbro
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Aggiungi intestazione su tutte le pagine
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Salva documento aggiornato
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere testo nell'intestazione di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare le tue intestazioni aggiungendo testo aggiuntivo ai tuoi documenti PDF.
