---
title: Personalizza i numeri di pagina durante l'aggiunta del sommario
linktitle: Personalizza i numeri di pagina durante l'aggiunta del sommario
second_title: Riferimento API Aspose.PDF per .NET
description: In questo tutorial completo scoprirai come personalizzare i numeri di pagina aggiungendo un indice ai tuoi documenti PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Introduzione

Nel mondo della gestione dei documenti, i PDF regnano sovrani. Sono il formato di riferimento per la condivisione e la conservazione dei documenti su diverse piattaforme. Ma cosa succede quando vuoi migliorare i tuoi documenti PDF con funzionalità come un indice (TOC)? Ecco dove entra in gioco Aspose.PDF per .NET! Questa potente libreria consente agli sviluppatori di manipolare i file PDF con facilità, consentendo loro di aggiungere, modificare e personalizzare i contenuti senza sforzo. In questo tutorial, approfondiremo come personalizzare i numeri di pagina aggiungendo un indice ai tuoi documenti PDF utilizzando Aspose.PDF per .NET. Quindi, prendi il tuo cappello da programmatore e iniziamo!

## Prerequisiti

Prima di passare al codice, ecco alcune cose che devi sapere:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Questo sarà il nostro ambiente di sviluppo.
2. Aspose.PDF per .NET: devi scaricare e installare la libreria Aspose.PDF. Puoi trovarla[Qui](https://releases.aspose.com/pdf/net/).
3. Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a comprendere meglio i frammenti di codice.
4. Un file PDF di esempio: tieni pronto un file PDF di esempio con cui possiamo lavorare. Puoi crearne uno semplice o scaricare un PDF esistente.

## Importa pacchetti

Per iniziare, dobbiamo importare i pacchetti necessari. Apri il tuo progetto Visual Studio e aggiungi un riferimento alla libreria Aspose.PDF. Puoi farlo usando NuGet Package Manager:

1. Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni.
2. Seleziona "Gestisci pacchetti NuGet".
3. Cerca "Aspose.PDF" e installalo.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Una volta installata la libreria, puoi iniziare a programmare!

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, dobbiamo impostare la nostra directory dei documenti. È qui che memorizzeremo i nostri file PDF di input e output. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

In questo frammento, sostituisci`YOUR DOCUMENT DIRECTORY` con il percorso effettivo in cui si trovano i tuoi file PDF. Questo ci aiuterà a caricare il PDF esistente e a salvare la versione modificata.

## Passaggio 2: caricare il file PDF esistente

Ora che abbiamo impostato la directory dei documenti, carichiamo il file PDF esistente. 

```csharp
Document doc = new Document(inFile);
```

 Qui creiamo un nuovo`Document` oggetto passando il percorso del file di input. Questo ci consente di manipolare il contenuto PDF a livello di programmazione.

## Passaggio 3: inserire una nuova pagina per il sommario

Ora dobbiamo creare una nuova pagina nel nostro PDF in cui inserire l'indice.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Questa riga inserisce una nuova pagina all'inizio del documento. Il TOC verrà visualizzato su questa pagina.

## Passaggio 4: creare le informazioni del sommario

Ora creiamo un oggetto per rappresentare le informazioni dell'indice.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 In questo passaggio creiamo un`TocInfo` oggetto e impostare il suo titolo su "Indice". Personalizziamo anche la dimensione e lo stile del carattere. Il`PageNumbersPrefix` è impostato su "P", che verrà aggiunto come anteposto ai numeri di pagina nell'indice.

## Passaggio 5: aggiungere titoli al sommario

Ora arriva la parte divertente! Faremo un ciclo tra le pagine del documento e aggiungeremo titoli al nostro TOC.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 In questo ciclo, creiamo un nuovo`Heading` oggetto per ogni pagina. Impostiamo la pagina di destinazione per ogni intestazione e specifichiamo il testo da visualizzare, che è "Pagina X" dove X è il numero di pagina. Infine, aggiungiamo l'intestazione alla pagina TOC.

## Passaggio 6: salvare il documento aggiornato

Dopo aver aggiunto tutte le intestazioni necessarie, è il momento di salvare il nostro documento aggiornato.

```csharp
doc.Save(outFile);
```

Questa riga salva il PDF modificato con il TOC incluso. Ora puoi aprire il file di output e vedere il tuo indice personalizzato!

## Conclusione

Ed ecco fatto! Hai personalizzato con successo i numeri di pagina aggiungendo un indice al tuo documento PDF usando Aspose.PDF per .NET. Questa potente libreria semplifica la manipolazione dei file PDF e, con solo poche righe di codice, puoi migliorare notevolmente i tuoi documenti. Che tu stia creando report, eBook o qualsiasi altro tipo di PDF, avere un indice può migliorare notevolmente la navigazione per i tuoi lettori. Quindi, cosa aspetti? Immergiti in Aspose.PDF e inizia a creare PDF straordinari oggi stesso!

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una libreria che consente agli sviluppatori di creare, manipolare e convertire documenti PDF a livello di programmazione.

### Posso usare Aspose.PDF gratuitamente?
 Sì, Aspose offre una versione di prova gratuita che puoi usare per esplorare le funzionalità della libreria. Puoi scaricarla[Qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.PDF?
 Puoi ottenere supporto visitando il forum Aspose[Qui](https://forum.aspose.com/c/pdf/10).

### È disponibile una licenza temporanea?
 Sì, puoi richiedere una licenza temporanea per Aspose.PDF[Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare Aspose.PDF per .NET?
 Puoi acquistare Aspose.PDF per .NET[Qui](https://purchase.aspose.com/buy).