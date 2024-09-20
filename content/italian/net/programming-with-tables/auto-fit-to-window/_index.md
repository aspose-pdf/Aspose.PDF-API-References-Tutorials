---
title: Adattamento automatico alla finestra
linktitle: Adattamento automatico alla finestra
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come adattare automaticamente una tabella alla finestra usando Aspose.PDF per .NET in questa guida dettagliata, passo dopo passo. Perfetta per creare tabelle raffinate e ben adattate nei PDF.
type: docs
weight: 50
url: /it/net/programming-with-tables/auto-fit-to-window/
---
## Introduzione

Quando si lavora con i PDF, è comune avere a che fare con le tabelle e ci sono momenti in cui hai bisogno che queste tabelle si adattino perfettamente alla larghezza di una pagina. In questo tutorial, esploreremo come adattare automaticamente una tabella a una finestra usando Aspose.PDF per .NET. Questo può far apparire le tue tabelle raffinate e organizzate, prevenendo problemi come overflow o colonne irregolari. Pronti a imparare? Tuffiamoci!

## Prerequisiti

Prima di passare alla guida dettagliata, ecco alcune cose di cui avrai bisogno:

1. Aspose.PDF per .NET installato nel tuo progetto. Se non lo hai ancora, puoi[scaricalo qui](https://releases.aspose.com/pdf/net/) o esplorarli[versione di prova gratuita](https://releases.aspose.com/).
2. Conoscenza di base della programmazione .NET.
3. Visual Studio o qualsiasi IDE supportato da .NET installato sul sistema.

>  PS Non dimenticare che ti servirà una licenza per usare Aspose.PDF senza limitazioni. Puoi comprarne una[Qui](https://purchase.aspose.com/buy) o ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per provare tutte le funzionalità.

## Importa pacchetti

Prima di immergerti nel codice, dovrai importare gli spazi dei nomi necessari:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ora che siamo pronti, scomponiamo il tutto in semplici e comprensibili passaggi per capire come adattare automaticamente una tabella a una finestra utilizzando Aspose.PDF per .NET.

## Passaggio 1: inizializzare l'oggetto documento

Per prima cosa, devi creare un documento PDF. Pensa a questo documento come a un foglio bianco in cui aggiungerai pagine e tabelle.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Pdf chiamando il suo costruttore vuoto
Document doc = new Document();
```
  
 Qui creiamo un nuovo documento utilizzando il`Document` classe da Aspose.PDF. La`dataDir` è la posizione in cui verrà salvato il tuo PDF una volta terminato.

## Passaggio 2: aggiungere una pagina al documento

Un documento PDF ha bisogno di pagine, giusto? Aggiungiamone una.

```csharp
// Crea una sezione (pagina) nell'oggetto Pdf
Page sec1 = doc.Pages.Add();
```
  
 Abbiamo aggiunto una nuova pagina al documento utilizzando il`Pages.Add()` metodo. Puoi pensare a questo come all'aggiunta di un nuovo foglio al tuo documento in cui inserirai la tabella.

## Passaggio 3: creare e configurare una tabella

Adesso è il momento di creare una tabella e di adattarla alla finestra.

```csharp
// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
sec1.Paragraphs.Add(tab1);
```
  
 Abbiamo inizializzato un nuovo`Table` oggetto e l'abbiamo aggiunto alla raccolta di paragrafi della pagina. Ogni pagina PDF può avere paragrafi diversi, e qui stiamo trattando la tabella come un paragrafo.

## Passaggio 4: definire la larghezza delle colonne e l'adattamento automatico alla finestra

Successivamente, impostiamo la larghezza delle colonne e ci assicuriamo che la tabella si adatti alla finestra.

```csharp
// Imposta la larghezza delle colonne per la tabella
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Abbiamo impostato larghezze di colonna fisse per la tabella ma abbiamo anche aggiunto`ColumnAdjustment.AutoFitToWindow`, che garantisce che la tabella adatti le sue dimensioni alla finestra disponibile.

## Passaggio 5: impostare bordi e margini per la tabella e le celle

Le tabelle senza bordi sono spesso illeggibili. Definiamo bordi e margini per renderle più ordinate.

```csharp
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// Crea l'oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
tab1.DefaultCellPadding = margin;
```
  
 I bordi vengono aggiunti sia alla tabella che alle celle utilizzando`BorderInfo` classe, dove definisci lo spessore. I margini sono impostati per dare alle celle un po' di spazio di riempimento.

## Passaggio 6: aggiungere righe e celle alla tabella

Una tabella senza contenuto? Non va bene! Aggiungiamo qualche riga e cella.

```csharp
//Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Stiamo creando due righe e aggiungendo tre celle a ciascuna riga. Qui è dove inserirai i tuoi dati effettivi (che potrebbero essere qualsiasi cosa, dalle stringhe a elementi più complessi).

## Passaggio 7: Salvare il documento

Una volta impostato tutto, puoi salvare il documento PDF appena creato.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);
```
  
 IL`doc.Save()` metodo salva il PDF nella directory specificata. In questo caso, il documento verrà salvato come`AutoFitToWindow_out.pdf` nella directory definita.

## Conclusione

Ed ecco fatto! Hai appena creato una tabella che si adatta automaticamente alla finestra usando Aspose.PDF per .NET. Questo non solo assicura che la tua tabella abbia un aspetto professionale e ben adattato, ma ti dà anche flessibilità quando lavori con dimensioni di dati variabili. Che tu stia creando report, fatture o qualsiasi documento che richieda tabelle, questo metodo è un ottimo modo per mantenere layout puliti e leggibili.

## Domande frequenti

### Posso aggiungere più righe in modo dinamico?  
 Sì, puoi continuare ad aggiungere righe utilizzando`tab1.Rows.Add()` metodo, basato dinamicamente sul contenuto.

### Come faccio a regolare la tabella se non voglio che si adatti automaticamente?  
 È possibile impostare manualmente il`ColumnWidths` senza usare`ColumnAdjustment.AutoFitToWindow` per mantenere una larghezza fissa del tavolo.

### Posso aggiungere immagini o altri contenuti all'interno delle celle?  
Sì, Aspose.PDF consente di aggiungere immagini, testo e persino altre tabelle all'interno delle celle!

### Cosa succede se ho bisogno di stili di tabella più complessi?  
È possibile personalizzare ulteriormente gli stili delle tabelle e delle celle utilizzando proprietà quali il colore di sfondo, l'allineamento del testo e le impostazioni del carattere.

### È possibile esportare questa tabella in formati diversi dal PDF?  
Assolutamente! Aspose.PDF supporta l'esportazione in vari formati come HTML, DOCX e altro.