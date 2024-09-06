---
title: Estrai il testo evidenziato nel file PDF
linktitle: Estrai il testo evidenziato nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre in modo efficiente il testo evidenziato da un file PDF usando Aspose.PDF per .NET con questo tutorial. Perfetto per l'analisi dei dati e la revisione dei contenuti.
type: docs
weight: 60
url: /it/net/annotations/extracthighlightedtext/
---
## Introduzione

Quando si lavora con file PDF, estrarre il testo evidenziato può essere un compito cruciale, sia per l'analisi dei dati, la revisione dei contenuti o semplicemente l'organizzazione delle note. Se si utilizza Aspose.PDF per .NET, questo processo è semplice ed efficiente. In questo tutorial, ti guideremo attraverso l'estrazione del testo evidenziato da un documento PDF utilizzando Aspose.PDF per .NET. Tratteremo tutto, dai prerequisiti alla guida passo dopo passo, assicurandoti di avere una comprensione completa alla fine.

## Prerequisiti

Prima di immergerti nel codice, ecco alcune cose che devi sapere:

-  Aspose.PDF per la libreria .NET: assicurati di avere la libreria Aspose.PDF installata. In caso contrario, puoi scaricarla da[pagina di rilascio](https://releases.aspose.com/pdf/net/).
- Ambiente di sviluppo: dovresti avere un ambiente di sviluppo funzionante, come Visual Studio.
- Conoscenza di base di C#: è essenziale avere familiarità con il linguaggio di programmazione C# e con la programmazione orientata agli oggetti.
-  Una licenza Aspose valida: sebbene tu possa iniziare con una prova gratuita, prendi in considerazione l'idea di ottenere una[licenza temporanea](https://purchase.aspose.com/temporary-license/) o acquistandone uno da[Qui](https://purchase.aspose.com/buy) per un utilizzo senza restrizioni.

## Importa pacchetti

Per iniziare, devi importare i namespace necessari nel tuo progetto C#. Questo è fondamentale per accedere alle classi e ai metodi forniti da Aspose.PDF per .NET.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora, analizziamo il processo di estrazione del testo evidenziato da un file PDF usando Aspose.PDF per .NET. Ogni passaggio è spiegato in dettaglio per aiutarti a comprendere i concetti e l'implementazione sottostanti.

## Passaggio 1: imposta la directory del progetto

Per prima cosa, devi impostare la directory del progetto in cui si trova il tuo file PDF. È qui che avviene la magia.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo alla directory in cui risiede il file PDF. Questa directory è dove l'applicazione recupererà il PDF per l'elaborazione.

## Passaggio 2: caricare il documento PDF

 Successivamente, devi caricare il documento PDF da cui vuoi estrarre il testo evidenziato. Questo viene fatto usando il`Document` classe fornita da Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 IL`Document` la classe viene istanziata con il percorso al file PDF. Qui,`"ExtractHighlightedText.pdf"` è il nome del file PDF che contiene il testo evidenziato. Assicurati che questo file esista nella directory specificata.

## Passaggio 3: accedi alla raccolta di annotazioni

Una volta caricato il documento PDF, il passo successivo è accedere alle annotazioni sulla prima pagina del documento. Le annotazioni vengono utilizzate nei PDF per aggiungere informazioni aggiuntive come evidenziazioni, commenti e altro.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 IL`Annotations` proprietà del`Page` object fornisce accesso a tutte le annotazioni su una pagina specifica del PDF. Qui, stiamo scorrendo ogni annotazione sulla prima pagina.

## Passaggio 4: filtro per annotazioni di testo evidenziate

Ora che abbiamo accesso a tutte le annotazioni, dobbiamo filtrare solo le annotazioni di testo evidenziate. Questo si ottiene controllando il tipo di ogni annotazione.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 IL`TextMarkupAnnotation` La classe viene utilizzata per rappresentare annotazioni di markup di testo, comprese le evidenziazioni. La`is` la parola chiave controlla se l'annotazione è di tipo`TextMarkupAnnotation` e, se lo è, converte l'annotazione in`TextMarkupAnnotation`.

## Passaggio 5: estrai il testo evidenziato

Una volta identificata l'annotazione evidenziata, il passo successivo consiste nell'estrarre il testo associato all'evidenziazione.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 IL`GetMarkedTextFragments()` il metodo restituisce una raccolta di`TextFragment` oggetti, ognuno dei quali rappresenta una porzione del testo evidenziato. Eseguiamo un ciclo attraverso questa raccolta e stampiamo il testo di ogni frammento sulla console.

## Conclusione

L'estrazione di testo evidenziato da un PDF tramite Aspose.PDF per .NET è una potente funzionalità che può semplificare il flusso di lavoro, soprattutto se si gestiscono documenti di grandi dimensioni. Seguendo i passaggi descritti in questo tutorial, è possibile implementare facilmente questa funzionalità nei propri progetti. Che si stiano organizzando appunti, preparando report o conducendo analisi di dati, questo metodo offre una soluzione fluida per estrarre e utilizzare testo evidenziato.

## Domande frequenti

### Posso estrarre altri tipi di annotazioni utilizzando questo metodo?  
 Sì, puoi estrarre altri tipi di annotazioni modificando il`if` condizione per controllare diversi tipi di annotazione, come ad esempio`TextAnnotation`, `StampAnnotation`, ecc.

### È possibile estrarre il testo evidenziato da tutte le pagine del PDF?  
Assolutamente! Puoi scorrere ogni pagina del documento PDF e applicare la stessa logica di estrazione per raccogliere il testo evidenziato da ogni pagina.

### Ho bisogno di una licenza per utilizzare Aspose.PDF per .NET?  
 Sebbene sia possibile iniziare con una prova gratuita, si consiglia di ottenere una[licenza temporanea](https://purchase.aspose.com/temporary-license/)oppure acquista una licenza completa per un accesso illimitato a tutte le funzionalità.

### Posso salvare il testo estratto in un file invece di stamparlo sulla console?  
Sì, puoi facilmente modificare il codice per salvare il testo estratto in un file di testo o in qualsiasi altro formato desiderato.

### Aspose.PDF supporta anche altre piattaforme oltre a .NET?  
Sì, Aspose.PDF supporta anche Java e altre piattaforme, offrendo funzionalità simili in diversi ambienti.