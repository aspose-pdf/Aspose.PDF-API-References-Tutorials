---
title: Testo nel piè di pagina del file PDF
linktitle: Testo nel piè di pagina del file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Impara ad aggiungere testo nel piè di pagina di un file PDF con Aspose.PDF per .NET.
type: docs
weight: 180
url: /it/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In questo tutorial, impareremo come aggiungere testo nel piè di pagina del file PDF utilizzando Aspose.PDF per .NET. Segui i passaggi sottostanti:

## Fase 1: Preparazione del progetto

Assicurati di aver installato Aspose.PDF per .NET e di aver creato un progetto C#.

## Passaggio 2: importazione degli spazi dei nomi

Aggiungere i seguenti namespace al file sorgente C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Fase 3: Apertura del documento

Aprire il documento PDF esistente utilizzando il percorso fornito:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 4: creare il testo del piè di pagina

Crea un nuovo timbro di testo con il testo che desideri aggiungere nel piè di pagina:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

È possibile personalizzare il testo modificandone le proprietà, ad esempio il margine inferiore, l'allineamento orizzontale e quello verticale.

## Passaggio 5: aggiungere il testo del piè di pagina a tutte le pagine

Esaminare tutte le pagine del documento PDF e aggiungere il timbro di testo nel piè di pagina:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Passaggio 6: salvataggio del documento PDF

Una volta aggiunto il testo del piè di pagina su tutte le pagine, salvare il documento PDF aggiornato:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

### Esempio di codice sorgente per Textin Footer utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
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

Congratulazioni! Hai imparato come aggiungere testo nel piè di pagina di un documento PDF usando Aspose.PDF per .NET. Ora puoi personalizzare i tuoi piè di pagina aggiungendo testo aggiuntivo ai tuoi documenti PDF.

### Domande frequenti sul testo nel piè di pagina del file PDF

#### D: Qual è lo scopo di aggiungere testo nel piè di pagina di un documento PDF?

R: L'aggiunta di testo nel piè di pagina di un documento PDF consente di includere informazioni importanti, come note di copyright, numeri di pagina, versione del documento o qualsiasi altro testo che si desidera venga visualizzato in modo coerente in fondo a ogni pagina.

#### D: In che modo il codice sorgente C# fornito consente di aggiungere testo nel piè di pagina di un documento PDF?

R: Il codice illustra il processo di apertura di un documento PDF esistente, creazione di un timbro di testo con il testo desiderato per il piè di pagina, personalizzazione delle proprietà del testo, aggiunta del timbro di testo a tutte le pagine e, infine, salvataggio del documento PDF aggiornato con il testo aggiunto per il piè di pagina.

#### D: Posso modificare l'aspetto del testo del piè di pagina, ad esempio il carattere, la dimensione, il colore e l'allineamento?

 A: Sì, puoi personalizzare l'aspetto del testo del piè di pagina modificando le proprietà del`TextStamp` object. L'esempio di codice include l'impostazione di proprietà come margine inferiore, allineamento orizzontale e allineamento verticale. Puoi anche regolare il font, la dimensione, il colore e altre proprietà relative al testo.

#### D: È possibile aggiungere un testo diverso al piè di pagina di ogni pagina?

 A: Sì, puoi aggiungere testo diverso al piè di pagina di ogni pagina creando un testo separato`TextStamp` oggetti con contenuti di testo o proprietà diversi e poi aggiungerli a pagine specifiche in base alle necessità.

#### D: Come posso assicurarmi che il testo del piè di pagina venga visualizzato in modo uniforme in ogni pagina del documento PDF?

R: Utilizzando un ciclo che scorre tutte le pagine del documento PDF e aggiungendo lo stesso timbro di testo a ogni pagina, si garantisce che il testo del piè di pagina venga visualizzato in modo coerente in ogni pagina.

#### D: Posso aggiungere più righe di testo o formattare il testo del piè di pagina con interruzioni di riga?

 R: Sì, puoi aggiungere più righe di testo al piè di pagina includendo interruzioni di riga nella stringa di testo. Ad esempio, puoi usare la sequenza di escape`\n` per indicare un'interruzione di riga nel testo.

#### D: Cosa succede se voglio aggiungere contenuti diversi all'intestazione e al piè di pagina dello stesso documento PDF?

R: Per aggiungere contenuti diversi alle sezioni header e footer, dovresti seguire passaggi simili per entrambe le sezioni. Il codice dimostra come aggiungere testo al footer; puoi usare un approccio simile per aggiungere testo all'header.

#### D: È possibile aggiungere immagini o altri elementi insieme al testo del piè di pagina utilizzando questo approccio?

R: Sebbene il codice fornito dimostri specificamente come aggiungere testo al piè di pagina, è possibile estendere l'approccio per aggiungere altri elementi come immagini, linee, forme o qualsiasi altro contenuto alla sezione del piè di pagina utilizzando la libreria Aspose.PDF.