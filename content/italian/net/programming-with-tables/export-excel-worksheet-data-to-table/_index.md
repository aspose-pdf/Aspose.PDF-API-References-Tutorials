---
title: Esporta i dati del foglio di lavoro Excel in una tabella
linktitle: Esporta i dati del foglio di lavoro Excel in una tabella
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come esportare i dati del foglio di lavoro Excel in una tabella PDF utilizzando Aspose.PDF per .NET. Esercitazione dettagliata con esempi di codice, prerequisiti e suggerimenti utili.
type: docs
weight: 70
url: /it/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Introduzione

Hai mai avuto bisogno di esportare dati da un foglio di lavoro Excel in un file PDF, ordinatamente disposti in un formato tabella? Immagina di avere un mucchio di dati in Excel, ma di doverli condividere come PDF dall'aspetto professionale. Può sembrare complicato, vero? Ma con Aspose.PDF per .NET, puoi trasformare questa attività in un gioco da ragazzi. In questo tutorial, ti guideremo attraverso il processo di esportazione dei dati del foglio di lavoro Excel in una tabella all'interno di un documento PDF utilizzando Aspose.PDF per .NET. Ti guideremo passo dopo passo, suddividendo tutto in modo che anche se sei alle prime armi, ti sentirai un professionista alla fine.

## Prerequisiti

Prima di addentrarci nella codifica, prepariamo alcune cose:

1.  Aspose.PDF per la libreria .NET – Assicurati di avere installata la versione più recente. Puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells per la libreria .NET: ti servirà per gestire le operazioni di Excel. Scaricalo da[Qui](https://releases.aspose.com/cells/net/).
3. Ambiente di sviluppo .NET: uno strumento come Visual Studio è perfetto per la codifica.
4. File Excel: tieni pronto un file Excel con i dati che vuoi esportare.

 Se non hai le librerie Aspose.PDF e Aspose.Cells, puoi iniziare con una[prova gratuita](https://releases.aspose.com/).

## Importa pacchetti

Per iniziare, assicurati di aver installato entrambe le librerie Aspose.PDF e Aspose.Cells nel tuo progetto. Puoi installarle usando NuGet Package Manager in Visual Studio.

Ecco come importare i pacchetti necessari nel codice C#:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Ora che abbiamo impostato i prerequisiti, vediamo come esportare i dati da un foglio Excel a una tabella in un documento PDF.

## Passaggio 1: caricare la cartella di lavoro di Excel

Per iniziare, devi caricare la tua cartella di lavoro Excel nel programma. In questo passaggio, useremo Aspose.Cells per aprire il file Excel.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Caricare la cartella di lavoro di Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Spiegazione: Qui specifichiamo il percorso della directory in cui si trova il nostro file Excel e carichiamo la cartella di lavoro utilizzando`Aspose.Cells.Workbook` Assicurati di regolare`"YOUR DOCUMENT DIRECTORY"` per indicare la posizione del file.

## Passaggio 2: accedi al primo foglio di lavoro

Dopo aver caricato la cartella di lavoro, dobbiamo accedere al primo foglio di lavoro in cui sono memorizzati i nostri dati.

```csharp
// Accesso al primo foglio di lavoro nel file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Spiegazione: questo passaggio è semplice: prendiamo il primo foglio di lavoro dalla cartella di lavoro, che contiene i dati da esportare.

## Passaggio 3: esportare i dati in DataTable

Ora esportiamo i dati dal foglio Excel in un oggetto DataTable, che fungerà da intermediario per il trasferimento dei dati al PDF.

```csharp
// Esportazione del contenuto di 7 righe e 2 colonne a partire dalla 1a cella in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Spiegazione: Il`ExportDataTable` metodo estrae i dati a partire dalla prima cella del foglio di lavoro e si estende su tutte le righe e le colonne. Questi dati vengono quindi memorizzati in un`DataTable` per un ulteriore utilizzo.

## Passaggio 4: creare un nuovo documento PDF

Successivamente, dobbiamo creare un nuovo documento PDF utilizzando Aspose.PDF.

```csharp
// Crea un'istanza di Documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crea una pagina nell'istanza del documento
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Spiegazione: qui inizializziamo un nuovo`Aspose.Pdf.Document` aggiungi una pagina. Questa pagina conterrà più avanti la tabella che stiamo creando dai dati di Excel.

## Passaggio 5: creare un oggetto tabella in PDF

Passiamo alla creazione di una tabella all'interno del documento PDF.

```csharp
// Crea un oggetto Tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Aggiungere l'oggetto Tabella alla raccolta dei paragrafi della pagina
page.Paragraphs.Add(table);
```

 Spiegazione: Creiamo un`Aspose.Pdf.Table` e aggiungerlo alla raccolta dei paragrafi della pagina, il che garantisce che la tabella venga visualizzata sulla pagina.

## Passaggio 6: impostare la larghezza e i bordi delle colonne

Le tabelle in PDF necessitano di larghezze di colonna definite. Aggiungeremo anche dei bordi per rendere la tabella più leggibile.

```csharp
// Imposta la larghezza delle colonne della tabella
table.ColumnWidths = "40 100 100";

// Imposta il bordo predefinito della cella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Spiegazione: Impostiamo le larghezze delle tre colonne e diamo a tutte le celle un bordo predefinito con uno spessore di`0.1F`.

## Passaggio 7: importare i dati da DataTable nella tabella PDF

Adesso è il momento di importare i dati dalla DataTable nella nostra tabella PDF.

```csharp
// Importare i dati nell'oggetto Tabella da DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Spiegazione: Il`ImportDataTable`metodo trasferisce tutti i dati dal`DataTable` alla tabella PDF. Questo popola la tabella con i dati dal tuo foglio Excel.

## Passaggio 8: definire lo stile della riga di intestazione

Modifichiamo lo stile della riga di intestazione della tabella modificando il colore di sfondo, il carattere e l'allineamento.

```csharp
// Prendi la prima riga dalla tabella
Aspose.Pdf.Row headerRow = table.Rows[0];

// Imposta lo stile per la riga dell'intestazione
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Spiegazione: Eseguiamo un ciclo su tutte le celle nella prima riga (intestazione), impostiamo il colore di sfondo su blu, il colore del testo su giallo e allineiamo il testo al centro.

## Passaggio 9: Definisci lo stile delle righe rimanenti

Per differenziare l'intestazione dal resto delle righe, aggiungiamo uno stile diverso per le righe rimanenti.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Spiegazione: per tutte le righe, eccetto l'intestazione, impostiamo uno sfondo grigio e il colore del testo bianco.

## Passaggio 10: Salvare il documento PDF

Infine, salva il documento PDF con la tabella.

```csharp
// Salva il PDF
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Spiegazione: salviamo il PDF nella directory specificata. Voilà! I tuoi dati Excel sono ora all'interno di una tabella PDF splendidamente formattata.

## Conclusione

Ed ecco fatto! In pochi passaggi, hai esportato dati da un foglio di lavoro Excel in una tabella all'interno di un PDF utilizzando Aspose.PDF per .NET. Suddividendo il processo e assegnandogli uno stile lungo il percorso, puoi personalizzare il tuo output e garantire che i tuoi dati appaiano puliti e professionali. Quindi la prossima volta che qualcuno ti porge un file Excel e ti chiede un report PDF, saprai esattamente cosa fare.

## Domande frequenti

### Posso personalizzare ulteriormente la tabella?
Assolutamente! Puoi modificare colori, caratteri, allineamento e persino aggiungere bordi a celle specifiche.

### Aspose.PDF per .NET è gratuito?
 Offre una prova gratuita, ma per un uso prolungato, avrai bisogno di una licenza. Puoi[compralo qui](https://purchase.aspose.com/buy).

### Posso esportare solo righe e colonne specifiche?
 Sì, puoi modificare i parametri in`ExportDataTable` metodo per esportare intervalli specifici.

### Funziona anche con file Excel di grandi dimensioni?
Sì, Aspose.Cells è progettato per gestire in modo efficiente file Excel di grandi dimensioni.

### Come posso aggiungere altre pagine al PDF?
 Puoi usare`pdfDocument.Pages.Add()` per aggiungere tutte le pagine di cui hai bisogno.