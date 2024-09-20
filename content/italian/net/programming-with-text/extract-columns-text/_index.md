---
title: Estrai testo colonne nel file PDF
linktitle: Estrai testo colonne nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre colonne di testo da file PDF usando Aspose.PDF per .NET. Questa guida suddivide ogni passaggio con esempi di codice e spiegazioni.
type: docs
weight: 150
url: /it/net/programming-with-text/extract-columns-text/
---
## Introduzione

Stai lavorando con file PDF e hai bisogno di estrarre testo in un formato di colonna specifico? Che tu stia elaborando fatture, report o documenti strutturati, estrarre testo in modo accurato da un PDF può essere un'attività complicata. È qui che entra in gioco Aspose.PDF per .NET per semplificare il processo. In questo tutorial, ti guideremo attraverso come estrarre colonne di testo da un file PDF con facilità. 

## Prerequisiti

Prima di immergerci nel codice, vediamo gli elementi essenziali di cui avrai bisogno:

-  Aspose.PDF per .NET: assicurati di avere installata l'ultima versione di Aspose.PDF per .NET. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).
- Ambiente di sviluppo: per lavorare con il codice sarà necessario Visual Studio o un altro ambiente di sviluppo .NET.
- Documento PDF: tieni a portata di mano un documento PDF di esempio, preferibilmente con colonne di testo, poiché estrarremo il testo da esso.

 Se non hai ancora installato Aspose.PDF per .NET, puoi scaricarlo[prova gratuita](https://releases.aspose.com/) O[acquistare una licenza](https://purchase.aspose.com/buy) per le funzionalità complete. Puoi anche richiedere un[licenza temporanea](https://purchase.aspose.com/temporary-license) se necessario.

## Importazione degli spazi dei nomi

Per utilizzare Aspose.PDF per .NET nel tuo progetto, dovrai importare i seguenti namespace:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Guida passo passo: estrai colonne di testo da un PDF

Ora, scomponiamo ogni parte del codice per capire meglio come funziona. Seguiteci passo dopo passo, spiegando ogni segmento del processo.

## Passaggio 1: caricare il documento PDF

 La prima cosa che devi fare è caricare il tuo file PDF nel`Document`oggetto. Ecco come Aspose.PDF interagisce con il tuo documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 In questo passaggio, stiamo semplicemente definendo la directory in cui è archiviato il tuo documento PDF. Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso al tuo file PDF locale. Il`Document` L'oggetto carica il PDF nella memoria, rendendolo accessibile per ulteriori elaborazioni.

## Passaggio 2: impostare l'assorbitore di frammenti di testo

 Successivamente, useremo un`TextFragmentAbsorber` per assorbire o catturare tutto il testo dal file PDF. Questa classe di assorbitori è progettata per estrarre frammenti di testo da aree specifiche del tuo PDF, il che la rende ideale per estrarre colonne di testo.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Qui creiamo un'istanza di`TextFragmentAbsorber` e applicarlo a tutte le pagine del PDF utilizzando`Accept()` . IL`TextFragmentCollection` memorizza il testo estratto e da questa raccolta possiamo manipolare o estrarre il testo a seconda delle nostre esigenze.

## Passaggio 3: regola la dimensione del carattere del testo estratto

Una volta catturati i frammenti di testo, potresti voler ridurre la dimensione del carattere, specialmente quando il testo originale è troppo grande. In questo esempio, stiamo riducendo la dimensione del carattere del 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Riduci la dimensione del carattere del 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Questo codice esegue un ciclo attraverso ciascuno`TextFragment` nella raccolta e ne riduce la dimensione del carattere del 70%. Regolando la dimensione del carattere è possibile rendere il testo estratto più facile da gestire, soprattutto se lo si formatta per scopi diversi.

## Passaggio 4: salvare il documento in un flusso di memoria

 Dopo aver modificato il testo, salviamo il PDF in un`MemoryStream`Ciò ci consente di conservare il documento in memoria per un'ulteriore elaborazione senza doverlo riscrivere sul disco.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Qui salviamo il PDF in un flusso di memoria e poi ricarichiamo il documento. Questo metodo è utile quando si lavora con file di grandi dimensioni e si vogliono evitare operazioni non necessarie sul disco.

## Passaggio 5: estrai tutto il testo utilizzando Text Absorber

 Ora che abbiamo preparato il PDF, è il momento di estrarre il testo. Useremo`TextAbsorber` per acquisire tutto il testo dal documento.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 In questa fase, il`TextAbsorber` assorbe tutto il testo dal PDF e il testo estratto viene memorizzato nel`extractedText` stringa. È qui che avviene la magia: le tue colonne di testo sono ora in formato testo normale!

## Passaggio 6: salvare il testo estratto in un file

 Infine, salviamo il testo estratto in un`.txt` file per un facile accesso e un ulteriore utilizzo.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Questo codice scrive il testo estratto in un nuovo`.txt` file e lo salva nella directory specificata. Un messaggio viene visualizzato nella console per confermare che il processo è riuscito.

## Conclusione

Ecco fatto! Estrarre colonne di testo da un file PDF usando Aspose.PDF per .NET è più facile di quanto si possa pensare. Con solo poche righe di codice, è possibile caricare un PDF, estrarre testo specifico, modificare la formattazione e salvare i risultati in un file di testo.

Questa tecnica è incredibilmente utile per elaborare documenti strutturati come tabelle, report o qualsiasi contenuto organizzato in colonne. Che tu abbia bisogno di automatizzare l'estrazione dei dati o elaborare documenti in blocco, Aspose.PDF fornisce gli strumenti per farlo in modo efficiente.

## Domande frequenti

### Posso estrarre il testo da pagine specifiche di un PDF?  
 Sì! Puoi modificare il`TextFragmentAbsorber` per indirizzare pagine specifiche utilizzando il`pdfDocument.Pages[pageIndex].Accept(tfa);` metodo.

### È possibile estrarre il testo da una sola colonna in un PDF multicolonna?  
 Sì, ma dovrai lavorare con le coordinate dei frammenti di testo utilizzando`TextFragment.Rectangle` per concentrarsi su aree specifiche del documento.

### Come posso migliorare la precisione dell'estrazione del testo?  
 Per una migliore accuratezza, assicurati che la struttura del PDF sia ben definita ed evita documenti con layout complessi. Puoi anche perfezionare il`TextFragmentAbsorber` per estrarre testo in base a stili, dimensioni o regioni del carattere.

### Aspose.PDF supporta l'estrazione di testo da documenti scansionati?  
Sì, ma dovrai usare la tecnologia OCR (Optical Character Recognition). Aspose fornisce anche strumenti per questo.

### Come posso gestire file PDF di grandi dimensioni con migliaia di pagine?  
Per i PDF di grandi dimensioni, elaborare il documento in blocchi estraendo il testo da poche pagine alla volta per evitare un utilizzo elevato di memoria.