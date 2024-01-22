---
title: Allineamento del testo per il contenuto della riga della tabella
linktitle: Allineamento del testo per il contenuto della riga della tabella
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come allineare il contenuto della riga in una tabella PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 210
url: /it/net/programming-with-tables/text-alignment-for-table-row-content/
---
In questo tutorial, ti guideremo passo dopo passo per allineare il contenuto di una riga in una tabella di un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: creazione del documento PDF
Per prima cosa creeremo il documento PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Passaggio 2: inizializzazione della tabella
Successivamente, inizializzeremo la tabella:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Passaggio 3: impostazione del colore del bordo della tabella
Configureremo il colore del bordo della tabella:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Passaggio 4: configurazione del bordo della cella della tabella
Configureremo il bordo della cella della tabella:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Passaggio 5: esegui il loop per aggiungere 10 righe alla tabella
Utilizzeremo ora un ciclo per aggiungere 10 righe alla tabella:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Passaggio 6: configurazione dell'allineamento della linea verticale
Andiamo a configurare l'allineamento verticale delle righe della tabella:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Passaggio 7: aggiunta di contenuto alle celle della riga
Aggiungeremo contenuto alle celle della riga:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Passaggio 8: aggiunta della tabella alla pagina del documento
Ora aggiungiamo la tabella alla pagina del documento:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Passaggio 9: salvataggio del documento PDF
Infine, salveremo il documento PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Codice sorgente di esempio per l'allineamento del testo per il contenuto delle righe della tabella utilizzando Aspose.PDF per .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inizializza una nuova istanza della tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta il colore del bordo della tabella come Grigio chiaro
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// imposta il bordo per le celle della tabella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// crea un ciclo per aggiungere 10 righe
for (int row_count = 0; row_count < 10; row_count++)
{
	// aggiungi riga alla tabella
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Aggiungi oggetto tabella alla prima pagina del documento di input
tocPage.Paragraphs.Add(table);
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusione
Congratulazioni! Ora hai imparato come allineare il contenuto di una riga in una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come creare un documento, inizializzare una tabella, configurare il bordo e l'allineamento, aggiungere contenuto e salvare il documento PDF. Ora puoi applicare questa conoscenza ai tuoi progetti.

### Domande frequenti

#### D: Come posso allineare orizzontalmente il contenuto delle celle della tabella?

 R: Puoi allineare orizzontalmente il contenuto delle celle della tabella impostando il`HorizontalAlign` proprietà della cellula`TextState` oggetto. Ad esempio, per allineare al centro il testo, utilizzare`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Puoi anche impostarlo su`HorizontalAlignment.Left` O`HorizontalAlignment.Right` rispettivamente per l'allineamento a sinistra e a destra.

#### D: Posso applicare stili e colori dei bordi diversi alle singole celle della tabella?

 R: Sì, puoi applicare diversi stili e colori dei bordi alle singole celle della tabella. Per personalizzare il bordo per una cella specifica, impostare il`cell.Border` proprietà a una nuova`BorderInfo`oggetto con le impostazioni desiderate, ad esempio lati del bordo, larghezza e colore.

#### D: Come posso regolare l'allineamento verticale del contenuto della tabella all'interno delle celle?

 R: Puoi regolare l'allineamento verticale del contenuto della tabella all'interno delle celle impostando il`VerticalAlignment` proprietà della riga a`VerticalAlignment.Center`, `VerticalAlignment.Top` , O`VerticalAlignment.Bottom`. Questa proprietà controlla l'allineamento verticale di tutte le celle in quella riga.

#### D: È possibile aggiungere più colonne o righe alla tabella in modo dinamico?

 R: Sì, puoi aggiungere più colonne e righe alla tabella in modo dinamico utilizzando il file`table.Rows.Add()` metodo per aggiungere nuove righe e il`row.Cells.Add()` metodo per aggiungere nuove celle alle righe. Puoi farlo all'interno dei cicli o in base ai tuoi requisiti specifici.

#### D: Come posso impostare un colore di sfondo per celle specifiche o per l'intera tabella?

 R: Per impostare un colore di sfondo per celle specifiche o per l'intera tabella, utilizzare`BackgroundColor` proprietà del`Cell` O`Table` oggetto. Ad esempio, per impostare il colore di sfondo di una cella, utilizzare`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.