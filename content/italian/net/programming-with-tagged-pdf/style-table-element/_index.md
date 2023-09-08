---
title: Elemento della tabella di stile
linktitle: Elemento della tabella di stile
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come formattare l'elemento tabella con Aspose.PDF per .NET. Guida passo passo per personalizzare stili e proprietà.
type: docs
weight: 170
url: /it/net/programming-with-tagged-pdf/style-table-element/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per formattare l'elemento dell'array utilizzando Aspose.PDF per .NET. Segui le istruzioni seguenti per capire come personalizzare gli stili e le proprietà dell'elemento dell'array.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò include l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

## Passaggio 2: creazione di un documento

In questo passaggio, creeremo un nuovo oggetto documento Aspose.PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua del documento.

## Passaggio 3: ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento della struttura radice per il nostro documento.

```csharp
//Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto l'elemento della struttura root che servirà da contenitore per l'elemento dell'array.

## Passaggio 4: creazione dell'elemento della struttura dell'array

Ora creiamo un nuovo elemento della struttura della tabella per il nostro documento.

```csharp
// Creare l'elemento della struttura dell'array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Abbiamo creato un nuovo elemento della struttura dell'array e lo abbiamo aggiunto all'elemento della struttura root.

## Passaggio 5: personalizzazione degli stili e delle proprietà degli elementi dell'array

In questo passaggio personalizzeremo gli stili e le proprietà dell'elemento dell'array.

```csharp
// Personalizza gli stili e le proprietà dell'elemento dell'array
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

Abbiamo utilizzato varie proprietà per personalizzare l'elemento della tabella, come colore di sfondo, bordi, allineamento, stile predefinito della cella, margini, larghezza della colonna, ecc.

## Passaggio 6: aggiungi intestazioni, corpo e piè di pagina della tabella

Ora aggiungiamo le intestazioni, il corpo e il piè di pagina della tabella all'elemento tabella.
```csharp
// Aggiungi intestazioni di tabella
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Numero di righe e colonne nella tabella
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Crea la riga di intestazione della tabella
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Aggiungi le righe del corpo della tabella
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

// Aggiungi la linea di fondo della tabella
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Abbiamo aggiunto le intestazioni, le righe del corpo e la riga del piè di pagina alla tabella utilizzando gli elementi corrispondenti.

## Passaggio 7: salvataggio del documento PDF contrassegnato

Ora che abbiamo creato il nostro documento con l'elemento tabella con stile, lo salveremo come documento PDF con tag.

```csharp
// Salva il documento PDF contrassegnato
document.Save(dataDir + "StyleTableElement.pdf");
```

Abbiamo salvato il documento PDF contrassegnato nella directory specificata.

## Passaggio 8: convalida della conformità PDF/UA

Successivamente, convalideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF con tag e ne abbiamo convalidato la conformità PDF/UA generando un report XML.

### Codice sorgente di esempio per l'elemento della tabella di stile utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea un elemento della struttura della tabella
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

// Salva documento PDF contrassegnato
document.Save(dataDir + "StyleTableElement.pdf");

// Verifica della conformità PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come formattare l'elemento dell'array con Aspose.PDF per .NET. Abbiamo personalizzato gli stili e le proprietà dell'elemento tabella, aggiunto intestazioni, righe del corpo e un piè di pagina, salvato il documento PDF con tag e convalidato la sua conformità PDF/UA.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial sulla formattazione dell'elemento dell'array utilizzando Aspose.PDF per .NET?

R: L'obiettivo di questo tutorial è guidarti attraverso il processo di formattazione dell'elemento array in un documento PDF utilizzando Aspose.PDF per .NET. Fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a personalizzare gli stili e le proprietà dell'elemento dell'array.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

#### D: Come posso creare un nuovo documento PDF e impostarne il titolo e la lingua utilizzando Aspose.PDF per .NET?

 R: Per creare un nuovo documento PDF, è necessario creare un file`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito nell'esercitazione illustra come creare un documento e impostarne il titolo e le proprietà della lingua.

#### D: Qual è il significato dell'elemento della struttura radice in un documento PDF?

R: L'elemento della struttura radice funge da contenitore per altri elementi della struttura, aiutando a organizzare e classificare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare e personalizzare un elemento della struttura dell'array utilizzando Aspose.PDF per .NET?

 R: Puoi creare un elemento della struttura dell'array utilizzando il comando`CreateTableElement()` metodo. Il codice sorgente del tutorial fornisce esempi di personalizzazione di varie proprietà dell'elemento tabella, come colore di sfondo, bordi, allineamento, larghezza della colonna e altro.

#### D: Posso personalizzare gli stili e le proprietà delle celle della tabella all'interno dell'elemento dell'array?

R: Sì, il tutorial spiega come personalizzare gli stili e le proprietà dell'intero elemento della tabella, incluse intestazioni, righe del corpo e piè di pagina. Tuttavia, non affronta specificamente la personalizzazione delle singole celle della tabella.

#### D: Come posso aggiungere intestazioni, righe del corpo e piè di pagina all'elemento tabella?

R: Il tutorial spiega come creare e aggiungere intestazioni, righe di corpo e piè di pagina all'elemento tabella utilizzando i metodi appropriati forniti da Aspose.PDF per .NET.

#### D: Cos'è la conformità PDF/UA e come posso convalidarla per il mio documento PDF con tag?

 R: La conformità PDF/UA garantisce che il documento PDF sia conforme agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial dimostra come convalidare la conformità PDF/UA utilizzando il file`Validate()` metodo e generare un rapporto di conformità XML.

#### D: Come posso incorporare questi concetti nelle mie applicazioni .NET?

R: è possibile usare gli esempi di codice sorgente C# forniti come guida per implementare la formattazione degli elementi dell'array nelle proprie applicazioni .NET. Modifica e adatta il codice per soddisfare le tue esigenze e integralo nei tuoi progetti.

#### D: Esistono best practice consigliate per la formattazione degli elementi dell'array nei documenti PDF?

R: Quando si formattano gli elementi dell'array (tabelle), considerare la leggibilità e l'accessibilità del contenuto. Utilizza caratteri chiari e leggibili, colori appropriati e mantieni un layout coerente. Convalida la conformità PDF/UA per garantire il rispetto degli standard di accessibilità.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la personalizzazione dei documenti PDF?

R: Aspose.PDF per .NET offre una gamma di funzionalità per la personalizzazione dei documenti PDF, tra cui la manipolazione del testo, l'inserimento di immagini, la gestione dei campi del modulo, le firme digitali, le annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per esplorare funzionalità aggiuntive.