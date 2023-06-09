---
title: Inserisci interruzione di pagina
linktitle: Inserisci interruzione di pagina
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come inserire un'interruzione di pagina in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-tables/insert-page-break/
---

In questo tutorial impareremo come inserire un'interruzione di pagina in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come aggiungere un'interruzione di pagina dopo un certo numero di righe in una tabella di un documento PDF. Iniziamo!

## Passaggio 1: configurazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungere il riferimento alla libreria e importare gli spazi dei nomi necessari.

## Passaggio 2: creazione del documento e della tabella
Creiamo una nuova istanza Document e aggiungiamo una pagina a questo documento. Successivamente, creiamo un'istanza Table per rappresentare la nostra tabella nel documento PDF. Definiamo anche gli stili del bordo per la tabella.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Passaggio 3: aggiungi righe alla tabella
Usiamo un ciclo per aggiungere 200 righe all'array. Per ogni riga, creiamo un'istanza di Row e aggiungiamo due celle con contenuto testuale.

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

## Passaggio 4: aggiunta della tabella al documento
Aggiungiamo la tabella alla raccolta dei paragrafi della pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Passaggio 5: salvare il documento
Salviamo il documento PDF con l'interruzione di pagina inserita.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Esempio di codice sorgente per Inserisci interruzione di pagina utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanza documento istanza
Document doc = new Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
doc.Pages.Add();
// Crea un'istanza di tabella
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Imposta lo stile del bordo per la tabella
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Imposta lo stile del bordo predefinito per la tabella con il colore del bordo come Rosso
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Specifica la larghezza delle colonne della tabella
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
	// Quando vengono aggiunte 10 righe, visualizza la nuova riga nella nuova pagina
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
In questo tutorial, abbiamo imparato come inserire un'interruzione di pagina in un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questa guida dettagliata per aggiungere un'interruzione di pagina dopo un determinato numero di righe in una tabella in un documento PDF utilizzando C#.