---
title: Testo nel piè di pagina del file PDF
linktitle: Testo nel piè di pagina del file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Impara ad aggiungere testo nel piè di pagina del file PDF con Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In questo tutorial impareremo come aggiungere testo nel piè di pagina del file PDF utilizzando Aspose.PDF per .NET. Segui i passaggi seguenti:

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

### Domande frequenti per il testo nel piè di pagina del file PDF

#### D: Qual è lo scopo dell'aggiunta di testo nel piè di pagina di un documento PDF?

R: L'aggiunta di testo nel piè di pagina di un documento PDF consente di includere informazioni importanti, come avvisi di copyright, numeri di pagina, versione del documento o qualsiasi altro testo che desideri venga visualizzato in modo coerente nella parte inferiore di ogni pagina.

#### D: In che modo il codice sorgente C# fornito ottiene l'aggiunta di testo nel piè di pagina di un documento PDF?

R: Il codice mostra il processo di apertura di un documento PDF esistente, la creazione di un timbro di testo con il testo del piè di pagina desiderato, la personalizzazione delle proprietà del testo, l'aggiunta del timbro di testo a tutte le pagine e infine il salvataggio del documento PDF aggiornato con il testo del piè di pagina aggiunto.

#### D: Posso modificare l'aspetto del testo del piè di pagina, come font, dimensioni, colore e allineamento?

 R: Sì, puoi personalizzare l'aspetto del testo del piè di pagina modificando le proprietà del file`TextStamp` oggetto. L'esempio di codice include l'impostazione di proprietà come margine inferiore, allineamento orizzontale e allineamento verticale. Puoi anche regolare il carattere, la dimensione, il colore e altre proprietà relative al testo.

#### D: È possibile aggiungere un testo diverso al piè di pagina di ciascuna pagina?

 R: Sì, puoi aggiungere un testo diverso al piè di pagina di ciascuna pagina creando file separati`TextStamp` oggetti con contenuto di testo o proprietà differenti e quindi aggiungendoli a pagine specifiche secondo necessità.

#### D: Come posso assicurarmi che il testo del piè di pagina appaia uniformemente su ogni pagina del documento PDF?

R: Usando un ciclo che itera attraverso tutte le pagine del documento PDF e aggiungendo lo stesso timbro di testo a ogni pagina, ti assicuri che il testo del piè di pagina appaia coerente su ogni pagina.

#### D: Posso aggiungere più righe di testo o formattare il testo del piè di pagina con interruzioni di riga?

 R: Sì, puoi aggiungere più righe di testo al piè di pagina includendo interruzioni di riga nella stringa di testo. Ad esempio, puoi utilizzare la sequenza di escape`\n` per indicare un'interruzione di riga nel testo.

#### D: Cosa succede se desidero aggiungere contenuti diversi all'intestazione e al piè di pagina dello stesso documento PDF?

R: Per aggiungere contenuti diversi alle sezioni di intestazione e piè di pagina, segui passaggi simili per entrambe le sezioni. Il codice mostra l'aggiunta di testo al piè di pagina; puoi utilizzare un approccio simile per aggiungere testo all'intestazione.

#### D: È possibile aggiungere immagini o altri elementi accanto al testo del piè di pagina utilizzando questo approccio?

A: Sebbene il codice fornito dimostri specificamente l'aggiunta di testo al piè di pagina, puoi estendere l'approccio per aggiungere altri elementi come immagini, linee, forme o qualsiasi altro contenuto alla sezione del piè di pagina utilizzando la libreria Aspose.PDF.