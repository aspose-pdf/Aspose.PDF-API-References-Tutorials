---
title: Manipolare la tabella nel file PDF
linktitle: Manipolare la tabella nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Manipola facilmente le tabelle nei file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-tables/manipulate-table/
---
In questo tutorial ti guideremo attraverso il processo passo passo di manipolazione delle tabelle nel file PDF utilizzando Aspose.PDF per .NET. Le tabelle sono un elemento comune nei documenti PDF e la possibilità di modificarne il contenuto a livello di codice può essere molto utile in vari scenari. Utilizzeremo il codice sorgente C# fornito per dimostrare il processo.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo C# installato.
- Libreria Aspose.PDF per .NET aggiunta come riferimento al tuo progetto.

Ora, approfondiamo i passaggi necessari per manipolare le tabelle in un documento PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nell'applicazione C#. È necessario fornire il percorso della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Sostituisci "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: ricerca di tabelle nel documento

Per manipolare le tabelle, dobbiamo trovarle all'interno del documento PDF. Aspose.PDF per .NET fornisce una classe TableAbsorber che ci consente di estrarre tabelle dal documento. Creeremo un'istanza della classe TableAbsorber e visiteremo la pagina desiderata del documento.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

In questo esempio, stiamo visitando la prima pagina del documento. Puoi modificare il numero di pagina in base alle tue esigenze.

## Passaggio 3: accesso alle celle della tabella e ai frammenti di testo

Una volta che abbiamo le tabelle, possiamo accedere alle loro celle e ai frammenti di testo per manipolarli. Nel codice sorgente fornito, accediamo alla prima tabella, alla prima cella della sua prima riga e al secondo frammento di testo all'interno di quella cella.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

Puoi modificare il codice per scegliere come target tabelle, celle o frammenti di testo diversi in base alle tue esigenze specifiche.

## Passaggio 4: manipolazione del testo della tabella

Una volta effettuato l'accesso al frammento di testo, ora possiamo modificarne il contenuto. Nell'esempio fornito, stiamo cambiando il testo in "hi world".

```csharp
fragment.Text = "hi world";
```

Sentiti libero di sostituire "ciao mondo" con il testo desiderato.

## Passaggio 5: salvataggio del documento modificato

Una volta apportate le modifiche desiderate, dobbiamo salvare il documento PDF modificato.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Assicurati di fornire il percorso e il nome file del documento modificato.


### Codice sorgente di esempio per Manipulate Table utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Carica il file PDF esistente
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Crea un oggetto TableAbsorber per trovare le tabelle
	TableAbsorber absorber = new TableAbsorber();

	// Visita la prima pagina con l'assorbitore
	absorber.Visit(pdfDocument.Pages[1]);

	// Ottieni l'accesso alla prima tabella della pagina, alla prima cella e ai frammenti di testo in essa contenuti
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Modifica il testo del primo frammento di testo nella cella
	fragment.Text = "hi world";
	dataDir = dataDir + "ManipulateTable_out.pdf";
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nTable manipulated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo imparato come manipolare le tabelle in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo la guida passo passo, puoi caricare facilmente un documento PDF, trovare tabelle, accedere a celle e frammenti di testo, modificare il contenuto della tabella e salvare il documento modificato. Questo approccio offre flessibilità ed efficienza nella gestione della manipolazione delle tabelle nei documenti PDF.

### Domande frequenti sulla manipolazione della tabella nel file PDF

#### D: Posso manipolare tabelle in documenti PDF multipagina?

R: Sì, puoi manipolare tabelle in documenti PDF multipagina utilizzando Aspose.PDF per .NET. Nell'esempio fornito, abbiamo visitato la prima pagina del documento (`pdfDocument.Pages[1]`), ma puoi scorrere tutte le pagine e manipolare le tabelle su ciascuna pagina secondo necessità.

#### D: Come posso aggiungere nuove righe o colonne a una tabella esistente?

 R: Per aggiungere nuove righe o colonne a una tabella esistente, è possibile utilizzare le API fornite da Aspose.PDF per .NET. Puoi accedere al`RowList` E`CellList` proprietà del`TableAbsorber.TableList` per aggiungere nuove righe e celle a livello di codice. Fare riferimento alla documentazione Aspose.PDF per .NET per informazioni dettagliate ed esempi di codice.

#### D: È possibile rimuovere una tabella da un documento PDF?

 R: Sì, puoi rimuovere una tabella da un documento PDF utilizzando Aspose.PDF per .NET. Per raggiungere questo obiettivo, è possibile rimuovere lo specifico`Table` oggetto da`Page.Paragraphs` collezione. È possibile identificare la tabella da rimuovere utilizzando proprietà come`Table.NumberOfColumns`, `Table.NumberOfRows`e altri identificatori univoci.

#### D: Posso modificare la formattazione (carattere, colore, allineamento) del testo della tabella?

 R: Sì, puoi modificare la formattazione del testo della tabella utilizzando Aspose.PDF per .NET. Puoi accedere al`TextState` proprietà del`TextFragment` oggetto per modificare il carattere, la dimensione del carattere, il colore e l'allineamento del testo.

#### D: Aspose.PDF per .NET supporta l'utilizzo di tabelle nei moduli PDF (AcroForms)?

R: Sì, Aspose.PDF per .NET supporta il lavoro con tabelle nei moduli PDF (AcroForms). Puoi accedere e manipolare gli elementi della tabella nei moduli PDF in modo simile all'approccio dimostrato in questo tutorial. Aspose.PDF per .NET fornisce un ampio supporto per lavorare con AcroForms e campi modulo.