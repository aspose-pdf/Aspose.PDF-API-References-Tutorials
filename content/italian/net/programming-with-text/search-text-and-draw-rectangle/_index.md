---
title: Cerca testo e disegna rettangolo
linktitle: Cerca testo e disegna rettangolo
second_title: Riferimento API Aspose.PDF per .NET
description: Impara a cercare testo nei PDF ed evidenziarlo con rettangoli usando Aspose.PDF per .NET! Semplice tutorial passo dopo passo per migliorare le tue capacità di manipolazione dei PDF.
type: docs
weight: 460
url: /it/net/programming-with-text/search-text-and-draw-rectangle/
---
## Introduzione

Stai cercando di migliorare le tue capacità di manipolazione PDF? Vuoi imparare a cercare testo specifico nei file PDF ed evidenziarlo con un rettangolo? Hai trovato la guida perfetta! Oggi ti guiderò attraverso l'uso di Aspose.PDF per .NET per cercare testo in un documento PDF e disegnare rettangoli attorno ad esso. Questo articolo fornirà un tutorial passo dopo passo progettato con chiarezza e utilità in mente, assicurandoti di poter seguire e applicare queste tecniche ai tuoi progetti. 

## Prerequisiti

Prima di immergerci nel tutorial, prepariamo il necessario per garantire un flusso di lavoro fluido:

1. Nozioni di base di .NET: per seguire questo tutorial in modo efficace è necessario avere familiarità con la programmazione C# e con il framework .NET.
   
2. Visual Studio installato: avrai bisogno di un ambiente di sviluppo integrato (IDE) per scrivere e testare il tuo codice. Visual Studio Community è un'ottima opzione, ed è gratuito.
   
3. Aspose.PDF per .NET: devi avere la libreria Aspose.PDF installata nel tuo progetto. Puoi scaricarla[Qui](https://releases.aspose.com/pdf/net/) o considera un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per funzionalità estese.
   
4.  Esempio di documento PDF: per questo tutorial, avrai bisogno di un file PDF di esempio denominato`SearchAndGetTextFromAll.pdf` memorizzati nella directory del progetto. 

## Importa pacchetti

Per iniziare, dovrai prima importare i pacchetti necessari nel tuo progetto .NET. Segui questi passaggi:

### Apri Visual Studio

Avvia Visual Studio e crea una nuova applicazione console oppure utilizzane una esistente in cui desideri implementare le funzionalità PDF.

### Aggiungi Aspose.PDF al tuo progetto

1. Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni.
2. Seleziona "Gestisci pacchetti NuGet".
3.  Cercare`Aspose.PDF` e installare la versione più recente.

In questo modo, porrai le basi per tutte le straordinarie manipolazioni PDF che stai per eseguire.

## Importazione degli spazi dei nomi

Nella parte superiore del file di programma, dovrai importare gli spazi dei nomi rilevanti dalla libreria Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

In questo modo sarà più semplice accedere alle classi e ai metodi all'interno della libreria Aspose.PDF per le tue attività.


Ora che hai impostato tutto, scomponiamo il processo di ricerca del testo in un PDF e di tracciamento di un rettangolo attorno ad esso in passaggi gestibili.

## Passaggio 1: imposta il percorso per il documento

 Per prima cosa, imposta il percorso del tuo file PDF. Assicurati di sostituire`YOUR DOCUMENT DIRECTORY` con il percorso effettivo in cui ti trovi`SearchAndGetTextFromAll.pdf` è memorizzato.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: aprire il documento PDF

 Quindi, crea un'istanza di`Document` classe per caricare il tuo PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Questa riga di codice apre il file PDF specificato, consentendoti di modificarlo ulteriormente.

## Passaggio 3: creare un assorbitore di testo

 Ora, avrai bisogno di un modo per cercare il testo all'interno di quel documento. Per questo, utilizziamo il`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 L'espressione regolare`@"[\S]+"` è progettato per corrispondere a qualsiasi stringa senza spazi vuoti nel PDF. 

## Passaggio 4: configurare le opzioni di ricerca del testo

Successivamente, dovresti impostare le opzioni di ricerca del testo:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Qui, il`true` parametro significa che la ricerca sarà sensibile alle maiuscole/minuscole. Puoi impostarlo su`false` se si desidera una ricerca senza distinzione tra maiuscole e minuscole.

## Passaggio 5: accettare l'assorbitore di testo nel documento

 Con il tuo`TextFragmentAbsorber` e le opzioni di ricerca sono pronte, è il momento di assorbire il testo dal documento:

```csharp
document.Pages.Accept(textAbsorber);
```

Questo metodo esamina ogni pagina del PDF per trovare frammenti di testo che corrispondono al modello specificato.

## Passaggio 6: creare un PdfContentEditor

 Per disegnare forme sul documento, avrai bisogno di`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Questo editor consente di manipolare e modificare facilmente il contenuto del PDF.

## Passaggio 7: scorrere i frammenti di testo trovati

Ora, dovrai scorrere i frammenti di testo trovati per disegnare dei rettangoli attorno a essi:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Questo ciclo esegue un'iterazione su ogni frammento di testo e sui relativi segmenti, chiamando un`DrawBox` metodo per disegnare rettangoli.

## Passaggio 8: definire il metodo DrawBox

 Devi definire il`DrawBox` metodo, che gestirà la logica di disegno del rettangolo. Ecco una semplice implementazione:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Calcola le dimensioni del rettangolo in base al segmento di testo
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Disegna un rettangolo utilizzando i valori calcolati
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Questo metodo determina la posizione e la dimensione del rettangolo in base al rettangolo di delimitazione del segmento e utilizza l'editor per disegnarlo.

## Passaggio 9: Salvare il documento modificato

Dopo aver disegnato i rettangoli attorno al testo trovato, puoi salvare il documento modificato:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Assicuratevi che il nuovo file venga salvato con un nome diverso per evitare di sovrascrivere il documento originale.

## Passaggio 10: messaggio di conferma

Infine, visualizza un messaggio di conferma sulla console per informarti che l'operazione è riuscita:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Ed ecco fatto! Hai creato con successo uno script per cercare testo in un PDF ed evidenziarlo con rettangoli.

## Conclusione

Congratulazioni! Hai appena sbloccato una potente abilità che può migliorare notevolmente le tue capacità di manipolazione PDF usando Aspose.PDF per .NET. Con pochi semplici passaggi, puoi cercare qualsiasi testo nel tuo documento ed evidenziarlo visivamente, rendendo i tuoi documenti PDF più interattivi e gestibili. Non esitare a sperimentare diversi modelli di espressioni regolari e opzioni di colore per rendere davvero tuo questo strumento!

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una libreria che fornisce un modo completo per creare, manipolare e convertire documenti PDF a livello di programmazione.

### Posso usare Aspose.PDF gratuitamente?
Sì, Aspose offre una prova gratuita che puoi usare per testare le funzionalità della libreria. Dai un'occhiata[Qui](https://releases.aspose.com/).

### Quale linguaggio di programmazione devo usare con Aspose.PDF per .NET?
Aspose.PDF per .NET è progettato per essere utilizzato con C# e altri linguaggi .NET.

### Come posso ottenere assistenza con Aspose.PDF?
 Puoi visitare il forum di supporto Aspose per ricevere assistenza su qualsiasi problema o domanda tu possa avere. Trova supporto[Qui](https://forum.aspose.com/c/pdf/10).

### Dove posso scaricare Aspose.PDF per .NET?
 È possibile scaricare la libreria dal sito web di Aspose,[Qui](https://releases.aspose.com/pdf/net/).