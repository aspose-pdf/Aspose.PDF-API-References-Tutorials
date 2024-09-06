---
title: Determinare l'interruzione della tabella nel file PDF
linktitle: Determinare l'interruzione della tabella nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come determinare le interruzioni di tabella nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-tables/determine-table-break/
---
In questo tutorial, impareremo come determinare le interruzioni di tabella in un file PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come determinare se una tabella supera i margini di pagina. Iniziamo!

## Fase 1: Impostazione dell'ambiente
Per prima cosa, assicurati di aver impostato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa i namespace necessari.

## Fase 2: Creazione del documento PDF
 In questo passaggio creiamo un nuovo`Document` oggetto per rappresentare il documento PDF.

```csharp
pdf-Document = new Document();
```

Questo documento verrà utilizzato per aggiungere sezioni e tabelle.

## Passaggio 3: aggiunta di una sezione e di una tabella
Adesso aggiungeremo una sezione al nostro documento PDF e creeremo una tabella al suo interno.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Specifichiamo anche un margine massimo di 300 punti per la tabella. Puoi adattare questo valore in base alle tue esigenze.

## Fase 4: Impostazione del tavolo
In questa fase configuriamo le proprietà della tabella, come la larghezza delle colonne e i bordi.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Qui definiamo la larghezza delle colonne della tabella e i bordi delle celle. Puoi regolare questi valori in base alle tue preferenze.

## Passaggio 5: aggiungere righe e celle alla tabella
Ora creeremo righe e celle nella tabella utilizzando un ciclo.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Qui creiamo 17 righe nella tabella e aggiungiamo tre celle a ogni riga. Puoi regolare la fibbia in base alle tue esigenze.

## Fase 6: Determinazione delle interruzioni di tabella
Ora determineremo se la tabella supera i margini della pagina confrontando l'altezza della pagina con l'altezza totale degli oggetti nella tabella.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Calcoliamo l'altezza della pagina e l'altezza totale degli oggetti tenendo conto dei margini. Se la differenza è 10 o meno, la tabella supera i margini della pagina.

## Passaggio 7: Salvataggio del documento PDF
Infine, salviamo il documento PDF con i risultati.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Assicuratevi di specificare la directory corretta del documento. Il file PDF risultante verrà salvato con le interruzioni di tabella determinate.

### Esempio di codice sorgente per Determina interruzione tabella utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di una classe PDF di oggetti
Document pdf = new Document();
// Aggiungere la sezione alla raccolta di sezioni del documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
page.Paragraphs.Add(table1);
// Impostato con le larghezze delle colonne della tabella
table1.ColumnWidths = "100 100 100";
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crea l'oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
table1.DefaultCellPadding = margin;
// Se aumenti il contatore a 17, il tavolo si romperà
// Poiché non può essere più ospitato su questa pagina
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Crea righe nella tabella e poi celle nelle righe
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Ottieni le informazioni sull'altezza della pagina
float PageHeight = (float)pdf.PageInfo.Height;
// Ottieni le informazioni sull'altezza totale del margine superiore e inferiore della pagina,
// Margine del piano del tavolo e altezza del tavolo.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Visualizza altezza pagina, altezza tabella, margine superiore tabella e parte superiore pagina
// E informazioni sul margine inferiore
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Controlla se deduciamo la somma del margine superiore della pagina + margine inferiore della pagina
// + Margine superiore della tabella e altezza della tabella da Altezza della pagina e il suo valore inferiore
// Di 10 (una riga media può essere maggiore di 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Se il valore è inferiore a 10, visualizza il messaggio.
	//Il che dimostra che non è possibile posizionare un'altra riga e se ne aggiungiamo una nuova
	// Riga, la tabella si interromperà. Dipende dal valore dell'altezza della riga.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Salva il documento pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come determinare le interruzioni di tabella in un documento PDF usando Aspose.PDF per .NET. Puoi usare questa guida passo passo per controllare se una tabella supera i margini di pagina nei tuoi progetti C#.

### Domande frequenti per determinare l'interruzione di tabella nel file PDF

#### D: Qual è lo scopo di determinare le interruzioni di tabella in un documento PDF?

R: Lo scopo della determinazione delle interruzioni di tabella in un documento PDF è di controllare se la tabella supera i margini di pagina. Ciò garantisce che il contenuto della tabella venga visualizzato correttamente all'interno dello spazio di pagina disponibile. Rilevando le interruzioni di tabella, puoi gestire l'overflow di contenuto e adattare di conseguenza il layout della tabella.

#### D: Come posso modificare il margine superiore della tabella?

 A: Nel codice sorgente C# fornito, è possibile regolare il margine superiore della tabella modificando il valore di`table1.Margin.Top`proprietà. Aumentare o diminuire il valore come necessario per impostare il margine superiore desiderato per la tabella.

#### D: Posso personalizzare l'aspetto della tabella, ad esempio i colori delle celle e la dimensione del carattere?

R: Sì, puoi personalizzare l'aspetto della tabella e delle sue celle utilizzando varie proprietà e metodi forniti da Aspose.PDF per .NET. Ad esempio, puoi modificare i colori di sfondo delle celle, la dimensione del carattere, la famiglia di caratteri, l'allineamento del testo e altro ancora. Fai riferimento alla documentazione ufficiale per maggiori informazioni su come personalizzare l'aspetto della tabella.

#### D: Cosa succede se la tabella supera i margini della pagina?

R: Se la tabella supera i margini della pagina, potrebbe causare il troncamento o la sovrapposizione del contenuto, rendendo il documento PDF meno leggibile e organizzato. Rilevando le interruzioni di tabella e gestendo l'overflow, puoi assicurarti che il contenuto rimanga visualizzato correttamente nell'area di pagina disponibile.

#### D: Posso stabilire interruzioni di tabella per più tabelle nello stesso documento PDF?

R: Sì, puoi determinare le interruzioni di tabella per più tabelle nello stesso documento PDF. Ripeti semplicemente i passaggi per ogni tabella che vuoi analizzare e modifica il layout della tabella come necessario per evitare l'overflow di contenuto.