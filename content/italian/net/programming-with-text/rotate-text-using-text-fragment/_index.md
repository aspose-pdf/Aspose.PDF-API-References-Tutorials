---
title: Ruota il testo utilizzando il frammento di testo nel file PDF
linktitle: Ruota il testo utilizzando il frammento di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come ruotare il testo nei file PDF usando Aspose.PDF per .NET con una guida passo-passo. Scopri le tecniche di manipolazione del testo, dal posizionamento alla rotazione.
type: docs
weight: 390
url: /it/net/programming-with-text/rotate-text-using-text-fragment/
---
## Introduzione

Creare PDF è una cosa, ma manipolarli per soddisfare requisiti specifici? È lì che avviene la vera magia! Ti sei mai chiesto come ruotare il testo in un PDF? Che tu stia generando report o creando un documento con un design personalizzato, ruotare frammenti di testo può rendere i tuoi PDF più accattivanti visivamente. In questo tutorial, esploreremo come ruotare il testo utilizzando Aspose.PDF per .NET, una potente libreria che consente una manipolazione fluida dei documenti PDF.

## Prerequisiti

Prima di passare al codice, passiamo rapidamente in rassegna gli strumenti e le impostazioni di cui avrai bisogno. Vuoi che tutto sia pronto, così puoi seguire senza sforzo.

### Aspose.PDF per la libreria .NET
Per prima cosa, avrai bisogno di Aspose.PDF per .NET installato nel tuo progetto. Questa libreria è piena di funzionalità per aiutarti a creare, modificare e gestire file PDF a livello di programmazione. Se non l'hai ancora scaricata, ecco dove trovarla:
- [Scarica Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/)

Per questo tutorial, assicurati di utilizzare la versione più recente della libreria.

### Ambiente di sviluppo
Avrai anche bisogno di un ambiente di sviluppo .NET come Visual Studio. È l'IDE di riferimento per lo sviluppo C# e renderà la tua esperienza di programmazione fluida ed efficiente.

### Licenza temporanea o completa
Sebbene tu possa iniziare con una prova gratuita di Aspose.PDF, se vuoi evitare limitazioni, è meglio usare una licenza temporanea o completa. Ecco come puoi ottenerne una:
- [Prova gratuita](https://releases.aspose.com/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Acquista la licenza completa](https://purchase.aspose.com/buy)

Una volta che hai acquisito tutti questi elementi essenziali, possiamo andare avanti!

## Importa pacchetti

Prima di iniziare a scrivere codice, devi importare i namespace necessari forniti con Aspose.PDF. Questo è fondamentale per lavorare con documenti, pagine, frammenti di testo e altro. Aggiungi il seguente codice all'inizio del tuo file C#:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

Ora analizziamo passo dopo passo il codice di esempio, così potrai ruotare il testo come un professionista!

## Passaggio 1: inizializzare l'oggetto documento

Ogni manipolazione PDF inizia con la creazione o il caricamento di un documento PDF. Qui, inizializzeremo un nuovo documento PDF da zero usando Aspose.PDF.

 Stiamo creando un nuovo`Document` oggetto che rappresenta il file PDF. Inizialmente, questo documento è vuoto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inizializza l'oggetto documento
Document pdfDocument = new Document();
```

Spiegazione:  
- `dataDir`: Questa è la directory in cui verrà salvato il PDF finale.
- `Document pdfDocument = new Document();`: Questo inizializza un nuovo documento PDF vuoto. 

## Passaggio 2: aggiungere una pagina al documento

Poi, dobbiamo aggiungere una pagina al documento. Un PDF è fondamentalmente una raccolta di pagine e hai bisogno di almeno una pagina per aggiungere il tuo contenuto.

```csharp
// Ottieni una pagina specifica
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Senza aggiungere una pagina, non c'è una tela su cui disegnare o posizionare il testo!

## Passaggio 3: creare il primo frammento di testo

Ora arriva la parte emozionante! Aggiungiamo un frammento di testo al PDF. Un frammento di testo è un pezzo di testo con proprietà specifiche come font, dimensione e posizione.

```csharp
// Crea frammento di testo
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment("main text"): crea un nuovo frammento di testo con il contenuto "main text".
- Position(100, 600): Definisce la posizione del testo sulla pagina. Il primo numero è la coordinata x, e il secondo è la coordinata y.
- TextState.FontSize: imposta la dimensione del carattere del testo.
- FontRepository.FindFont: trova il font specificato da applicare al testo.

## Passaggio 4: creare i frammenti di testo ruotati

Aggiungiamo altri frammenti di testo, ma questa volta li ruoteremo in angolazioni diverse!

### Rotazione del frammento di testo a 45 gradi

```csharp
// Crea frammento di testo ruotato
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

Qui, il cambiamento fondamentale è:
- TextState.Rotation: questa proprietà imposta l'angolo di rotazione del frammento di testo e, in questo caso, è di 45 gradi.

### Rotazione del frammento di testo a 90 gradi

```csharp
// Crea frammento di testo ruotato
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

In questo caso la rotazione è di 90 gradi.

## Passaggio 5: aggiungere frammenti di testo alla pagina PDF

Ora che abbiamo pronti tutti i frammenti di testo, è il momento di aggiungerli alla pagina PDF utilizzando la classe TextBuilder.

```csharp
// crea oggetto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Aggiungere il frammento di testo alla pagina PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

La classe TextBuilder consente di aggiungere più frammenti di testo a una singola pagina, offrendoti la flessibilità di manipolarli individualmente.

## Passaggio 6: Salvare il documento PDF

Infine, salva il documento nella directory specificata. Senza questo passaggio, tutto il tuo duro lavoro svanirà nel nulla!

```csharp
// Salvare il documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Hai ruotato con successo il testo in un file PDF usando Aspose.PDF per .NET. Ora puoi aprire il PDF per visualizzare i frammenti di testo ruotati!

## Conclusione

La rotazione del testo in un PDF può aggiungere un tocco professionale ai tuoi documenti, rendendoli visivamente accattivanti e unici. Con Aspose.PDF per .NET, è incredibilmente facile manipolare frammenti di testo, dandoti il controllo completo su come appare il tuo contenuto. Ora che hai imparato a ruotare il testo, puoi sperimentare diverse angolazioni e layout per soddisfare le esigenze del tuo progetto.

## Domande frequenti

### Posso ruotare frammenti di testo in qualsiasi angolazione?
 Sì! Puoi impostare il`TextState.Rotation` proprietà in qualsiasi grado (anche angoli negativi) per ruotare il testo secondo necessità.

### Posso usare font diversi per ogni frammento di testo?
 Assolutamente. Puoi personalizzare il font di ogni frammento di testo usando`FontRepository.FindFont` e passa il font che vuoi applicare.

### Aspose.PDF supporta i PDF multipagina?
Sì, puoi aggiungere più pagine al tuo documento PDF e manipolare ogni pagina in modo indipendente.

### C'è un limite al numero di frammenti di testo che posso aggiungere?
No, puoi aggiungere tutti i frammenti di testo che vuoi. Assicurati solo che siano posizionati correttamente sulla pagina.

### Posso modificare frammenti di testo dopo averli aggiunti?
Sì, una volta aggiunto un frammento di testo, puoi comunque aggiornarne le proprietà o rimuoverlo dalla pagina.