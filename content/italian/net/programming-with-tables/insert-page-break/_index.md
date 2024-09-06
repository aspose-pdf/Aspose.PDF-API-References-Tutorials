---
title: Inserisci interruzione di pagina nel file PDF
linktitle: Inserisci interruzione di pagina nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come inserire un'interruzione di pagina in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-tables/insert-page-break/
---
In questo tutorial, impareremo come inserire un'interruzione di pagina in un file PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come aggiungere un'interruzione di pagina dopo un certo numero di righe in una tabella di un documento PDF. Iniziamo!

## Fase 1: Impostazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa i namespace necessari.

## Fase 2: creazione del documento e della tabella
Creiamo una nuova istanza Document e aggiungiamo una pagina a questo documento. Poi, creiamo un'istanza Table per rappresentare la nostra tabella nel documento PDF. Definiamo anche gli stili dei bordi per la tabella.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Passaggio 3: aggiungere righe alla tabella
Utilizziamo un ciclo per aggiungere 200 righe all'array. Per ogni riga, creiamo un'istanza di Row e aggiungiamo due celle con contenuto di testo.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Quando vengono aggiunte 10 righe, inseriamo una nuova interruzione di pagina
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Fase 4: Aggiunta della tabella al documento
Aggiungiamo la tabella alla raccolta dei paragrafi della pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Passaggio 5: Salvare il documento
Salviamo il documento PDF con l'interruzione di pagina inserita.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Esempio di codice sorgente per Inserisci interruzione di pagina utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza del documento
Document doc = new Document();
// Aggiungi pagina alla raccolta di pagine del file PDF
doc.Pages.Add();
// Crea istanza tabella
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Imposta lo stile del bordo per la tabella
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Imposta lo stile del bordo predefinito per la tabella con il colore del bordo come Rosso
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Specificare la larghezza delle colonne della tabella
tab.ColumnWidths = "100 100";
// Crea un ciclo per aggiungere 200 righe per la tabella
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Quando vengono aggiunte 10 righe, visualizza la nuova riga in una nuova pagina
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Aggiungi tabella alla raccolta di paragrafi del file PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Salva il documento PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come inserire un'interruzione di pagina in un documento PDF usando Aspose.PDF per .NET. Puoi usare questa guida passo passo per aggiungere un'interruzione di pagina dopo un certo numero di righe in una tabella in un documento PDF usando C#.

### FAQ per inserire un'interruzione di pagina in un file PDF

#### D: Come posso modificare le dimensioni delle nuove pagine create dopo l'interruzione di pagina?

 A: Per modificare la dimensione della pagina per le nuove pagine create dopo l'interruzione di pagina, è possibile impostare`PageSize` proprietà del`Page` oggetto. Ad esempio, puoi usare il seguente codice per impostare la dimensione della pagina su A4:

```csharp
// Imposta la dimensione della pagina su A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### D: Posso controllare i margini delle nuove pagine dopo l'interruzione di pagina?

 A: Sì, puoi controllare i margini di pagina per le nuove pagine dopo l'interruzione di pagina. Usa il`Margin` proprietà del`Page` oggetto per impostare i margini della pagina. Ad esempio, per impostare tutti i margini a 10 punti, puoi usare il seguente codice:

```csharp
// Imposta tutti i margini a 10 punti
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### D: È possibile aggiungere intestazioni e piè di pagina alle nuove pagine dopo l'interruzione di pagina?

 A: Sì, puoi aggiungere intestazioni e piè di pagina alle nuove pagine dopo l'interruzione di pagina. Utilizza il`Page.Header` E`Page.Footer` proprietà per aggiungere contenuto alle sezioni intestazione e piè di pagina della pagina. Ad esempio:

```csharp
// Aggiungere l'intestazione alle nuove pagine
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Aggiungere il piè di pagina alle nuove pagine
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### D: Posso inserire interruzioni di pagina in posizioni specifiche, oltre a un certo numero di righe?

 A: Sì, puoi inserire interruzioni di pagina in posizioni specifiche diverse da dopo un certo numero di righe. Puoi impostare`IsInNewPage` proprietà di una riga a`true` per forzare la tabella a iniziare una nuova pagina dopo quella riga.

#### D: Come posso regolare il comportamento delle interruzioni di pagina in base all'altezza del contenuto?

 A: Puoi usare il`IsBroken` proprietà della tabella per abilitare o disabilitare l'interruzione automatica delle righe tra le pagine. Quando impostato su`true`, consente di suddividere le righe nelle pagine in base all'altezza del contenuto.