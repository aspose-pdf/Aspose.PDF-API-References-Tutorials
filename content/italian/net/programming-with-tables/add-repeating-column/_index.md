---
title: Aggiungi colonna ripetuta nel documento PDF
linktitle: Aggiungi colonna ripetuta nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere colonne ripetute ai documenti PDF usando Aspose.PDF per .NET. Guida passo passo con esempi e codice. Perfetto per gli sviluppatori.
type: docs
weight: 20
url: /it/net/programming-with-tables/add-repeating-column/
---
## Introduzione

Se lavori con documenti PDF e hai bisogno di aggiungere colonne ripetute, sei nel posto giusto! Utilizzando Aspose.PDF per .NET, puoi gestire facilmente tabelle e contenuti all'interno di un PDF. Che tu stia creando report dinamici, fatture o qualsiasi altro documento strutturato, le colonne ripetute possono cambiare le carte in tavola nell'organizzazione dei dati. Immergiamoci in una guida passo passo su come aggiungere colonne ripetute a un documento PDF.

## Prerequisiti

Prima di passare al codice, assicuriamoci di aver impostato tutto:

- Aspose.PDF per .NET: è necessario che la libreria Aspose.PDF per .NET sia installata nel progetto.
- [Scarica Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/)
- [Prova gratuita](https://releases.aspose.com/)
- Ambiente di sviluppo: assicurati di avere installato un IDE compatibile con .NET, come Visual Studio.
- Nozioni di base di C#: anche se spiegheremo tutto nei dettagli, una conoscenza di base di C# ti aiuterà a seguire il tutto senza problemi.
  
 Se non hai ancora Aspose.PDF per .NET, puoi ottenerne uno[licenza temporanea](https://purchase.aspose.com/temporary-license/) per iniziare a esplorarne le caratteristiche.

## Importa pacchetti

Per iniziare, devi importare i namespace necessari da Aspose.PDF per .NET. Ecco come fare:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Questi pacchetti forniscono le classi e i metodi essenziali richiesti per lavorare con documenti PDF e manipolare tabelle.

Ora, scomponiamo il processo in più passaggi per aggiungere colonne ripetute a un documento PDF. Seguiteci!

## Passaggio 1: imposta il percorso della directory dei documenti

Prima di creare o manipolare qualsiasi file, dobbiamo definire il percorso in cui verrà salvato il PDF generato. Nel tuo progetto C#, imposta il percorso della directory in cui saranno posizionati i tuoi file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Questo percorso punta alla directory in cui verrà salvato il PDF di output. Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della tua macchina.

## Passaggio 2: creare un nuovo documento PDF

 Per iniziare, crea un nuovo`Document` oggetto. Questo servirà da contenitore per tutte le pagine e i contenuti all'interno del PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Qui, abbiamo creato un nuovo documento PDF e vi abbiamo aggiunto una pagina vuota.`doc.Pages.Add()` Il metodo inserisce una nuova pagina nel documento.

## Passaggio 3: creare un'istanza della tabella esterna

Successivamente, creiamo una tabella esterna. Questa tabella coprirà l'intera larghezza della pagina e fungerà da contenitore per altre tabelle, inclusa quella che conterrà le colonne ripetute.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Abbiamo impostato il`ColumnWidths` proprietà su "100%", il che significa che la tabella si estenderà per tutta la larghezza della pagina.

## Passaggio 4: creare la tabella interna

 Ora creiamo la tabella interna, che avrà colonne ripetute. Le proprietà chiave qui sono`Broken` , che consente alla tabella di continuare sulla stessa pagina e`ColumnAdjustment`, che adatta automaticamente la larghezza delle colonne in base al contenuto.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Questa tabella interna sarà annidata nella tabella esterna.

## Passaggio 5: aggiungere tabelle alla pagina

Ora che abbiamo pronte sia le tabelle esterne che quelle interne, aggiungiamole alla pagina. Questo passaggio assicura che le tabelle siano incluse nella struttura del documento.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Qui abbiamo aggiunto il`outerTable` alla pagina, e poi all'interno della tabella esterna, abbiamo nidificato il`mytable` Inoltre, abbiamo impostato`RepeatingColumnsCount` 5, specificando quante colonne devono essere ripetute quando vengono aggiunti dati.

## Passaggio 6: aggiungere la riga di intestazione

Ora è il momento di aggiungere le intestazioni alla tabella. La riga di intestazione fornisce contesto ai dati e aiuta a strutturare le colonne. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Questo frammento di codice aggiunge la prima riga (che utilizzeremo come intestazioni) e la popola con celle contenenti testo come "intestazione 1", "intestazione 2" e così via.

## Passaggio 7: aggiungere righe di dati

Infine, possiamo aggiungere alcuni dati alla tabella. Questo ciclo crea dinamicamente righe e riempie le celle con il contenuto:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Il ciclo viene ripetuto sei volte, aggiungendo righe e riempiendo ogni cella con i dati delle colonne corrispondenti (ad esempio, "col 1, 1", "col 2, 2", ecc.).

## Passaggio 8: Salvare il documento

Una volta aggiunte tutte le righe e le colonne, l'ultimo passaggio consiste nel salvare il documento nel percorso file specificato.

```csharp
doc.Save(outFile);
```

Il tuo documento è ora salvato con colonne ripetute!

## Conclusione

Ecco fatto! Con questi semplici passaggi, puoi creare un documento PDF con colonne ripetute usando Aspose.PDF per .NET. Sfruttando la flessibilità delle tabelle nidificate, puoi ottenere layout complessi che rendono i tuoi PDF professionali e organizzati. Provalo per il tuo prossimo progetto ed esplora il pieno potenziale di Aspose.PDF per gestire le tue esigenze di generazione di PDF.

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e gestire documenti PDF a livello di programmazione.

### Posso modificare dinamicamente il numero di colonne ripetute?
 Sì, puoi modificare il numero di colonne ripetute modificando il`RepeatingColumnsCount` proprietà.

### Come posso applicare una licenza ad Aspose.PDF per .NET?
 È possibile applicare una licenza da un file o da un flusso seguendo le istruzioni[documentazione](https://reference.aspose.com/pdf/net/).

### È possibile aggiungere immagini alle celle della tabella?
Sì, Aspose.PDF per .NET supporta l'aggiunta di vari tipi di contenuto, tra cui immagini, alle celle della tabella.

### Posso personalizzare ulteriormente il layout della tabella?
Assolutamente! Aspose.PDF offre funzionalità estese per personalizzare gli stili delle tabelle, inclusi bordi, spaziatura, allineamento e altro ancora.