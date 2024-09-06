---
title: Elemento della tabella di stile
linktitle: Elemento della tabella di stile
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come formattare gli elementi della tabella con Aspose.PDF per .NET. Guida passo passo per personalizzare stili e proprietà.
type: docs
weight: 170
url: /it/net/programming-with-tagged-pdf/style-table-element/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per formattare l'elemento array utilizzando Aspose.PDF per .NET. Segui le istruzioni sottostanti per capire come personalizzare gli stili e le proprietà dell'elemento array.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per usare Aspose.PDF per .NET. Ciò include l'installazione della libreria Aspose.PDF e la configurazione del tuo progetto per farvi riferimento.

## Fase 2: Creazione di un documento

In questo passaggio creeremo un nuovo oggetto documento Aspose.PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua.

## Fase 3: Ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento struttura radice per il nostro documento.

```csharp
//Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto l'elemento della struttura radice che fungerà da contenitore per l'elemento array.

## Fase 4: Creazione dell'elemento della struttura array

Ora creiamo un nuovo elemento di struttura tabella per il nostro documento.

```csharp
// Crea l'elemento della struttura array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Abbiamo creato un nuovo elemento della struttura array e lo abbiamo aggiunto all'elemento della struttura radice.

## Passaggio 5: personalizzazione degli stili e delle proprietà degli elementi dell'array

In questa fase personalizzeremo gli stili e le proprietà dell'elemento array.

```csharp
// Personalizza gli stili e le proprietà dell'elemento array
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Personalizza lo stile delle linee ripetute
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Abbiamo utilizzato varie proprietà per personalizzare l'elemento della tabella, come il colore di sfondo, i bordi, l'allineamento, lo stile predefinito delle celle, i margini, la larghezza delle colonne, ecc.

## Passaggio 6: aggiungere intestazioni, corpo e piè di pagina della tabella

Aggiungiamo ora le intestazioni, il corpo e il piè di pagina della tabella all'elemento tabella.
```csharp
// Aggiungere intestazioni di tabella
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Numero di righe e colonne nella tabella
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Crea la riga dell'intestazione della tabella
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Aggiungere le righe del corpo della tabella
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Aggiungere la riga di fondo della tabella
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Abbiamo aggiunto le intestazioni, le righe del corpo e la riga del piè di pagina alla tabella utilizzando gli elementi corrispondenti.

## Passaggio 7: salvataggio del documento PDF taggato

Ora che abbiamo creato il nostro documento con l'elemento tabella formattato, lo salveremo come documento PDF con tag.

```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableElement.pdf");
```

Abbiamo salvato il documento PDF taggato nella directory specificata.

## Fase 8: convalida della conformità PDF/UA

Successivamente valideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF taggato e ne abbiamo convalidato la conformità PDF/UA generando un report XML.

### Esempio di codice sorgente per Style Table Element utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea elemento struttura tabella
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableElement.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come formattare l'elemento array con Aspose.PDF per .NET. Abbiamo personalizzato gli stili e le proprietà dell'elemento tabella, aggiunto intestazioni, righe del corpo e un piè di pagina, salvato il documento PDF taggato e convalidato la sua conformità PDF/UA.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial sulla formattazione degli elementi dell'array utilizzando Aspose.PDF per .NET?

R: L'obiettivo di questo tutorial è guidarti attraverso il processo di formattazione dell'elemento array in un documento PDF utilizzando Aspose.PDF per .NET. Fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a personalizzare gli stili e le proprietà dell'elemento array.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo per usare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del tuo progetto per farvi riferimento.

#### D: Come posso creare un nuovo documento PDF e impostarne il titolo e la lingua utilizzando Aspose.PDF per .NET?

 A: Per creare un nuovo documento PDF, è necessario creare un`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito dal tutorial dimostra come creare un documento e impostarne le proprietà titolo e lingua.

#### D: Qual è il significato dell'elemento struttura radice in un documento PDF?

A: L'elemento struttura radice funge da contenitore per altri elementi struttura, aiutando a organizzare e categorizzare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare e personalizzare un elemento di struttura array utilizzando Aspose.PDF per .NET?

 A: È possibile creare un elemento di struttura array utilizzando`CreateTableElement()` metodo. Il codice sorgente del tutorial fornisce esempi di personalizzazione di varie proprietà dell'elemento tabella, come colore di sfondo, bordi, allineamento, larghezza delle colonne e altro.

#### D: Posso personalizzare gli stili e le proprietà delle celle della tabella all'interno dell'elemento array?

R: Sì, il tutorial spiega come personalizzare gli stili e le proprietà dell'intero elemento della tabella, inclusi intestazioni, righe del corpo e piè di pagina. Tuttavia, non affronta specificamente la personalizzazione delle singole celle della tabella.

#### D: Come posso aggiungere intestazioni, righe del corpo e un piè di pagina all'elemento tabella?

R: Il tutorial spiega come creare e aggiungere intestazioni, righe del corpo e un piè di pagina all'elemento tabella utilizzando i metodi appropriati forniti da Aspose.PDF per .NET.

#### D: Che cos'è la conformità PDF/UA e come posso convalidarla per il mio documento PDF taggato?

 A: La conformità PDF/UA assicura che il documento PDF sia conforme agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial mostra come convalidare la conformità PDF/UA utilizzando`Validate()` metodo e generare un report di conformità XML.

#### D: Come posso integrare questi concetti nelle mie applicazioni .NET?

R: Puoi usare gli esempi di codice sorgente C# forniti come guida per implementare la formattazione degli elementi array nelle tue applicazioni .NET. Modifica e adatta il codice per adattarlo ai tuoi requisiti e integralo nei tuoi progetti.

#### D: Esistono delle buone pratiche consigliate per la formattazione degli elementi array nei documenti PDF?

A: Quando formatti gli elementi di array (tabelle), considera la leggibilità e l'accessibilità del contenuto. Utilizza font chiari e leggibili, colori appropriati e mantieni un layout coerente. Convalida la conformità PDF/UA per garantire che gli standard di accessibilità siano rispettati.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la personalizzazione dei documenti PDF?

R: Aspose.PDF per .NET offre una gamma di funzionalità per la personalizzazione dei documenti PDF, tra cui manipolazione del testo, inserimento di immagini, gestione dei campi dei moduli, firme digitali, annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per esplorare funzionalità aggiuntive.