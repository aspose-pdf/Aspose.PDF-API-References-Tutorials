---
title: Esporta i dati del foglio di lavoro Excel nella tabella
linktitle: Esporta i dati del foglio di lavoro Excel nella tabella
second_title: Aspose.PDF per riferimento API .NET
description: Esporta i dati da un foglio Excel a una tabella PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In questo tutorial impareremo come esportare dati da un foglio di lavoro Excel e creare una tabella in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Esamineremo il codice sorgente passo dopo passo e spiegheremo ogni sezione in dettaglio. Alla fine di questo tutorial, sarai in grado di generare file PDF con tabelle contenenti dati da fogli di lavoro Excel. Iniziamo!

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#
- Visual Studio installato nel tuo computer
- Aspose.PDF per la libreria .NET aggiunta al tuo progetto

## Passaggio 1: configurazione dell'ambiente
Per iniziare, crea un nuovo progetto C# in Visual Studio. Aggiungere il riferimento alla libreria Aspose.PDF per .NET facendo clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, selezionando "Gestisci pacchetti NuGet" e cercando "Aspose.PDF". Installa il pacchetto e sei pronto per partire.

## Passaggio 2: caricamento del foglio di lavoro Excel
Nel primo passaggio del nostro codice, definiamo il percorso della directory contenente il documento Excel. Sostituisci "YOUR DOCUMENT DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo file Excel.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Qui, usiamo la libreria Aspose.Cells per caricare la cartella di lavoro di Excel. Assicurati di sostituire "newBook1.xlsx" con il nome del tuo file Excel.

## Passaggio 3: accesso al foglio di lavoro
 Successivamente, dobbiamo accedere al primo foglio di lavoro nel file Excel. Lo facciamo usando il`Worksheets` raccolta del`Workbook` oggetto.

```csharp
// Accesso al primo foglio di lavoro nel file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Se il tuo file Excel contiene più fogli di lavoro, puoi modificare il valore dell'indice`[0]` per accedere a un foglio di lavoro diverso.

## Passaggio 4: esportazione dei dati in DataTable
 Ora esporteremo il contenuto del foglio di lavoro di Excel in a`DataTable` oggetto. Specifichiamo l'intervallo di celle da esportare utilizzando il file`ExportDataTable` metodo.

```csharp
// Esportazione del contenuto di 7 righe e 2 colonne a partire dalla prima cella in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In questo esempio, esportiamo tutte le righe e le colonne a partire dalla prima cella (0, 0) fino all'ultima cella del foglio di lavoro. Impostare l'intervallo appropriato in base alle proprie esigenze.

## Passaggio 5: creazione di un documento PDF
Ora creeremo un nuovo documento PDF utilizzando la libreria Aspose.PDF.

```csharp
// Crea un'istanza di un documento
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Questo crea un documento PDF vuoto in cui possiamo aggiungere contenuto.

## Passaggio 6: aggiunta di una pagina e di una tabella
Per visualizzare i dati in un formato tabella, dobbiamo aggiungere una pagina e una tabella al documento PDF.

```csharp
// Creare una pagina nell'istanza del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crea un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere l'oggetto Table nella raccolta dei paragrafi della sezione
sec1.Paragraphs.Add(tab1);
```

Qui, creiamo una nuova pagina e un oggetto tabella. Aggiungiamo quindi la tabella alla raccolta dei paragrafi della pagina.

## Passaggio 7: impostazione delle proprietà della tabella
Prima di importare i dati, dobbiamo impostare alcune proprietà della tabella, come la larghezza delle colonne e i bordi delle celle predefiniti.

```csharp
// Imposta la larghezza delle colonne della tabella
tab1.ColumnWidths = "40 100 100";

// Imposta il bordo della cella predefinito della tabella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In questo esempio, impostiamo la larghezza delle colonne su 40, 100 e 100 unità. Regola i valori in base ai tuoi dati. Impostiamo anche il bordo della cella predefinito per visualizzare i bordi su tutti i lati di ogni cella.

## Passaggio 8: importazione dei dati nella tabella
 Ora importeremo i dati dal file`DataTable` oggetto nella tabella utilizzando il`ImportDataTable` metodo.

```csharp
// Importa i dati nell'oggetto Table dal DataTable creato in precedenza
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Qui specifichiamo l'intervallo di righe e colonne da importare. In questo esempio, importiamo tutte le righe e le colonne dal file`dataTable` oggetto.

## Passaggio 9: formattazione della tabella
Per migliorare l'aspetto della tabella, possiamo applicare la formattazione a celle o righe specifiche. In questo passaggio, formatteremo la prima riga e alterneremo le righe della tabella.

```csharp
// Ottieni la prima riga dalla tabella
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatta la prima riga
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

// Formato di riga alternativo
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Imposta il colore di sfondo delle celle in righe alternate
         curCell.BackgroundColor = Color.Gray;
        
         // Imposta il colore del testo delle celle in righe alternate
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Qui, iteriamo attraverso le celle nella prima riga e impostiamo il colore di sfondo, il tipo di carattere, il colore del carattere e l'allineamento del testo. Quindi, iteriamo attraverso tutte le celle nelle righe alternate e impostiamo il loro sfondo e il colore del testo.

## Passaggio 10: salvare il documento PDF
Infine, salviamo il documento PDF nella posizione specificata.

```csharp
// Salva il PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Assicurati di sostituire "YOUR DOCUMENT DIRECTORY" con il percorso della directory e il nome file desiderati per il file PDF di output.

### Esempio di codice sorgente per l'esportazione dei dati del foglio di lavoro Excel nella tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Accesso al primo foglio di lavoro nel file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Esportazione del contenuto di 7 righe e 2 colonne a partire dalla prima cella in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Crea un'istanza di Document instanc
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Creare una pagina nell'istanza del documento
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Crea un oggetto Tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Aggiungere l'oggetto Table nella raccolta dei paragrafi della sezione
sec1.Paragraphs.Add(tab1);

// Imposta la larghezza delle colonne della tabella. Dobbiamo specificare il ColumnCount manualmente.
// Poiché il foglio di lavoro Excel attuale ha tre colonne, stiamo specificando lo stesso conteggio
tab1.ColumnWidths = "40 100 100";

// Imposta il bordo della cella predefinito della tabella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importa i dati nell'oggetto Table dal DataTable creato in precedenza
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Ottieni la prima riga dalla tabella
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Scorri tutte le celle nella prima riga e imposta il colore di sfondo su blu
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Imposta lo sfondo di tutte le celle nella prima riga della tabella.
	curCell.BackgroundColor = Color.Blue;
	// Imposta il tipo di carattere per le celle della prima riga nella tabella.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Imposta il colore del carattere di tutte le celle nella prima riga della tabella.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Imposta l'allineamento del testo per le celle della prima riga come Centro.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Scorri tutte le celle nella prima riga e imposta il colore di sfondo su blu
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Imposta il colore di sfondo di tutte le celle tranne la prima riga.
		curCell.BackgroundColor = Color.Gray;
		// Imposta il colore del testo di tutte le celle tranne la prima riga.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Salva il Pdf
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come esportare i dati da un foglio di lavoro Excel a una tabella PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo coperto il processo dettagliato di caricamento del foglio di lavoro Excel, creazione di un documento PDF, aggiunta di una tabella, importazione di dati e formattazione della tabella. Ora puoi generare file PDF con tabelle contenenti dati Excel in modo programmatico.

### FAQ

#### D: Qual è lo scopo dell'esportazione dei dati del foglio di lavoro Excel in una tabella PDF?

R: L'esportazione dei dati del foglio di lavoro Excel in una tabella PDF consente di presentare i dati in un formato strutturato e organizzato. Ti consente di generare file PDF con tabelle che contengono dati da fogli di lavoro Excel, semplificando la condivisione e la conservazione delle informazioni in un formato di documento portatile.

#### D: Posso personalizzare l'aspetto della tabella PDF?

A: Sì, è possibile personalizzare l'aspetto della tabella PDF utilizzando varie proprietà fornite da Aspose.PDF per .NET. Nel codice sorgente C# fornito, puoi modificare la larghezza delle colonne, i bordi delle celle, l'allineamento del testo, lo stile del carattere e altro ancora per soddisfare le tue esigenze specifiche.

#### D: Come gestisco i file Excel con più fogli di lavoro?

 R: Nel codice C# fornito, abbiamo effettuato l'accesso al primo foglio di lavoro nel file Excel utilizzando il file index`[0]` . Se il tuo file Excel contiene più fogli di lavoro, puoi accedervi modificando il valore dell'indice di conseguenza, ad esempio`[1]` per il secondo foglio di lavoro o`[2]` per il terzo foglio di lavoro.

#### D: Posso applicare una formattazione diversa a righe o celle specifiche nella tabella PDF?

R: Sì, puoi applicare una formattazione diversa a righe o celle specifiche nella tabella PDF. Nel codice sorgente C# fornito, abbiamo dimostrato come formattare la prima riga e alternare le righe in modo diverso modificando il colore di sfondo, lo stile del carattere e il colore del carattere. È possibile applicare tecniche di formattazione simili a righe o celle specifiche, se necessario.

#### D: Aspose.PDF per .NET è l'unica libreria che consente di esportare dati Excel in una tabella PDF?

R: Aspose.PDF per .NET è una potente libreria per lavorare con documenti PDF in applicazioni .NET. Sebbene possano essere disponibili altre librerie, Aspose.PDF per .NET offre un'ampia gamma di funzionalità e capacità per generare, manipolare ed esportare file PDF con tabelle da dati Excel, rendendolo una scelta popolare per tali attività.