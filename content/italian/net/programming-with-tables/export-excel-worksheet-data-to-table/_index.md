---
title: Esporta i dati del foglio di lavoro Excel in una tabella
linktitle: Esporta i dati del foglio di lavoro Excel in una tabella
second_title: Riferimento API Aspose.PDF per .NET
description: Esportare dati da un foglio Excel in una tabella PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In questo tutorial, impareremo come esportare dati da un foglio di lavoro Excel e creare una tabella in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Esamineremo il codice sorgente passo dopo passo e spiegheremo ogni sezione in dettaglio. Alla fine di questo tutorial, sarai in grado di generare file PDF con tabelle contenenti dati da fogli di lavoro Excel. Cominciamo!

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Visual Studio installato sul tuo computer
- Libreria Aspose.PDF per .NET aggiunta al tuo progetto

## Fase 1: Impostazione dell'ambiente
Per iniziare, crea un nuovo progetto C# in Visual Studio. Aggiungi il riferimento alla libreria Aspose.PDF per .NET facendo clic con il pulsante destro del mouse sul tuo progetto in Solution Explorer, selezionando "Manage NuGet Packages" e cercando "Aspose.PDF". Installa il pacchetto e sei pronto per iniziare.

## Passaggio 2: caricamento del foglio di lavoro Excel
Nel primo passaggio del nostro codice, definiamo il percorso della directory contenente il documento Excel. Sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo file Excel.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Qui, utilizziamo la libreria Aspose.Cells per caricare la cartella di lavoro di Excel. Assicurati di sostituire "newBook1.xlsx" con il nome del tuo file Excel.

## Passaggio 3: accesso al foglio di lavoro
 Successivamente, dobbiamo accedere al primo foglio di lavoro nel file Excel. Lo facciamo utilizzando`Worksheets` raccolta di`Workbook` oggetto.

```csharp
// Accesso al primo foglio di lavoro nel file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Se il file Excel contiene più fogli di lavoro, è possibile modificare il valore dell'indice`[0]` per accedere a un foglio di lavoro diverso.

## Passaggio 4: esportazione dei dati in DataTable
 Ora esporteremo il contenuto del foglio di lavoro Excel in un`DataTable` oggetto. Specifichiamo l'intervallo di celle da esportare utilizzando`ExportDataTable` metodo.

```csharp
// Esportazione del contenuto di 7 righe e 2 colonne a partire dalla 1a cella in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In questo esempio, esportiamo tutte le righe e le colonne a partire dalla prima cella (0, 0) fino all'ultima cella del foglio di lavoro. Imposta l'intervallo appropriato in base alle tue esigenze.

## Passaggio 5: creazione di un documento PDF
Ora creeremo un nuovo documento PDF utilizzando la libreria Aspose.PDF.

```csharp
// Crea un'istanza di Documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Verrà creato un documento PDF vuoto in cui potremo aggiungere contenuti.

## Passaggio 6: aggiunta di una pagina e di una tabella
Per visualizzare i dati in formato tabella, dobbiamo aggiungere una pagina e una tabella al documento PDF.

```csharp
// Crea una pagina nell'istanza del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crea un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere l'oggetto Tabella nella raccolta dei paragrafi della sezione
sec1.Paragraphs.Add(tab1);
```

Qui creiamo una nuova pagina e un oggetto tabella. Aggiungiamo quindi la tabella alla raccolta di paragrafi della pagina.

## Passaggio 7: impostazione delle proprietà della tabella
Prima di importare i dati, dobbiamo impostare alcune proprietà della tabella, come la larghezza delle colonne e i bordi predefiniti delle celle.

```csharp
// Imposta la larghezza delle colonne della tabella
tab1.ColumnWidths = "40 100 100";

// Imposta il bordo predefinito della cella della tabella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In questo esempio, impostiamo le larghezze delle colonne a 40, 100 e 100 unità. Regoliamo i valori in base ai dati. Impostiamo anche il bordo predefinito della cella per visualizzare i bordi su tutti i lati di ogni cella.

## Passaggio 8: importazione dei dati nella tabella
 Ora importeremo i dati dal`DataTable` oggetto nella tabella utilizzando il`ImportDataTable` metodo.

```csharp
// Importa i dati nell'oggetto Tabella dalla DataTable creata sopra
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Qui specifichiamo l'intervallo di righe e colonne da importare. In questo esempio importiamo tutte le righe e le colonne dal`dataTable` oggetto.

## Passaggio 9: formattazione della tabella
Per migliorare l'aspetto della tabella, possiamo applicare la formattazione a celle o righe specifiche. In questo passaggio, formatteremo la prima riga e le righe alterne della tabella.

```csharp
// Prendi la prima riga dalla tabella
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formattare la prima riga
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Imposta il colore di sfondo delle celle nella prima riga
     curCell.BackgroundColor = Color.Blue;// Imposta la faccia per le celle nella prima riga
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Imposta il colore del carattere delle celle nella prima riga
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Imposta l'allineamento del testo per le celle nella prima riga
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Formato riga alternata
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Imposta il colore di sfondo delle celle in righe alterne
         curCell.BackgroundColor = Color.Gray;
        
         // Imposta il colore del testo delle celle in righe alterne
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Qui, scorriamo le celle nella prima riga e impostiamo il loro colore di sfondo, il tipo di carattere, il colore del carattere e l'allineamento del testo. Quindi, scorriamo tutte le celle nelle righe alterne e impostiamo il loro colore di sfondo e del testo.

## Passaggio 10: salvataggio del documento PDF
Infine, salviamo il documento PDF nella posizione specificata.

```csharp
// Salva il PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Assicurati di sostituire "DIRECTORY DEI TUOI DOCUMENTI" con il percorso della directory e il nome file desiderati per il file PDF di output.

### Esempio di codice sorgente per esportare i dati del foglio di lavoro Excel in una tabella utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Accesso al primo foglio di lavoro nel file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Esportazione del contenuto di 7 righe e 2 colonne a partire dalla 1a cella in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Crea un'istanza di un documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Crea una pagina nell'istanza del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crea un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere l'oggetto Tabella nella raccolta dei paragrafi della sezione
sec1.Paragraphs.Add(tab1);

// Imposta le larghezze delle colonne della tabella. Dobbiamo specificare ColumnCount manualmente.
// Poiché l'attuale foglio di lavoro Excel ha tre colonne, stiamo specificando lo stesso conteggio
tab1.ColumnWidths = "40 100 100";

// Imposta il bordo predefinito della cella della tabella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importa i dati nell'oggetto Tabella dalla DataTable creata sopra
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Prendi la prima riga dalla tabella
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Scorrere tutte le celle nella prima riga e impostare il colore di sfondo su blu
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Imposta lo sfondo di tutte le celle nella prima riga della tabella.
	curCell.BackgroundColor = Color.Blue;
	// Imposta il tipo di carattere per le celle della prima riga della tabella.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Imposta il colore del carattere di tutte le celle nella prima riga della tabella.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Imposta l'allineamento del testo per le celle della prima riga come Centro.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Scorrere tutte le celle nella prima riga e impostare il colore di sfondo su blu
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Imposta il colore di sfondo di tutte le celle, tranne quella della prima riga.
		curCell.BackgroundColor = Color.Gray;
		// Imposta il colore del testo di tutte le celle eccetto la prima riga.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Salva il PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come esportare dati da un foglio di lavoro Excel a una tabella PDF usando la libreria Aspose.PDF per .NET. Abbiamo trattato il processo passo dopo passo di caricamento del foglio di lavoro Excel, creazione di un documento PDF, aggiunta di una tabella, importazione di dati e formattazione della tabella. Ora puoi generare file PDF con tabelle contenenti dati Excel in modo programmatico.

### Domande frequenti

#### D: Qual è lo scopo dell'esportazione dei dati del foglio di lavoro Excel in una tabella PDF?

A: L'esportazione dei dati del foglio di lavoro Excel in una tabella PDF consente di presentare i dati in un formato strutturato e organizzato. Consente di generare file PDF con tabelle che contengono dati da fogli di lavoro Excel, semplificando la condivisione e la conservazione delle informazioni in un formato di documento portatile.

#### D: Posso personalizzare l'aspetto della tabella PDF?

R: Sì, puoi personalizzare l'aspetto della tabella PDF utilizzando varie proprietà fornite da Aspose.PDF per .NET. Nel codice sorgente C# fornito, puoi modificare le larghezze delle colonne, i bordi delle celle, l'allineamento del testo, lo stile del carattere e altro ancora per adattarli ai tuoi requisiti specifici.

#### D: Come faccio a gestire i file Excel con più fogli di lavoro?

 A: Nel codice C# fornito, abbiamo avuto accesso al primo foglio di lavoro nel file Excel utilizzando l'indice`[0]` Se il tuo file Excel contiene più fogli di lavoro, puoi accedervi modificando di conseguenza il valore dell'indice, ad esempio`[1]` per il secondo foglio di lavoro o`[2]` per il terzo foglio di lavoro.

#### D: Posso applicare una formattazione diversa a righe o celle specifiche nella tabella PDF?

R: Sì, puoi applicare una formattazione diversa a righe o celle specifiche nella tabella PDF. Nel codice sorgente C# fornito, abbiamo dimostrato come formattare la prima riga e le righe alternate in modo diverso modificandone il colore di sfondo, lo stile del carattere e il colore del carattere. Puoi applicare tecniche di formattazione simili a qualsiasi riga o cella specifica, se necessario.

#### D: Aspose.PDF per .NET è l'unica libreria che consente di esportare dati Excel in una tabella PDF?

R: Aspose.PDF per .NET è una potente libreria per lavorare con documenti PDF in applicazioni .NET. Sebbene possano essere disponibili altre librerie, Aspose.PDF per .NET offre un'ampia gamma di funzionalità e capacità per generare, manipolare ed esportare file PDF con tabelle da dati Excel, rendendolo una scelta popolare per tali attività.