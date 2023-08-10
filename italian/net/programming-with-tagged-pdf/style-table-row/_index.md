---
title: Riga della tabella di stile
linktitle: Riga della tabella di stile
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come personalizzare le righe della tabella con Aspose.PDF per .NET guida passo passo allo stile e alla formattazione delle righe.
type: docs
weight: 180
url: /it/net/programming-with-tagged-pdf/style-table-row/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per formattare la riga della tabella utilizzando Aspose.PDF per .NET. Segui le istruzioni riportate di seguito per comprendere come personalizzare gli stili e le proprietà delle righe della tabella.

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
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua del documento.

## Passaggio 3: ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento della struttura radice per il nostro documento.

```csharp
//Ottenere l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo l'elemento della struttura radice che fungerà da contenitore per l'elemento dell'array.

## Passaggio 4: creazione dell'elemento della struttura dell'array

Ora creiamo un nuovo elemento della struttura della tabella per il nostro documento.

```csharp
// Creare l'elemento della struttura dell'array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Abbiamo creato un nuovo elemento della struttura dell'array e lo abbiamo aggiunto all'elemento della struttura principale.

## Passaggio 5: personalizzare gli stili e le proprietà delle righe della tabella

In questo passaggio, personalizzeremo gli stili e le proprietà delle righe della tabella.

```csharp
// Personalizza gli stili e le proprietà delle righe della tabella
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Personalizza le righe del corpo della tabella
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Crea la riga del piè di pagina della tabella
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Abbiamo personalizzato vari aspetti della riga della tabella, come il colore di sfondo, i bordi, l'altezza della riga, l'impaginazione, lo stile predefinito della cella e altro ancora.

## Passaggio 6: salvare il documento PDF con tag

Ora che abbiamo creato il nostro documento con la riga della tabella in stile, lo salveremo come documento PDF con tag.
```csharp
// Salva il documento PDF con tag
document.Save(dataDir + "StyleTableRow.pdf");
```

Abbiamo salvato il documento PDF con tag nella directory specificata.

## Passaggio 7: convalida della conformità PDF/UA

Successivamente, convalideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF con tag e ne abbiamo convalidato la conformità PDF/UA generando un rapporto XML.


### Esempio di codice sorgente per Style Table Row utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea un elemento della struttura della tabella
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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

// Salva documento PDF con tag
document.Save(dataDir + "StyleTableRow.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come formattare la riga della tabella con Aspose.PDF per .NET. Abbiamo personalizzato gli stili e le proprietà delle righe della tabella, aggiunto le intestazioni, le righe del corpo e il piè di pagina, salvato il documento PDF con tag e convalidato la sua conformità PDF/UA.

### FAQ

#### D: Qual è lo scopo di questo tutorial sulla formattazione delle righe della tabella utilizzando Aspose.PDF per .NET?

A: Lo scopo di questo tutorial è guidarti attraverso il processo di formattazione delle righe della tabella in un documento PDF utilizzando Aspose.PDF per .NET. Fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a personalizzare gli stili e le proprietà delle righe della tabella.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo per utilizzare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del progetto per farvi riferimento.

#### D: Come posso creare un nuovo documento PDF e impostarne il titolo e la lingua utilizzando Aspose.PDF per .NET?

 R: Per creare un nuovo documento PDF, devi creare un file`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito dall'esercitazione illustra come creare un documento e impostarne il titolo e le proprietà della lingua.

#### D: Qual è il significato dell'elemento della struttura radice in un documento PDF?

R: L'elemento della struttura principale funge da contenitore per altri elementi della struttura, contribuendo a organizzare e classificare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare e personalizzare un elemento della struttura della tabella per formattare le righe della tabella utilizzando Aspose.PDF per .NET?

R: Il tutorial spiega come creare un elemento della struttura della tabella e personalizzarne le proprietà per formattare le righe della tabella. Copre aspetti come il colore di sfondo, i bordi, l'altezza della riga, l'impaginazione, lo stile di cella predefinito e altro.

#### D: Posso personalizzare gli stili e le proprietà delle singole celle all'interno di una riga della tabella?

R: Sì, puoi personalizzare gli stili e le proprietà delle singole celle all'interno di una riga della tabella. L'esercitazione illustra come impostare proprietà come il colore di sfondo, i bordi, il colore del testo, la spaziatura interna e altro ancora per le celle della tabella all'interno della riga della tabella formattata.

#### D: Come posso aggiungere intestazioni, righe del corpo e un piè di pagina alla riga della tabella formattata?

R: Il tutorial fornisce esempi di creazione e aggiunta di intestazioni, righe del corpo e un piè di pagina all'elemento della struttura della tabella. Questi elementi possono essere ulteriormente personalizzati utilizzando le proprietà descritte nel tutorial.

#### D: Cos'è la conformità PDF/UA e come posso convalidarla per il mio documento PDF con tag?

 R: La conformità PDF/UA garantisce che il documento PDF sia conforme agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial dimostra come convalidare la conformità PDF/UA utilizzando il file`Validate()` metodo e generare un rapporto di conformità XML.

#### D: Come posso incorporare questi concetti nelle mie applicazioni .NET?

R: È possibile utilizzare gli esempi di codice sorgente C# forniti come guida per l'implementazione della formattazione delle righe della tabella nelle proprie applicazioni .NET. Modifica e adatta il codice alle tue esigenze e integralo nei tuoi progetti.

#### D: Esistono best practice consigliate per la formattazione delle righe delle tabelle nei documenti PDF?

R: Quando formatti le righe della tabella, considera la leggibilità e l'accessibilità del contenuto. Assicurati che i colori abbiano un contrasto sufficiente, utilizza caratteri chiari e leggibili e mantieni un layout coerente. Convalida la conformità PDF/UA per garantire il rispetto degli standard di accessibilità.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la personalizzazione dei documenti PDF?

R: Aspose.PDF per .NET offre un'ampia gamma di funzionalità per la personalizzazione dei documenti PDF, tra cui la manipolazione del testo, l'inserimento di immagini, la gestione dei campi modulo, le firme digitali, le annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per esplorare funzionalità aggiuntive.