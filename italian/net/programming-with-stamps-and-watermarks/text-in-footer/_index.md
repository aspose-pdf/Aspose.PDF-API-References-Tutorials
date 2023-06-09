---
title: Testo nel piè di pagina
linktitle: Testo nel piè di pagina
second_title: Aspose.PDF per riferimento API .NET
description: Impara ad aggiungere testo nel piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In questo tutorial impareremo come aggiungere testo nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Segui i passaggi seguenti:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 4: crea il testo del piè di pagina

Crea un nuovo timbro di testo con il testo che desideri aggiungere nel piè di pagina:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Puoi personalizzare il testo modificandone le proprietà come margine inferiore, allineamento orizzontale e allineamento verticale.

## Passaggio 5: aggiungi il testo del piè di pagina a tutte le pagine

Scorri tutte le pagine del documento PDF e aggiungi il timbro di testo nel piè di pagina:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Passaggio 6: salvare il documento PDF

Una volta che il testo del piè di pagina è stato aggiunto su tutte le pagine, salva il documento PDF aggiornato:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Esempio di codice sorgente per Textin Footer utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Crea piè di pagina
TextStamp textStamp = new TextStamp("Footer Text");

// Imposta le proprietà del timbro
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Aggiungi piè di pagina su tutte le pagine
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Salva il file PDF aggiornato
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere testo nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare i tuoi piè di pagina aggiungendo testo aggiuntivo ai tuoi documenti PDF.
