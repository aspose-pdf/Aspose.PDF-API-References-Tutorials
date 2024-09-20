---
title: Elemento della tabella di stile
linktitle: Elemento della tabella di stile
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare e definire lo stile di un elemento tabella in Aspose.PDF per .NET con istruzioni dettagliate, stile personalizzato e conformità PDF/UA.
type: docs
weight: 170
url: /it/net/programming-with-tagged-pdf/style-table-element/
---
## Introduzione

In questo articolo, approfondiremo come creare e definire lo stile di un elemento tabella usando Aspose.PDF per .NET. Imparerai come strutturare una tabella, applicare stili personalizzati e convalidare la conformità PDF/UA del tuo documento. Alla fine di questo tutorial, sarai in grado di creare tabelle dall'aspetto professionale nei tuoi PDF con facilità!

## Prerequisiti

Prima di iniziare il tutorial, assicurati di avere quanto segue:

1. Visual Studio o un IDE simile installato sul computer.
2. .NET Framework o .NET Core SDK per l'esecuzione dell'applicazione.
3.  Aspose.PDF per la libreria .NET scaricata e referenziata nel tuo progetto. Puoi prendere l'ultima versione da[Qui](https://releases.aspose.com/pdf/net/).
4.  Una licenza Aspose valida o una[licenza temporanea](https://purchase.aspose.com/temporary-license/) per sbloccare tutte le funzionalità della libreria.

## Importa pacchetti

Per iniziare, importa gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Questi namespace coprono le principali operazioni PDF, i contenuti taggati, le tabelle e la formattazione del testo.

Ora analizziamo il processo di creazione e definizione dello stile di una tabella in Aspose.PDF. Analizzeremo ogni sezione in dettaglio, così potrai seguire.

## Passaggio 1: creare un nuovo documento PDF e impostare il contenuto taggato

In questo primo passaggio creeremo un documento PDF vuoto e imposteremo il suo contenuto taggato.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un nuovo documento PDF
Document document = new Document();

// Imposta contenuto taggato
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Iniziamo creando un nuovo`Document` oggetto, che rappresenta il nostro PDF. L'`TaggedContent`object viene utilizzato per gestire la struttura del documento, assicurando la conformità con gli standard di accessibilità. Impostiamo il titolo e la lingua del documento per un tagging appropriato.

## Passaggio 2: definire l'elemento radice

Successivamente creeremo l'elemento struttura radice, che fungerà da contenitore per tutti i contenuti del nostro PDF.

```csharp
// Ottieni l'elemento della struttura radice
StructureElement rootElement = taggedContent.RootElement;
```

 IL`RootElement` funge da contenitore di base per tutti gli elementi strutturati, inclusa la nostra tabella. Aiuta a mantenere la gerarchia strutturale del documento, che è importante sia per l'organizzazione che per l'accessibilità.

## Passaggio 3: creare e definire lo stile dell'elemento tabella

 Ora che l'elemento radice è impostato, creeremo un`TableElement` e applicare stili come colore di sfondo, bordi e allineamento.

```csharp
// Crea elemento struttura tabella
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Imposta lo stile della tabella
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Creiamo un`TableElement` , che definisce la struttura della nostra tabella. Il`BackgroundColor`, `Border` , E`Alignment` le proprietà ci permettono di personalizzare l'aspetto della tabella.`Broken` La proprietà assicura che se la tabella si divide su più pagine, lo fa verticalmente.

## Passaggio 4: impostare le dimensioni della tabella e gli stili delle celle

In questo passaggio definiremo il numero di colonne, la spaziatura delle celle e altre importanti proprietà della tabella.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Specifichiamo le larghezze delle colonne per garantire che ogni colonna nella tabella sia uniformemente distanziata.`DefaultCellBorder`, `DefaultCellPadding` , E`DefaultCellTextState` definire gli stili predefiniti per le celle, inclusi bordi, spaziatura, colore del testo e dimensione del carattere.

## Passaggio 5: aggiungere righe ripetute e stili personalizzati

Possiamo anche definire stili per le righe ripetute e altri elementi specifici della tabella, come intestazioni e piè di pagina.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 IL`RepeatingRowsCount` assicura che le prime tre righe si ripetano se la tabella si estende su più pagine. Impostiamo il`RepeatingRowsStyle` per applicare un colore di sfondo personalizzato a queste righe.

## Passaggio 6: aggiungere gli elementi intestazione, corpo e piede della tabella

Ora creiamo le sezioni intestazione, corpo e piè di pagina della tabella e riempiamole con il contenuto.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Crea riga di intestazione
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Popolare il corpo della tabella
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 La tabella è divisa in tre parti: testa, corpo e piede. Per prima cosa creiamo la riga di intestazione usando`TableTHElement` aggiungiamo le intestazioni di colonna. Quindi, popoliamo il corpo della tabella con`TableTDElement`, riempiendo ogni cella con un'etichetta che include la sua posizione.

## Passaggio 7: Salvare il documento

Infine, salviamo il documento PDF nella directory specificata.

```csharp
// Salva il documento PDF taggato
document.Save(dataDir + "StyleTableElement.pdf");
```

Questo passaggio completa il processo di creazione del documento salvando il file PDF con la tabella formattata.

## Fase 8: convalidare la conformità PDF/UA

Dopo aver salvato il documento, è fondamentale assicurarsi che sia conforme agli standard PDF/UA (Universal Accessibility).

```csharp
// Controllare la conformità PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Qui, ricarichiamo il documento e lo convalidiamo rispetto agli standard PDF/UA. La conformità assicura che il tuo PDF soddisfi i requisiti di accessibilità, rendendolo adatto a un'ampia gamma di utenti.

## Conclusione

Con Aspose.PDF per .NET, creare e definire lo stile delle tabelle nei tuoi documenti PDF è semplice e intuitivo. Seguendo i passaggi descritti in questo tutorial, puoi creare tabelle con stili personalizzati e garantire che i tuoi PDF soddisfino gli standard di accessibilità. Che tu stia generando report o creando documenti strutturati, le tabelle sono uno strumento potente per presentare i dati in modo chiaro.

## Domande frequenti

### Posso aggiungere immagini all'interno delle celle della tabella?
 Sì, puoi inserire immagini nelle celle della tabella utilizzando`Image` elemento.

### Come posso regolare dinamicamente la larghezza delle colonne?
 Puoi impostare il`ColumnAdjustment` proprietà a`AutoFitToWindow` per adattare automaticamente la larghezza delle colonne in base al contenuto.

### La conformità PDF/UA è obbligatoria per tutti i documenti?
Sebbene non sia obbligatorio, è consigliato per i documenti che richiedono elevati standard di accessibilità.

### Posso applicare stili diversi a righe specifiche?
 Sì, puoi personalizzare singole righe o celle modificandone le impostazioni`TextState` O`BackgroundColor`.

### Qual è il vantaggio di utilizzare contenuti taggati?
contenuti taggati migliorano l'accessibilità dei documenti e contribuiscono a garantire la conformità con standard come PDF/UA.