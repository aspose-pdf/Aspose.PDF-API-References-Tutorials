---
title: Tabella di rendering nel documento PDF
linktitle: Tabella di rendering nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come visualizzare una tabella in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 170
url: /it/net/programming-with-tables/render-table/
---
In questo tutorial, ti guideremo passo dopo passo per visualizzare una tabella in un documento PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Fase 1: Creazione del documento
Per prima cosa creeremo un nuovo documento PDF:

```csharp
// Percorso alla directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un nuovo documento
Document doc = new Document();
```

## Passaggio 2: configurazione dei margini e dell'orientamento della pagina
Successivamente, configureremo i margini della pagina e imposteremo l'orientamento in modalità orizzontale:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Fase 3: Creazione della tabella e delle colonne
Ora creiamo una tabella e impostiamo la larghezza delle colonne:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Passaggio 4: aggiungere righe e celle alla tabella
Successivamente aggiungeremo righe e celle alla tabella utilizzando un ciclo:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Passaggio 5: aggiunta della tabella alla pagina
Aggiungiamo ora la tabella alla pagina del documento:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Fase 6: Visualizzazione della tabella su una nuova pagina
Successivamente, creeremo una nuova tabella e imposteremo la proprietà "IsInNewPage" su "true" per visualizzare la tabella su una nuova pagina:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Passaggio 7: Salva PDF
Infine, salviamo il documento PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Esempio di codice sorgente per Render Table utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Pagina aggiunta.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Vorrei che la tabella 1 venisse pubblicata nella pagina successiva, per favore...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusione
Congratulazioni! Ora hai imparato come visualizzare una tabella in un documento PDF usando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come creare un documento, configurare i margini e l'orientamento della pagina, aggiungere una tabella e visualizzare una tabella su una nuova pagina. Ora puoi applicare questa conoscenza ai tuoi progetti.

### Domande frequenti sulla tabella di rendering nel documento PDF

#### D: Come posso modificare l'aspetto della tabella, ad esempio cambiando i colori delle celle o aggiungendo bordi?

 A: Per modificare l'aspetto della tabella, è possibile impostare varie proprietà della`Aspose.Pdf.Table` e le sue celle. Ad esempio, puoi impostare`BackgroundColor` proprietà delle celle per cambiare il loro colore di sfondo. Puoi anche impostare la`Border` proprietà della tabella o delle singole celle per aggiungere bordi. Inoltre, puoi personalizzare il font, il colore del testo e l'allineamento del contenuto della tabella modificando il`TextState` del`TextFragment` oggetti aggiunti alle celle.

#### D: Posso aggiungere intestazioni o piè di pagina alla tabella?

R: Sì, puoi aggiungere intestazioni o piè di pagina alla tabella creando righe aggiuntive all'inizio o alla fine della tabella e impostando il contenuto appropriato nelle celle. Puoi personalizzare le intestazioni o i piè di pagina indipendentemente dal resto del contenuto della tabella aggiungendo stili o contenuti diversi a queste righe specifiche.

#### D: Come posso controllare la posizione della tabella sulla pagina?

A: Per controllare la posizione della tabella sulla pagina, puoi regolare il`MarginInfo` del`PageInfo` oggetto. Il`MarginInfo` consente di impostare i margini sinistro, destro, superiore e inferiore della pagina, il che influisce sullo spazio disponibile per la tabella. È inoltre possibile utilizzare`PositioningType` proprietà del`Aspose.Pdf.Table` per controllare l'allineamento orizzontale e verticale all'interno dell'area del contenuto della pagina.

#### D: Posso esportare la tabella in formati di file diversi, come Excel o CSV?

R: Aspose.PDF per .NET è progettato principalmente per lavorare con documenti PDF. Sebbene possa esportare il documento PDF come immagine o XPS, non supporta direttamente l'esportazione di tabelle in formati come Excel o CSV. Per esportare i dati della tabella in formati di file diversi, potrebbe essere necessario utilizzare librerie o metodi aggiuntivi per convertire il contenuto PDF nel formato desiderato.

#### D: Come posso aggiungere collegamenti ipertestuali alle celle della tabella?

 A: Per aggiungere collegamenti ipertestuali alle celle della tabella, puoi utilizzare`Aspose.Pdf.WebHyperlink` classe per creare un collegamento ipertestuale e quindi aggiungerlo come ancoraggio al`TextFragment`all'interno della cella. Ciò consente di associare un URL o un link target a un testo o contenuto specifico all'interno della cella, creando collegamenti ipertestuali cliccabili.