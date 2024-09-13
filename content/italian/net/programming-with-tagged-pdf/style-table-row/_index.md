---
title: Riga della tabella di stile
linktitle: Riga della tabella di stile
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come personalizzare le righe della tabella con Aspose.PDF per .NET, una guida dettagliata per la formattazione e lo stile delle righe.
type: docs
weight: 180
url: /it/net/programming-with-tagged-pdf/style-table-row/
---
In questo tutorial dettagliato, ti guideremo passo dopo passo attraverso il codice sorgente C# fornito per formattare la riga della tabella utilizzando Aspose.PDF per .NET. Segui le istruzioni sottostanti per capire come personalizzare stili e proprietà delle righe della tabella.

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
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua.

## Fase 3: Ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento struttura radice per il nostro documento.

```csharp
// Ottieni l'elemento della struttura radice
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

## Passaggio 5: personalizzare gli stili e le proprietà delle righe della tabella

In questa fase personalizzeremo gli stili e le proprietà delle righe della tabella.

```csharp
// Personalizza gli stili e le proprietà delle righe della tabella
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

Abbiamo personalizzato vari aspetti della riga della tabella, come il colore di sfondo, i bordi, l'altezza della riga, la paginazione, lo stile predefinito delle celle e altro ancora.

## Passaggio 6: salvataggio del documento PDF taggato

Ora che abbiamo creato il nostro documento con la riga della tabella formattata, lo salveremo come documento PDF con tag.
```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableRow.pdf");
```

Abbiamo salvato il documento PDF taggato nella directory specificata.

## Fase 7: convalida della conformità PDF/UA

Successivamente valideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF taggato e ne abbiamo convalidato la conformità PDF/UA generando un report XML.


### Esempio di codice sorgente per Style Table Row utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea elemento struttura tabella
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

// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableRow.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come formattare le righe di tabella con Aspose.PDF per .NET. Abbiamo personalizzato gli stili e le proprietà delle righe di tabella, aggiunto le intestazioni, le righe del corpo e il piè di pagina, salvato il documento PDF taggato e convalidato la sua conformità PDF/UA.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial sulla formattazione delle righe di una tabella utilizzando Aspose.PDF per .NET?

R: Lo scopo di questo tutorial è guidarti attraverso il processo di formattazione delle righe di tabella in un documento PDF utilizzando Aspose.PDF per .NET. Fornisce istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a personalizzare stili e proprietà delle righe di tabella.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo per usare Aspose.PDF per .NET. Ciò comporta l'installazione della libreria Aspose.PDF e la configurazione del tuo progetto per farvi riferimento.

#### D: Come posso creare un nuovo documento PDF e impostarne il titolo e la lingua utilizzando Aspose.PDF per .NET?

 A: Per creare un nuovo documento PDF, è necessario creare un`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito dal tutorial dimostra come creare un documento e impostarne le proprietà titolo e lingua.

#### D: Qual è il significato dell'elemento struttura radice in un documento PDF?

A: L'elemento struttura radice funge da contenitore per altri elementi struttura, aiutando a organizzare e categorizzare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare e personalizzare un elemento della struttura della tabella per formattare le righe della tabella utilizzando Aspose.PDF per .NET?

R: Il tutorial spiega come creare un elemento struttura tabella e personalizzare le sue proprietà per formattare le righe della tabella. Copre aspetti quali colore di sfondo, bordi, altezza riga, impaginazione, stile cella predefinito e altro.

#### D: Posso personalizzare gli stili e le proprietà delle singole celle all'interno di una riga di una tabella?

R: Sì, puoi personalizzare gli stili e le proprietà delle singole celle all'interno di una riga di tabella. Il tutorial mostra come impostare proprietà quali colore di sfondo, bordi, colore del testo, padding e altro per le celle di tabella all'interno della riga di tabella formattata.

#### D: Come posso aggiungere intestazioni, righe del corpo e un piè di pagina alla riga della tabella formattata?

R: Il tutorial fornisce esempi di creazione e aggiunta di intestazioni, righe del corpo e un piè di pagina all'elemento struttura tabella. Questi elementi possono essere ulteriormente personalizzati utilizzando le proprietà descritte nel tutorial.

#### D: Che cos'è la conformità PDF/UA e come posso convalidarla per il mio documento PDF taggato?

 A: La conformità PDF/UA assicura che il documento PDF sia conforme agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial mostra come convalidare la conformità PDF/UA utilizzando`Validate()` metodo e generare un report di conformità XML.

#### D: Come posso integrare questi concetti nelle mie applicazioni .NET?

R: Puoi usare gli esempi di codice sorgente C# forniti come guida per implementare la formattazione delle righe di tabella nelle tue applicazioni .NET. Modifica e adatta il codice per adattarlo ai tuoi requisiti e integralo nei tuoi progetti.

#### D: Esistono delle buone pratiche consigliate per la formattazione delle righe delle tabelle nei documenti PDF?

R: Quando formatti le righe della tabella, considera la leggibilità e l'accessibilità del contenuto. Assicurati che i colori abbiano un contrasto sufficiente, usa caratteri chiari e leggibili e mantieni un layout coerente. Convalida la conformità PDF/UA per garantire che gli standard di accessibilità siano rispettati.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la personalizzazione dei documenti PDF?

R: Aspose.PDF per .NET offre un'ampia gamma di funzionalità per la personalizzazione dei documenti PDF, tra cui manipolazione del testo, inserimento di immagini, gestione dei campi dei moduli, firme digitali, annotazioni e altro ancora. Consulta la documentazione e le risorse ufficiali per esplorare funzionalità aggiuntive.