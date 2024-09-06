---
title: Manipolare la tabella nel file PDF
linktitle: Manipolare la tabella nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Manipola facilmente le tabelle nei file PDF con Aspose.PDF per .NET.
type: docs
weight: 130
url: /it/net/programming-with-tables/manipulate-table/
---
In questo tutorial, ti guideremo passo dopo passo nel processo di manipolazione delle tabelle in un file PDF usando Aspose.PDF per .NET. Le tabelle sono un elemento comune nei documenti PDF e poter modificare il loro contenuto a livello di programmazione può essere molto utile in vari scenari. Utilizzeremo il codice sorgente C# fornito per dimostrare il processo.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro ambiente di sviluppo C# installato.
- La libreria Aspose.PDF per .NET è stata aggiunta come riferimento al progetto.

Ora analizziamo i passaggi necessari per manipolare le tabelle in un documento PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: caricamento del documento PDF

Il primo passo è caricare il documento PDF esistente nella tua applicazione C#. Devi fornire il percorso alla directory in cui si trova il tuo documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Sostituisci "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 2: ricerca delle tabelle nel documento

Per manipolare le tabelle, dobbiamo trovarle all'interno del documento PDF. Aspose.PDF per .NET fornisce una classe TableAbsorber che ci consente di estrarre le tabelle dal documento. Creeremo un'istanza della classe TableAbsorber e visiteremo la pagina desiderata del documento.

```csharp
TableAbsorber absorber = new TableAbsorber();
absorb.Visit(pdfDocument.Pages[1]);
```

In questo esempio, stiamo visitando la prima pagina del documento. Puoi modificare il numero di pagina in base alle tue esigenze.

## Passaggio 3: accesso alle celle della tabella e ai frammenti di testo

Una volta ottenute le tabelle, possiamo accedere alle loro celle e ai frammenti di testo per la manipolazione. Nel codice sorgente fornito, stiamo accedendo alla prima tabella, alla prima cella della sua prima riga e al secondo frammento di testo all'interno di quella cella.

```csharp
TextFragment fragment = absorb.TableList[0].RowList[0].CellList[0].TextFragments[1];
```

È possibile modificare il codice per adattarlo a tabelle, celle o frammenti di testo diversi, in base alle proprie esigenze specifiche.

## Fase 4: Manipolazione del testo della tabella

Con il frammento di testo a cui si accede, ora possiamo modificarne il contenuto. Nell'esempio dato, stiamo cambiando il testo in "hi world".

```csharp
fragment.Text = "hi world";
```

Sentiti libero di sostituire "hi world" con il testo che preferisci.

## Passaggio 5: salvataggio del documento modificato

Una volta apportate le modifiche desiderate, dobbiamo salvare il documento PDF modificato.

```csharp
dataDir = dataDir + "ManipulateTable_out.pdf";
pdfDocument.Save(dataDir);
```

Assicurati di fornire il percorso e il nome file del documento modificato.


### Esempio di codice sorgente per Manipulate Table utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Carica file PDF esistente
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Crea un oggetto TableAbsorber per trovare le tabelle
	TableAbsorber absorber = new TableAbsorber();

	// Visita la prima pagina con l'assorbitore
	absorber.Visit(pdfDocument.Pages[1]);

	// Ottieni l'accesso alla prima tabella della pagina, alla prima cella e ai frammenti di testo in essa contenuti
	TextFragment fragment = absorber.TableList[0].RowList[0].CellList[0].TextFragments[1];

	// Cambia il testo del primo frammento di testo nella cella
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

In questo tutorial, abbiamo imparato come manipolare le tabelle in un documento PDF usando Aspose.PDF per .NET. Seguendo la guida passo passo, puoi caricare facilmente un documento PDF, trovare tabelle, accedere a celle e frammenti di testo, modificare il contenuto della tabella e salvare il documento modificato. Questo approccio fornisce flessibilità ed efficienza quando si ha a che fare con la manipolazione delle tabelle nei documenti PDF.

### FAQ per manipolare la tabella in un file PDF

#### D: Posso manipolare le tabelle nei documenti PDF multipagina?

A: Sì, puoi manipolare le tabelle nei documenti PDF multipagina usando Aspose.PDF per .NET. Nell'esempio fornito, abbiamo visitato la prima pagina del documento (`pdfDocument.Pages[1]`), ma è possibile scorrere tutte le pagine e manipolare le tabelle di ciascuna pagina in base alle proprie esigenze.

#### D: Come posso aggiungere nuove righe o colonne a una tabella esistente?

 A: Per aggiungere nuove righe o colonne a una tabella esistente, puoi utilizzare le API fornite da Aspose.PDF per .NET. Puoi accedere a`RowList` E`CellList` proprietà del`TableAbsorber.TableList` per aggiungere nuove righe e celle a livello di programmazione. Fare riferimento alla documentazione Aspose.PDF per .NET per informazioni dettagliate ed esempi di codice.

#### D: È possibile rimuovere una tabella da un documento PDF?

 R: Sì, puoi rimuovere una tabella da un documento PDF usando Aspose.PDF per .NET. Per ottenere questo risultato, puoi rimuovere lo specifico`Table` oggetto dal`Page.Paragraphs` raccolta. Puoi identificare la tabella da rimuovere utilizzando proprietà come`Table.NumberOfColumns`, `Table.NumberOfRows`e altri identificatori univoci.

#### D: Posso modificare la formattazione (carattere, colore, allineamento) del testo della tabella?

 A: Sì, puoi modificare la formattazione del testo della tabella utilizzando Aspose.PDF per .NET. Puoi accedere a`TextState` proprietà del`TextFragment` oggetto per modificare il carattere, la dimensione del carattere, il colore e l'allineamento del testo.

#### D: Aspose.PDF per .NET supporta l'utilizzo di tabelle nei moduli PDF (AcroForms)?

R: Sì, Aspose.PDF per .NET supporta l'uso di tabelle in moduli PDF (AcroForms). È possibile accedere e manipolare elementi di tabella in moduli PDF in modo simile all'approccio illustrato in questo tutorial. Aspose.PDF per .NET fornisce un ampio supporto per l'uso di AcroForms e campi modulo.