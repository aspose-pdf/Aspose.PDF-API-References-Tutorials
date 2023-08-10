---
title: Cella tabella stili
linktitle: Cella tabella stili
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come modellare le celle della tabella con Aspose.PDF per .NET. Guida dettagliata alla creazione e alla personalizzazione delle tabelle.
type: docs
weight: 160
url: /it/net/programming-with-tagged-pdf/style-table-cell/
---
Benvenuto in questo tutorial dettagliato sulla formattazione delle celle della tabella utilizzando Aspose.PDF per .NET. In questa guida, spiegheremo in dettaglio ogni passaggio del codice sorgente C# fornito per aiutarti a capire come assegnare uno stile alle celle della tabella. Assicurati di aver installato Aspose.PDF per .NET e di configurare il tuo ambiente di sviluppo prima di iniziare.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua del documento.

## Passaggio 3: ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento della struttura radice per il nostro documento.

```csharp
//Ottenere l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo l'elemento della struttura radice che fungerà da contenitore per gli elementi dell'array.

## Passaggio 4: creazione dell'elemento della struttura dell'array

Ora creiamo un nuovo elemento della struttura della tabella per il nostro documento.

```csharp
// Creare l'elemento della struttura dell'array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Abbiamo creato un nuovo elemento della struttura dell'array e lo abbiamo aggiunto all'elemento della struttura radice. Abbiamo anche creato gli elementi di intestazione, corpo e piè di pagina della tabella.

## Passaggio 5: aggiunta di intestazioni di tabella

In questo passaggio aggiungeremo le intestazioni della tabella alla nostra tabella.

```csharp
// Numero di righe e colonne nella tabella
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Crea la riga di intestazione della tabella
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Abbiamo creato una riga di intestazione per la nostra tabella e aggiunto celle di intestazione con proprietà di formattazione come colore di sfondo, bordi, margini e allineamento.

## Passaggio 6: aggiunta delle righe del corpo della tabella

Ora aggiungiamo le righe del corpo della tabella alla nostra tabella.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Abbiamo aggiunto righe al corpo della tabella utilizzando cicli per iterare su ogni cella della tabella. Impostiamo le proprietà di formattazione per ogni cella, come il colore di sfondo, i bordi, i margini, l'allineamento del testo, ecc.

## Passaggio 7: aggiunta del piè di pagina

Infine, aggiungeremo il piè di pagina della tabella alla nostra tabella.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Abbiamo creato un piè di pagina per la nostra tabella e aggiunto celle a piè di pagina con testo.



## Passaggio 8: salvare il documento PDF con tag

Ora che abbiamo creato il nostro documento con la tabella in stile, lo salveremo come documento PDF con tag.

```csharp
// Salva il documento PDF con tag
document.Save(dataDir + "StyleTableCell.pdf");
```

Abbiamo salvato il documento PDF con tag nella directory specificata.

## Passaggio 9: convalida della conformità PDF/UA

Successivamente, convalideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF con tag e ne abbiamo convalidato la conformità PDF/UA generando un rapporto XML.

### Esempio di codice sorgente per Style Table Cell utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea un elemento della struttura della tabella
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come definire lo stile delle celle della tabella utilizzando Aspose.PDF per .NET. Abbiamo visto come creare un documento, aggiungere una tabella con intestazioni, righe del corpo e un piè di pagina e personalizzare gli stili delle celle. Infine, abbiamo salvato il documento PDF con tag e ne abbiamo convalidato la conformità PDF/UA. È ora possibile utilizzare Aspose.PDF per .NET per creare e applicare uno stile alle tabelle nelle applicazioni .NET.

### FAQ

#### D: Qual è lo scopo di questo tutorial sulla formattazione delle celle delle tabelle utilizzando Aspose.PDF per .NET?

R: Questo tutorial ha lo scopo di fornire una guida completa su come modellare le celle di una tabella in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Copre istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a comprendere e implementare la formattazione delle celle di tabella.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver installato Aspose.PDF per .NET e di aver impostato il tuo ambiente di sviluppo. Ciò include la configurazione del progetto per fare riferimento alla libreria Aspose.PDF.

#### D: Come faccio a creare un nuovo documento PDF utilizzando Aspose.PDF per .NET?

R: Per creare un nuovo documento PDF, è necessario creare un'istanza a`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito mostra come creare un documento e impostarne il titolo e la lingua.

#### D: Qual è il significato dell'elemento della struttura radice in un documento PDF?

R: L'elemento della struttura principale funge da contenitore per altri elementi della struttura, aiutando a organizzare e classificare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare un elemento della struttura della tabella e personalizzarne l'aspetto utilizzando Aspose.PDF per .NET?

 R: Puoi creare un elemento della struttura della tabella utilizzando il file`CreateTableElement()` metodo. Il codice sorgente fornito mostra come personalizzare l'aspetto della tabella, inclusi intestazione, corpo e piè di pagina, impostando proprietà quali colore di sfondo, bordi, margini e allineamento.

#### D: Posso aggiungere più righe e colonne al corpo della tabella e personalizzarne la formattazione?

R: Sì, il tutorial mostra come aggiungere più righe e colonne al corpo della tabella utilizzando i cicli. Fornisce inoltre esempi di personalizzazione della formattazione delle celle, come il colore di sfondo, i bordi, l'allineamento del testo, lo stile del carattere e altro.

#### D: Qual è lo scopo della convalida della conformità PDF/UA e come posso eseguire questa convalida?

 R: La convalida della conformità PDF/UA garantisce che il documento PDF aderisca agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial mostra come convalidare la conformità PDF/UA utilizzando il file`Validate()` metodo e generare un report XML.

#### D: Come posso applicare questi concetti alle mie applicazioni .NET?

R: È possibile utilizzare gli esempi di codice sorgente C# forniti come guida per l'implementazione della formattazione delle celle di tabella nelle proprie applicazioni .NET. Personalizza il codice secondo necessità per soddisfare le tue esigenze e integralo nei tuoi progetti.

#### D: Esistono best practice consigliate per applicare lo stile alle celle delle tabelle nei documenti PDF?

R: Quando definisci lo stile delle celle della tabella, considera le esigenze del tuo pubblico, inclusi i requisiti di accessibilità. Utilizza colori contrastanti, caratteri appropriati e un chiaro allineamento delle celle per migliorare la leggibilità. Inoltre, convalida la conformità PDF/UA per garantire il rispetto degli standard di accessibilità.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la manipolazione di documenti PDF?

R: Aspose.PDF per .NET offre un'ampia gamma di funzionalità per la manipolazione dei documenti PDF, tra cui l'estrazione del testo, l'inserimento di immagini, la gestione dei campi modulo, le firme digitali e altro ancora. Esplora la documentazione e le risorse ufficiali per conoscere le funzionalità aggiuntive.
