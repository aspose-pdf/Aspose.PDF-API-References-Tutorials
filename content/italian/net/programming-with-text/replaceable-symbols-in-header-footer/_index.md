---
title: Simboli sostituibili nell'intestazione e nel piè di pagina
linktitle: Simboli sostituibili nell'intestazione e nel piè di pagina
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare simboli sostituibili nell'intestazione e nel piè di pagina di un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Introduzione

Quando si lavora con file PDF, a volte è necessario personalizzare intestazioni e piè di pagina con contenuti dinamici come numeri di pagina, nomi di report o date generate. Fortunatamente, Aspose.PDF per .NET semplifica questo processo, consentendo di creare PDF con simboli aggiornati automaticamente in intestazioni e piè di pagina, come numeri di pagina o dettagli di generazione di report. Questo articolo ti guiderà passo dopo passo nel processo di sostituzione dei simboli in intestazioni e piè di pagina utilizzando Aspose.PDF per .NET, in un modo non solo semplice ma anche incredibilmente efficiente.

## Prerequisiti

Prima di immergerti nella guida passo passo, assicurati di avere quanto segue:

-  Aspose.PDF per la libreria .NET –[Scaricamento](https://releases.aspose.com/pdf/net/) o ottenere un[prova gratuita](https://releases.aspose.com/).
- Visual Studio o qualsiasi IDE C# installato sul sistema.
- Conoscenza di base dello sviluppo C# e .NET.
-  Un valido[licenza](https://purchase.aspose.com/temporary-license/) per Aspose.PDF oppure puoi utilizzare la versione di prova.

## Importa pacchetti

Per iniziare, devi importare i namespace necessari che abiliteranno la funzionalità di Aspose.PDF per .NET. Di seguito è riportata l'importazione necessaria:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Sono essenziali per gestire la creazione di PDF, la manipolazione del testo e la gestione di intestazioni e piè di pagina.

Scomponiamo il codice di esempio in passaggi facili da comprendere.

## Passaggio 1: impostare il documento e la pagina

Per prima cosa, dobbiamo inizializzare il documento e aggiungervi una pagina. Questo pone le basi per aggiungere intestazioni e piè di pagina.

```csharp
// Imposta la directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inizializza l'oggetto documento
Document doc = new Document();

// Aggiungere una pagina al documento
Page page = doc.Pages.Add();
```

 Qui stiamo impostando un documento PDF utilizzando`Document` classe e aggiunta di una pagina con`doc.Pages.Add()`Questa pagina conterrà l'intestazione, il piè di pagina e altri contenuti.

## Passaggio 2: configurare i margini della pagina

Ora definiremo i margini della pagina per garantire che il contenuto non arrivi fino al bordo.

```csharp
// Configurare i margini
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Qui abbiamo definito i margini superiore, inferiore, sinistro e destro utilizzando`MarginInfo` classe e l'ho applicata alla pagina usando`page.PageInfo.Margin`.

## Passaggio 3: creare e configurare l'intestazione

Ora, creiamo un'intestazione e aggiungiamola alla pagina. L'intestazione includerà il titolo e il nome del report.

```csharp
// Crea intestazione
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Imposta i margini dell'intestazione
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Aggiungi titolo all'intestazione
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Aggiungi il nome del report all'intestazione
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 Ne abbiamo aggiunti due`TextFragment` oggetti all'intestazione: uno per il titolo del report e un altro per il nome del report. Il testo è formattato utilizzando`TextState` proprietà come carattere, dimensione e allineamento.

## Passaggio 4: creare e configurare il piè di pagina

Adesso è il momento di impostare il piè di pagina, che conterrà contenuti dinamici come i numeri di pagina e la data di generazione.

```csharp
// Crea piè di pagina
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Imposta i margini del piè di pagina
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Aggiungere contenuto al piè di pagina
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

Nel piè di pagina includiamo frammenti per la data di generazione, il nome del report e i numeri di pagina dinamici (`$p` E`$P` rappresentano rispettivamente il numero di pagina corrente e il numero totale di pagine).

## Passaggio 5: creare una tabella nel piè di pagina

Puoi anche aggiungere elementi più complessi, come tabelle, nel piè di pagina per organizzare meglio i tuoi dati.

```csharp
// Crea tabella per il piè di pagina
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Crea righe e celle per la tabella
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Imposta l'allineamento per ogni cella
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Aggiungere contenuto alle celle della tabella
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Questo blocco di codice crea una tabella a 3 colonne nel piè di pagina, in cui ogni colonna contiene informazioni diverse, come la data di generazione, il nome del report e i numeri di pagina.

## Passaggio 6: aggiungere contenuto alla pagina

Oltre alle intestazioni e ai piè di pagina, puoi aggiungere contenuti al corpo della pagina PDF. Qui, aggiungiamo una tabella con del testo segnaposto.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Aggiungere contenuto alla tabella
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Questo codice aggiunge una semplice tabella con tre colonne alla pagina. Puoi modificarla per adattarla alle tue esigenze specifiche.

## Passaggio 7: Salva il PDF

Una volta impostato tutto, l'ultimo passaggio consiste nel salvare il documento PDF nella posizione desiderata.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Si specifica il percorso del file e si salva il documento utilizzando`doc.Save()`Ecco fatto! Hai creato con successo un PDF con intestazioni e piè di pagina personalizzati.

## Conclusione

Sostituire i simboli nelle intestazioni e nei piè di pagina usando Aspose.PDF per .NET non è solo semplice ma anche potente. Seguendo la guida passo passo sopra, puoi personalizzare facilmente i tuoi PDF con contenuti dinamici, come numeri di pagina, nomi di report e date. Questo metodo è altamente flessibile, consentendoti di inserire tabelle, modificare la formattazione e controllare il layout per adattarlo ai tuoi requisiti specifici.

## Domande frequenti

### Posso personalizzare i font per intestazioni e piè di pagina?  
Sì, puoi personalizzare completamente i caratteri, le dimensioni, i colori e gli stili del testo nelle intestazioni e nei piè di pagina.

### Come faccio ad aggiungere immagini alle intestazioni e ai piè di pagina?  
 Puoi usare`ImageStamp` per inserire immagini nelle intestazioni e nei piè di pagina.

### È possibile aggiungere collegamenti ipertestuali nelle intestazioni o nei piè di pagina?  
 Sì, puoi usare`TextFragment` con un collegamento ipertestuale impostando il`Hyperlink` proprietà.

### Posso usare intestazioni diverse per le pagine pari e dispari?  
Sì, Aspose.PDF consente di specificare intestazioni e piè di pagina diversi per le pagine pari e dispari.

### Come faccio a modificare le posizioni di intestazione e piè di pagina?  
È possibile regolare i margini e le proprietà di allineamento per controllare la posizione delle intestazioni e dei piè di pagina.