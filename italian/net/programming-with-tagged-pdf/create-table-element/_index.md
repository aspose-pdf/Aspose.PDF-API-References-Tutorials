---
title: Crea elemento tabella
linktitle: Crea elemento tabella
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per creare un elemento di matrice con Aspose.PDF per .NET. Genera facilmente PDF dinamici con tabelle.
type: docs
weight: 80
url: /it/net/programming-with-tagged-pdf/create-table-element/
---
In questa guida dettagliata, ti guideremo attraverso il processo di creazione di un elemento dell'array utilizzando Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di manipolare i documenti PDF a livello di programmazione. La creazione di un elemento di matrice è un requisito comune durante la generazione di PDF dinamici e Aspose.PDF offre un modo semplice ed efficiente per ottenere questo risultato.

Immergiamoci nel codice e impariamo come creare un elemento di matrice utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.PDF per .NET installata.
2. Conoscenza di base del linguaggio di programmazione C#.

## Passaggio 1: configurazione dell'ambiente

Per iniziare, apri il tuo ambiente di sviluppo C# e crea un nuovo progetto. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET nel tuo progetto.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento

 Il primo passaggio consiste nel creare un nuovo documento PDF utilizzando il file`Document` classe.

```csharp
// Crea il documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Qui impostiamo anche il titolo e la lingua per il contenuto taggato.

## Passaggio 3: creazione dell'elemento dell'array

Successivamente, dobbiamo creare l'elemento dell'array e aggiungerlo al documento. Iniziamo ottenendo l'elemento della struttura radice, quindi creiamo un nuovo elemento della tabella utilizzando il`CreateTableElement` metodo.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Salva il documento PDF con tag
document.Save(dataDir + "CreateTableElement.pdf");

// Controllo di conformità PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Esempio di codice sorgente per Crea elemento tabella utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea documento
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Salva documento PDF con tag
document.Save(dataDir + "CreateTableElement.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusione

Hai imparato come creare un elemento di matrice utilizzando Aspose.PDF per .NET. Ora puoi generare documenti PDF con tabelle dinamiche utilizzando questo metodo. Sentiti libero di esplorare più funzionalità di Aspose.PDF per scoprire il suo pieno potenziale.

### FAQ

#### D: Cos'è un elemento array in un documento PDF e perché dovrei crearne uno utilizzando Aspose.PDF per .NET?

R: Un elemento array in un documento PDF rappresenta una raccolta strutturata di dati, spesso utilizzata per creare tabelle o griglie. Potrebbe essere necessario creare un elemento di matrice utilizzando Aspose.PDF per .NET quando si generano PDF dinamici che richiedono una presentazione di dati strutturati, come informazioni tabulari o griglie.

#### D: In che modo Aspose.PDF per .NET semplifica il processo di creazione di un elemento dell'array?

R: Aspose.PDF per .NET fornisce un set completo di classi e metodi che consentono di creare, personalizzare e gestire gli elementi dell'array (tabelle) in un documento PDF in modo programmatico. Ciò elimina la necessità di manipolare PDF manualmente e semplifica la creazione di rappresentazioni di dati strutturati.

#### D: Quali sono i passaggi chiave coinvolti nella creazione di un elemento dell'array utilizzando Aspose.PDF per .NET?

R: I passaggi chiave includono l'impostazione dell'ambiente, la creazione del documento, l'ottenimento dell'elemento della struttura principale, la creazione di un elemento della tabella, la definizione di righe e celle all'interno della tabella e la specifica della formattazione e delle proprietà degli elementi. L'esempio di codice fornito illustra questi passaggi.

####  D: Che ruolo ha il`taggedContent` object play in creating an array element?

 R: Il`taggedContent` oggetto, ottenuto dal documento`TaggedContent`proprietà, consente di definire la struttura del contenuto con tag all'interno del documento PDF. Ciò include la creazione e l'organizzazione degli elementi dell'array e dei relativi elementi figlio in modo gerarchico.

#### D: In che modo il codice garantisce l'accessibilità e la semantica dell'elemento dell'array creato?

 R: Il codice imposta attributi come`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , E`ColSpan` per migliorare l'accessibilità e la semantica dell'elemento dell'array. Questi attributi contribuiscono a una rappresentazione dei dati ben strutturata, informativa e visivamente accattivante.

#### D: Qual è l'importanza della conformità PDF/UA nel contesto della creazione di elementi di array?

 R: La conformità a PDF/UA (Universal Accessibility) garantisce che i documenti PDF generati siano accessibili agli utenti con disabilità e soddisfino determinati standard di accessibilità. L'esempio di codice verifica la conformità PDF/UA utilizzando il`Validate` metodo, aiutandoti a creare documenti inclusivi e accessibili.

#### D: Posso personalizzare ulteriormente la formattazione e l'aspetto degli elementi dell'array?

R: Sì, puoi personalizzare la formattazione e l'aspetto degli elementi dell'array regolando attributi come il colore di sfondo, lo stile del bordo, la dimensione del carattere e l'allineamento. Aspose.PDF per .NET offre un'ampia gamma di proprietà per adattare la presentazione visiva alle tue esigenze.

#### D: Come posso estendere questa conoscenza per creare strutture di tabelle più complesse o incorporare elementi di matrice in documenti PDF più grandi?

R: È possibile estendere questa conoscenza esplorando le funzionalità aggiuntive di Aspose.PDF per .NET, come l'unione di più elementi dell'array, la creazione di tabelle nidificate, l'aggiunta di intestazioni e piè di pagina e l'integrazione di elementi dell'array in layout PDF più grandi. La documentazione e gli esempi della libreria forniscono indicazioni per questi scenari avanzati.

#### D: È possibile importare dati da fonti esterne, come database o fogli di calcolo, per popolare gli elementi dell'array?

R: Sì, puoi importare dati da fonti esterne per popolare gli elementi dell'array. È possibile utilizzare le tecniche di recupero e trasformazione dei dati in C# per recuperare i dati da database, fogli di calcolo o altre origini e quindi popolare gli elementi dell'array di conseguenza.

#### D: Come posso utilizzare le conoscenze acquisite da questo tutorial per migliorare la qualità e l'usabilità dei documenti PDF che creo a livello di programmazione?

R: Le conoscenze acquisite da questo tutorial ti consentono di creare elementi array (tabelle) strutturati e visivamente accattivanti nei documenti PDF. Incorporando queste tecniche, puoi migliorare la leggibilità, l'accessibilità e l'esperienza utente dei PDF generati dinamicamente, rendendoli più informativi e di facile utilizzo.