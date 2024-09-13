---
title: Cella della tabella di stile
linktitle: Cella della tabella di stile
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come definire lo stile delle celle di una tabella con Aspose.PDF per .NET. Guida passo passo per creare e personalizzare le tabelle.
type: docs
weight: 160
url: /it/net/programming-with-tagged-pdf/style-table-cell/
---
Benvenuti a questo tutorial dettagliato sulla formattazione delle celle di tabella tramite Aspose.PDF per .NET. In questa guida, spiegheremo in dettaglio ogni passaggio del codice sorgente C# fornito per aiutarvi a capire come formattare le celle di tabella. Assicuratevi di aver installato Aspose.PDF per .NET e di aver configurato il vostro ambiente di sviluppo prima di iniziare.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Abbiamo creato un nuovo documento e impostato il titolo e la lingua.

## Fase 3: Ottenere l'elemento della struttura radice

In questo passaggio otterremo l'elemento struttura radice per il nostro documento.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

Abbiamo ottenuto l'elemento della struttura radice che fungerà da contenitore per gli elementi dell'array.

## Fase 4: Creazione dell'elemento della struttura array

Ora creiamo un nuovo elemento di struttura tabella per il nostro documento.

```csharp
// Crea l'elemento della struttura array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Abbiamo creato un nuovo elemento di struttura array e lo abbiamo aggiunto all'elemento di struttura radice. Abbiamo anche creato gli elementi di intestazione, corpo e piè di pagina della tabella.

## Passaggio 5: aggiunta di intestazioni di tabella

In questo passaggio aggiungeremo le intestazioni di tabella alla nostra tabella.

```csharp
// Numero di righe e colonne nella tabella
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Crea la riga dell'intestazione della tabella
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

Abbiamo creato una riga di intestazione per la nostra tabella e aggiunto celle di intestazione con proprietà di formattazione quali colore di sfondo, bordi, margini e allineamento.

## Passaggio 6: aggiunta delle righe del corpo della tabella

Aggiungiamo ora le righe del corpo della tabella alla nostra tabella.
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

Abbiamo aggiunto righe al corpo della tabella usando cicli per scorrere ogni cella della tabella. Abbiamo impostato le proprietà di formattazione per ogni cella, come colore di sfondo, bordi, margini, allineamento del testo, ecc.

## Fase 7: Aggiungere il piè di pagina

Infine, aggiungeremo il piè di pagina alla nostra tabella.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Abbiamo creato un piè di pagina per la nostra tabella e abbiamo aggiunto celle con testo.



## Passaggio 8: salvataggio del documento PDF taggato

Ora che abbiamo creato il nostro documento con la tabella formattata, lo salveremo come documento PDF con tag.

```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableCell.pdf");
```

Abbiamo salvato il documento PDF taggato nella directory specificata.

## Fase 9: convalida della conformità PDF/UA

Successivamente valideremo la conformità PDF/UA del nostro documento.

```csharp
// Controllo di conformità PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Abbiamo caricato il documento PDF taggato e ne abbiamo convalidato la conformità PDF/UA generando un report XML.

### Esempio di codice sorgente per Style Table Cell utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea elemento struttura tabella
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

// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableCell.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

In questo tutorial, abbiamo imparato come formattare le celle di tabella usando Aspose.PDF per .NET. Abbiamo visto come creare un documento, aggiungere una tabella con intestazioni, righe del corpo e un piè di pagina e personalizzare gli stili delle celle. Infine, abbiamo salvato il documento PDF taggato e convalidato la sua conformità PDF/UA. Ora puoi usare Aspose.PDF per .NET per creare e formattare tabelle nelle tue applicazioni .NET.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial sulla formattazione delle celle di una tabella utilizzando Aspose.PDF per .NET?

R: Questo tutorial ha lo scopo di fornire una guida completa su come formattare le celle di tabella in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Copre istruzioni dettagliate ed esempi di codice sorgente C# per aiutarti a comprendere e implementare la formattazione delle celle di tabella.

#### D: Quali sono i prerequisiti per seguire questo tutorial?

R: Prima di iniziare, assicurati di aver installato Aspose.PDF per .NET e di aver impostato il tuo ambiente di sviluppo. Ciò include la configurazione del tuo progetto per fare riferimento alla libreria Aspose.PDF.

#### D: Come posso creare un nuovo documento PDF utilizzando Aspose.PDF per .NET?

 A: Per creare un nuovo documento PDF, è necessario creare un'istanza di`Document` oggetto dalla libreria Aspose.PDF. Il codice sorgente C# fornito dimostra come creare un documento e impostarne il titolo e la lingua.

#### D: Qual è il significato dell'elemento struttura radice in un documento PDF?

A: L'elemento struttura radice funge da contenitore per altri elementi struttura, aiutando a organizzare e categorizzare il contenuto del documento PDF. Svolge un ruolo cruciale nello stabilire la struttura logica del documento.

#### D: Come posso creare un elemento struttura tabella e personalizzarne l'aspetto utilizzando Aspose.PDF per .NET?

 A: È possibile creare un elemento di struttura della tabella utilizzando`CreateTableElement()` metodo. Il codice sorgente fornito dimostra come personalizzare l'aspetto della tabella, inclusi intestazione, corpo e piè di pagina, impostando proprietà quali colore di sfondo, bordi, margini e allineamento.

#### D: Posso aggiungere più righe e colonne al corpo della tabella e personalizzarne la formattazione?

R: Sì, il tutorial mostra come aggiungere più righe e colonne al corpo della tabella usando i loop. Fornisce anche esempi di personalizzazione della formattazione delle celle, come colore di sfondo, bordi, allineamento del testo, stile del carattere e altro.

#### D: Qual è lo scopo della convalida della conformità PDF/UA e come posso eseguire questa convalida?

 A: La convalida della conformità PDF/UA garantisce che il documento PDF aderisca agli standard di accessibilità, rendendolo più accessibile agli utenti con disabilità. Il tutorial mostra come convalidare la conformità PDF/UA utilizzando`Validate()` metodo e generare un report XML.

#### D: Come posso applicare questi concetti alle mie applicazioni .NET?

R: Puoi usare gli esempi di codice sorgente C# forniti come guida per implementare la formattazione delle celle di tabella nelle tue applicazioni .NET. Personalizza il codice come necessario per adattarlo ai tuoi requisiti e integralo nei tuoi progetti.

#### D: Esistono delle buone pratiche consigliate per definire lo stile delle celle delle tabelle nei documenti PDF?

R: Quando si assegna lo stile alle celle della tabella, considerare le esigenze del pubblico, inclusi i requisiti di accessibilità. Utilizzare colori contrastanti, font appropriati e un chiaro allineamento delle celle per migliorare la leggibilità. Inoltre, convalidare la conformità PDF/UA per garantire che gli standard di accessibilità siano rispettati.

#### D: Quali altre funzionalità di Aspose.PDF per .NET posso esplorare per la manipolazione di documenti PDF?

R: Aspose.PDF per .NET offre un'ampia gamma di funzionalità per la manipolazione di documenti PDF, tra cui estrazione di testo, inserimento di immagini, gestione dei campi dei moduli, firme digitali e altro ancora. Esplora la documentazione ufficiale e le risorse per scoprire funzionalità aggiuntive.
