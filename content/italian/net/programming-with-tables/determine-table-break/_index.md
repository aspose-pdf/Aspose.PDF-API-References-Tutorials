---
title: Determina l'interruzione della tabella nel file PDF
linktitle: Determina l'interruzione della tabella nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come determinare le interruzioni di tabella nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 60
url: /it/net/programming-with-tables/determine-table-break/
---
In questo tutorial impareremo come determinare le interruzioni di tabella nel file PDF utilizzando Aspose.PDF per .NET. Spiegheremo passo dopo passo il codice sorgente in C#. Alla fine di questo tutorial, saprai come determinare se una tabella supera i margini della pagina. Iniziamo!

## Passaggio 1: configurazione dell'ambiente
Innanzitutto, assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa gli spazi dei nomi necessari.

## Passaggio 2: creazione del documento PDF
 In questo passaggio ne creiamo uno nuovo`Document` oggetto per rappresentare il documento PDF.

```csharp
pdf-Document = new Document();
```

Questo documento verrà utilizzato per aggiungere sezioni e tabelle.

## Passaggio 3: aggiunta di una sezione e di una tabella
Ora aggiungeremo una sezione al nostro documento PDF e creeremo una tabella all'interno di questa sezione.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Specifichiamo inoltre un margine superiore di 300 punti per la tabella. Puoi regolare questo valore in base alle tue esigenze.

## Passaggio 4: impostazione della tabella
In questo passaggio configuriamo le proprietà della tabella, come la larghezza e i bordi delle colonne.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Qui definiamo la larghezza delle colonne della tabella e dei bordi delle celle. Puoi regolare questi valori in base alle tue preferenze.

## Passaggio 5: aggiungi righe e celle alla tabella
Ora creeremo righe e celle nella tabella utilizzando un loop.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Qui creiamo 17 righe nella tabella e aggiungiamo tre celle a ciascuna riga. Puoi regolare la fibbia in base alle tue esigenze.

## Passaggio 6: determinare le interruzioni della tabella
Ora determineremo se la tabella supera i margini della pagina confrontando l'altezza della pagina con l'altezza totale degli oggetti nella tabella.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Calcoliamo l'altezza della pagina e l'altezza totale degli oggetti tenendo conto dei margini. Se la differenza è pari o inferiore a 10, la tabella supera i margini della pagina.

## Passaggio 7: salvataggio del documento PDF
Infine, salviamo il documento PDF con i risultati.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Assicurati di specificare la directory dei documenti corretta. Il file PDF risultante verrà salvato con le interruzioni di tabella determinate.

### Codice sorgente di esempio per Determinare interruzione tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare una classe PDF oggetto
Document pdf = new Document();
// Aggiungi la sezione alla raccolta di sezioni di documenti PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Istanziare un oggetto tabella
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Aggiungi la tabella nella raccolta paragrafi della sezione desiderata
page.Paragraphs.Add(table1);
// Impostato con la larghezza delle colonne della tabella
table1.ColumnWidths = "100 100 100";
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crea un oggetto MarginInfo e imposta i margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Imposta il riempimento cella predefinito sull'oggetto MarginInfo
table1.DefaultCellPadding = margin;
// Se aumenti il contatore a 17, il tavolo si romperà
// Perché non può più essere ospitato su questa pagina
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
// Margine superiore della tabella e altezza della tabella.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Visualizza altezza pagina, altezza tabella, margine superiore tabella e parte superiore pagina
// E informazioni sul margine inferiore
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Controlla se deduciamo la somma del margine superiore della pagina + margine inferiore della pagina
// + Margine superiore della tabella e altezza della tabella dall'altezza della pagina e inferiore
// Di 10 (una riga media può essere maggiore di 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Se il valore è inferiore a 10, visualizza il messaggio.
	//Il che dimostra che un'altra riga non può essere posizionata e se ne aggiungiamo una nuova
	// Riga, la tabella si romperà. Dipende dal valore dell'altezza della riga.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Salvare il documento pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come determinare le interruzioni di tabella in un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questa guida passo passo per verificare se una tabella supera i margini della pagina nei tuoi progetti C#.

### Domande frequenti per determinare l'interruzione della tabella nel file PDF

#### D: Qual è lo scopo di determinare le interruzioni di tabella in un documento PDF?

R: Lo scopo di determinare le interruzioni di tabella in un documento PDF è verificare se la tabella supera i margini della pagina. Ciò garantisce che il contenuto della tabella venga visualizzato correttamente nello spazio disponibile della pagina. Rilevando le interruzioni della tabella, puoi gestire l'overflow del contenuto e regolare di conseguenza il layout della tabella.

#### D: Come posso modificare il margine superiore della tabella?

 R: Nel codice sorgente C# fornito, puoi regolare il margine superiore della tabella modificando il valore di`table1.Margin.Top`proprietà. Aumenta o diminuisci il valore secondo necessità per impostare il margine superiore desiderato per la tabella.

#### D: Posso personalizzare l'aspetto della tabella, ad esempio i colori delle celle e la dimensione del carattere?

R: Sì, puoi personalizzare l'aspetto della tabella e delle sue celle utilizzando varie proprietà e metodi forniti da Aspose.PDF per .NET. Ad esempio, puoi modificare i colori dello sfondo della cella, la dimensione del carattere, la famiglia dei caratteri, l'allineamento del testo e altro ancora. Fare riferimento alla documentazione ufficiale per ulteriori informazioni su come personalizzare l'aspetto della tabella.

#### D: Cosa succede se la tabella supera i margini della pagina?

R: Se la tabella supera i margini della pagina, il contenuto potrebbe essere troncato o sovrapposto, rendendo il documento PDF meno leggibile e organizzato. Rilevando le interruzioni di tabella e gestendo l'overflow, puoi garantire che il contenuto rimanga visualizzato correttamente nell'area disponibile della pagina.

#### D: Posso determinare le interruzioni di tabella per più tabelle nello stesso documento PDF?

R: Sì, puoi determinare le interruzioni di tabella per più tabelle nello stesso documento PDF. Ripeti semplicemente i passaggi per ogni tabella che desideri analizzare e regola il layout della tabella secondo necessità per evitare l'overflow del contenuto.