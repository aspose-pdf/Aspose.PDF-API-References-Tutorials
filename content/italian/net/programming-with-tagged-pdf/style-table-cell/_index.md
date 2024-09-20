---
title: Cella della tabella di stile
linktitle: Cella della tabella di stile
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come formattare le celle di tabella in un PDF usando Aspose.PDF per .NET con questo tutorial dettagliato. Segui le istruzioni per creare e formattare splendide tabelle PDF.
type: docs
weight: 160
url: /it/net/programming-with-tagged-pdf/style-table-cell/
---
## Introduzione

Creare tabelle PDF dall'aspetto professionale può essere complicato, ma con Aspose.PDF per .NET è sorprendentemente semplice! Che tu stia assegnando uno stile a intestazioni, piè di pagina o celle specifiche di una tabella, questa potente libreria ti fornisce tutti gli strumenti di cui hai bisogno per creare documenti PDF splendidamente formattati. In questo tutorial, ti guideremo attraverso come assegnare uno stile alle celle di una tabella in un documento PDF usando Aspose.PDF per .NET. Non preoccuparti: suddivideremo tutto in semplici passaggi da seguire.

## Prerequisiti

Prima di immergerti nel codice, assicurati di disporre dei seguenti prerequisiti:

1. Aspose.PDF per .NET: Scarica e installa l'ultima versione di Aspose.PDF da[Qui](https://releases.aspose.com/pdf/net/).
2. IDE (come Visual Studio): configura un ambiente di sviluppo .NET.
3. Conoscenza di base della programmazione C#: è richiesta una certa familiarità con C#.
4.  Licenza Aspose.PDF: Ottieni una licenza temporanea o completa per sbloccare tutte le funzionalità della libreria. Puoi ottenere una prova gratuita[Qui](https://purchase.aspose.com/temporary-license/).

## Importa pacchetti

Prima di iniziare, assicurati di importare i namespace necessari. Avrai bisogno di quanto segue nel tuo progetto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora che tutto è pronto, passiamo alla guida passo dopo passo!

Creeremo una tabella in un documento PDF e imposteremo lo stile delle sue celle. Ogni passaggio spiegherà il processo in dettaglio.

## Passaggio 1: creare un nuovo documento PDF

 Il primo passo è creare un nuovo documento PDF. In Aspose.PDF, puoi inizializzare un nuovo`Document` oggetto, che rappresenta il file PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un nuovo documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Qui, inizializziamo un documento PDF e ne impostiamo il titolo e la lingua. Ciò conferisce al documento una struttura appropriata, essenziale per la conformità PDF/UA.

## Passaggio 2: impostare la struttura della tabella

Le tabelle nei PDF sono definite all'interno di elementi di struttura. Creiamo la tabella e definiamo le righe e le colonne della tabella.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;

// Crea un elemento struttura tabella
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Abbiamo ora definito la testa della tabella (`TableTHeadElement`), corpo (`TableTBodyElement`), e piede (`TableTFootElement`) sezioni. Puoi pensare a queste come allo scheletro della tua tabella.

## Passaggio 3: definire lo stile delle celle dell'intestazione

Lo stile delle celle dell'intestazione le fa risaltare. Qui applichiamo colori di sfondo, bordi e allineamento del testo.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

In questo passaggio, eseguiamo un ciclo su ogni cella di intestazione, assegnandole uno sfondo verde-giallo, un bordo grigio e un testo allineato a destra. Puoi adattare queste proprietà per adattarle al design desiderato.

## Passaggio 4: popolare e definire lo stile del corpo della tabella

Il corpo della tabella contiene i dati effettivi. Ecco come puoi definire lo stile di ogni cella con margini, bordi e impostazioni di testo specifici.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 In questo passaggio, riempiamo il corpo della tabella con quattro righe e stiliamo ogni cella con sfondi gialli e testo blu in grassetto centrato. Utilizziamo anche il`MarginInfo`classe per definire la spaziatura attorno al testo.

## Passaggio 5: Definisci lo stile del piè di pagina

Per dare alla tabella una struttura completa, aggiungiamo e stiliamo le celle del piè di pagina, proprio come abbiamo fatto con l'intestazione.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

La sezione del piè di pagina ha uno stile simile a quello dell'intestazione, consentendo ai lettori di seguire facilmente la struttura della tabella.

## Passaggio 6: Salvare e convalidare il documento PDF

Infine, salviamo il documento PDF e controlliamo se è compatibile con PDF/UA.

```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableCell.pdf");

// Controllo della conformità PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Salviamo il PDF e utilizziamo il`Validate` metodo per garantire che soddisfi gli standard di accessibilità (conformità PDF/UA).

## Conclusione

Lo stile delle tabelle in un PDF tramite Aspose.PDF per .NET è potente e flessibile. Con poche righe di codice, puoi creare design di tabelle personalizzati che faranno risaltare i tuoi documenti PDF. Dalla personalizzazione dei bordi e degli sfondi delle celle alla garanzia della conformità all'accessibilità, Aspose.PDF semplifica la creazione di file PDF rifiniti.

## Domande frequenti

### Posso applicare stili diversi alle singole celle della tabella?  
Sì, puoi definire lo stile delle singole celle personalizzando`TableTDElement` proprietà.

### Come posso unire le celle di una tabella?  
 Puoi usare il`ColSpan` E`RowSpan` proprietà per unire le celle in una tabella.

### È possibile creare una tabella compatibile con PDF/UA?  
 Sì, come dimostrato in questa guida, è possibile garantire la conformità PDF/UA convalidando il documento utilizzando`Validate` metodo.

### Posso usare font diversi nelle celle della tabella?  
 Assolutamente! Puoi specificare diversi font utilizzando`TextState` oggetto per ogni cella.

### Come posso scaricare Aspose.PDF per .NET?  
 Puoi scaricarlo da[pagina delle release](https://releases.aspose.com/pdf/net/).