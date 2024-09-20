---
title: Specificare la spaziatura delle righe nel file PDF
linktitle: Specificare la spaziatura delle righe nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come specificare la spaziatura delle linee in un PDF usando Aspose.PDF per .NET con questa guida passo-passo. Perfetta per gli sviluppatori che cercano una formattazione precisa del testo.
type: docs
weight: 510
url: /it/net/programming-with-text/specify-line-spacing/
---
## Introduzione

Hai mai avuto difficoltà a controllare la spaziatura delle linee in un file PDF? Forse hai avuto del testo che sembrava troppo ammassato o semplicemente non sembrava così rifinito come vorresti. In questo tutorial, ti mostreremo come puoi specificare facilmente la spaziatura delle linee in un PDF usando Aspose.PDF per .NET. Utilizzeremo una semplice guida passo dopo passo per portarti da un PDF vuoto a uno che include la spaziatura delle linee personalizzata. Questo è perfetto se hai bisogno di precisione nel layout del testo per documenti come report, fatture o certificati.

## Prerequisiti

Prima di passare al codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.PDF per .NET installato. Se non lo hai, scaricalo da[Pagina di download di Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. Un ambiente di sviluppo .NET (come Visual Studio).
3. Un file di font TrueType (`.ttf` ) che useremo nell'esempio. Puoi usare qualsiasi font, ma per questa guida useremo il`HPSimplified.TTF` font.
4. Conoscenza di base di C# e manipolazione PDF.

Se sei pronto, passiamo all'importazione dei pacchetti necessari.

## Importa pacchetti

Nel tuo progetto C#, dovrai importare gli spazi dei nomi Aspose.PDF per lavorare con le funzionalità PDF. Ecco come fare:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Questi namespace consentono di creare e manipolare documenti PDF, nonché di lavorare con la formattazione del testo e le opzioni dei caratteri.

Suddivideremo il tutto in piccoli passaggi, così potrai seguirli facilmente. Ogni passaggio si concentrerà su una parte fondamentale del processo, dall'impostazione del PDF alla specificazione della spaziatura delle righe.

## Passaggio 1: imposta il tuo progetto e definisci la directory dei documenti

La prima cosa che dobbiamo fare è definire dove si trovano i nostri file. Questo aiuta il programma a sapere dove trovare il font e dove salvare il PDF risultante.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 In questo passaggio sostituirai`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui memorizzi i tuoi file. Questo sarà il posto in cui posizionerai il tuo file font (`HPSimplified.TTF`) e dove verrà salvato il PDF.

## Passaggio 2: carica un documento PDF

Ora, dobbiamo creare un nuovo documento PDF. Per questa guida, inizieremo con un documento vuoto, ma puoi anche caricare un PDF esistente se necessario.

```csharp
Document doc = new Document();
```

Questo crea un nuovo documento PDF vuoto. Facile, vero?

## Passaggio 3: imposta le opzioni di formattazione del testo

 Ecco dove avviene la magia. Specifichiamo la modalità di spaziatura delle linee per il testo che vogliamo aggiungere al PDF. Aspose.PDF ci offre diverse opzioni, ma in questa guida useremo`LineSpacingMode.FullSize`, che garantisce il pieno rispetto della spaziatura delle righe.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Questo codice imposta la modalità di spaziatura delle linee su`FullSize` , assicurando che il testo venga visualizzato con la spaziatura corretta. Ci sono altre opzioni come`Proportional` se vuoi comportamenti di spaziatura diversi, ma per ora, atteniamoci a`FullSize`.

## Passaggio 4: creare un frammento di testo

Ora creeremo il testo effettivo che verrà inserito nel PDF. Questo testo rispetterà la spaziatura delle righe che abbiamo definito.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Abbiamo creato un frammento di testo con la stringa`"Hello world"`Naturalmente puoi personalizzare questo testo come preferisci.

## Passaggio 5: Carica e applica un font personalizzato

Per far risaltare il testo, caricheremo un font TrueType personalizzato da un file. Questo passaggio è facoltativo, ma può aggiungere un tocco professionale ai tuoi PDF.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Qui, carichiamo il file font e lo applichiamo al frammento di testo. Se il percorso del file è valido, il font viene utilizzato. Altrimenti, viene applicato il font predefinito.

## Passaggio 6: imposta la posizione e la formattazione del testo

Poi, dobbiamo posizionare il testo sul PDF. Applicheremo anche le opzioni di formattazione che abbiamo creato in precedenza.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 IL`Position` imposta le coordinate in cui il testo apparirà sulla pagina (in questo caso, 100 unità da sinistra e 600 unità dal basso). Le opzioni di formattazione, inclusa la modalità di spaziatura delle linee, vengono applicate qui.

## Passaggio 7: aggiungere testo alla pagina PDF

Ora che il testo è formattato e posizionato, è il momento di aggiungerlo al documento PDF.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Questo codice crea una nuova pagina nel documento PDF e vi aggiunge il frammento di testo.

## Passaggio 8: Salva il PDF

Siamo arrivati al passaggio finale! Ora che tutto è impostato, salviamo il PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

In questo modo il PDF verrà salvato con la spaziatura specificata e il file sarà pronto!

## Conclusione

Ed ecco fatto! Hai appena creato un documento PDF con spaziatura personalizzata usando Aspose.PDF per .NET. È uno strumento potente che ti consente di controllare ogni aspetto dei tuoi file PDF, e questo è solo un esempio di ciò che puoi ottenere. Dal posizionamento del testo alla formattazione, le possibilità sono infinite.

Se stai cercando di approfondire la manipolazione dei PDF, Aspose.PDF offre una vasta gamma di funzionalità da esplorare. Non esitare a sperimentare e a spingere i limiti di ciò che puoi fare con i tuoi documenti!

## Domande frequenti

### Posso adattare la spaziatura delle linee ad altre modalità?  
 Sì, puoi usare altre modalità come`Proportional` O`Fixed` a seconda delle vostre esigenze.

### È possibile caricare i font dal sistema invece che da un file?  
 Sì, puoi caricare i font installati nel sistema utilizzando`FontRepository`.

### Posso usare Aspose.PDF per .NET con altri formati di file?  
Assolutamente! Aspose.PDF per .NET supporta una varietà di formati come XML, HTML e altro ancora.

### Ho bisogno di una licenza per utilizzare Aspose.PDF per .NET?  
Sì, per la piena funzionalità, avrai bisogno di una licenza, che puoi ottenere[Qui](https://purchase.aspose.com/buy).

### Come faccio a impostare la spaziatura delle righe per più paragrafi?  
 Puoi applicare`TextFormattingOptions` a ciascuno`TextFragment` O`TextParagraph` per controllare la spaziatura tra più righe o paragrafi.