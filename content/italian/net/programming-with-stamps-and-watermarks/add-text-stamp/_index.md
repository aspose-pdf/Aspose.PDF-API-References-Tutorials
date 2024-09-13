---
title: Aggiungi timbro di testo nel file PDF
linktitle: Aggiungi timbro di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un timbro di testo in un file PDF utilizzando Aspose.PDF per .NET con la nostra guida dettagliata e migliora le presentazioni dei tuoi documenti.
type: docs
weight: 50
url: /it/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Introduzione

Nell'era digitale odierna, i PDF sono un formato comune per la condivisione e la distribuzione di documenti. Che tu sia uno sviluppatore, un creatore di contenuti o semplicemente qualcuno che cerca di migliorare i propri file PDF, sapere come manipolare i PDF a livello di programmazione può essere un punto di svolta. Una caratteristica ingegnosa di cui potresti voler fare uso è la possibilità di aggiungere timbri di testo nei tuoi file PDF. Aggiungere un timbro di testo può dare ai tuoi documenti un tocco professionale o trasmettere informazioni importanti, come "Esempio", "Riservato" o persino una filigrana.

## Prerequisiti

Prima di passare al codice, ci sono alcuni prerequisiti per assicurarti di aver impostato tutto correttamente. Ecco cosa ti servirà:

1.  Aspose.PDF per .NET: assicurati di avere la libreria Aspose.PDF installata nel tuo progetto. Se non l'hai ancora fatto, puoi scaricarla da[Sito web di Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio o IDE compatibile: avrai bisogno di un ambiente di sviluppo per scrivere ed eseguire il tuo codice .NET. Visual Studio è la scelta più comune tra gli sviluppatori.
3. Conoscenza di base di C#: la familiarità con C# e con i principi della programmazione orientata agli oggetti ti aiuterà a comprendere meglio gli esempi.
4. File PDF di esempio: dovresti avere un file PDF pronto per lavorare. Puoi creare un PDF di base o usare qualsiasi PDF esistente per testare la funzionalità.

Una volta soddisfatti questi prerequisiti, possiamo passare alla codifica!

## Importa pacchetti

Ora, importiamo i pacchetti necessari. Questo passaggio è cruciale perché rende disponibili nel tuo progetto le classi e i metodi della libreria Aspose.

### Importa Aspose.PDF Assembly

Per iniziare, devi importare lo spazio dei nomi Aspose.PDF. In cima al tuo file C#, aggiungi la seguente direttiva using:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ciò ti consentirà di accedere a corsi essenziali per la creazione e la manipolazione di documenti PDF.

Ora, entriamo nel vivo del tutorial. Suddivideremo il processo in passaggi chiari e concisi. Ogni passaggio ti guiderà attraverso il codice per aggiungere un timbro di testo a un file PDF.

## Passaggio 1: impostare la directory dei documenti

Per prima cosa, devi stabilire la directory in cui è archiviato il tuo documento PDF. Ciò significa che il tuo codice deve sapere dove trovare il file PDF che vuoi modificare.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Spiegazione: Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si trova il file PDF (`AddTextStamp.pdf`) viene memorizzato. Questo percorso viene utilizzato in seguito per aprire e salvare il PDF modificato.

## Passaggio 2: aprire il documento PDF

 Successivamente, apriremo il documento PDF utilizzando`Document` classe dallo spazio dei nomi Aspose.PDF.

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Spiegazione: qui stiamo creando un'istanza di`Document` classe e passando il percorso al nostro file PDF. Questo caricherà il PDF in modo che possiamo manipolarlo.

## Passaggio 3: creare un timbro di testo

Ora creeremo un timbro di testo che applicheremo in seguito al nostro documento PDF.

```csharp
// Crea timbro di testo
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Spiegazione: Il`TextStamp` l'oggetto viene creato con il testo che vuoi visualizzare. In questo caso, stiamo usando "Sample Stamp" come testo per il nostro timbro.

## Passaggio 4: impostare le proprietà del timbro

Per personalizzare il timbro, possiamo impostare varie proprietà come il colore di sfondo, la posizione e la rotazione. Facciamolo ora:

```csharp
// Imposta se il timbro è uno sfondo
textStamp.Background = true;

// Imposta origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Ruota timbro
textStamp.Rotate = Rotation.on90;
```

Spiegazione:
- Contesto: impostazione su`true` significa che il timbro apparirà dietro il contenuto del PDF.
- XIndent e YIndent: queste proprietà determinano la posizione del timbro sulla pagina. In questo esempio, il timbro verrà posizionato a 100 unità dai bordi sinistro e superiore della pagina.
- Rotate: ruota il timbro di 90 gradi. Puoi scegliere diverse opzioni di rotazione in base ai requisiti del tuo design.

## Passaggio 5: personalizzare le proprietà del testo

Ora diamo sfogo alla nostra creatività personalizzando l'aspetto del testo all'interno del nostro timbro:

```csharp
// Imposta le proprietà del testo
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Spiegazione:
- Carattere: stiamo utilizzando il carattere Arial, rendendolo grassetto e corsivo.
- FontSize: è impostato su 14 punti.
- ForegroundColor: utilizzo di RGB per impostare il colore del testo su Aqua. Sentiti libero di cambiare il colore per adattarlo alle tue esigenze di branding o design!

## Passaggio 6: aggiungere il timbro alla pagina PDF

Adesso è il momento di aggiungere il timbro a una pagina specifica del documento PDF.

```csharp
// Aggiungi timbro a una pagina specifica
pdfDocument.Pages[1].AddStamp(textStamp);
```

Spiegazione: In questo esempio, il timbro viene aggiunto alla prima pagina del PDF (le pagine sono indicizzate 1). Adatta il numero di pagina in base alle tue esigenze per il tuo documento.

## Passaggio 7: Salvare il PDF modificato

Infine, salviamo il documento con il timbro di testo appena aggiunto.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Spiegazione: Definiamo un nuovo percorso per il file di output e quindi salviamo il documento modificato. Dopo il salvataggio, il percorso viene stampato sulla console, confermando l'operazione riuscita.

## Conclusione

Congratulazioni! Hai aggiunto con successo un timbro di testo a un file PDF usando Aspose.PDF per .NET. Questo metodo ti consente di annotare i tuoi documenti in modo efficiente, migliorandone sia la professionalità che l'usabilità. Che tu stia aggiungendo filigrane, firme o semplici note, la libreria Aspose fornisce potenti strumenti per manipolare i tuoi PDF con facilità.

## Domande frequenti

### Cos'è un timbro di testo in un PDF?
Un timbro di testo è una sovrapposizione grafica contenente testo che può essere inserita in un documento PDF, spesso utilizzata per annotazioni o filigrane.

### Posso personalizzare il timbro con immagini?
Sì, Aspose.PDF supporta anche l'aggiunta di timbri immagine, garantendo maggiore flessibilità di progettazione.

### Quali linguaggi di programmazione posso usare con Aspose.PDF?
Aspose.PDF è incentrato principalmente su .NET, ma sono disponibili versioni per altri linguaggi come Java e Python.

### Come posso ottenere una licenza temporanea per Aspose.PDF?
 È possibile richiedere una licenza temporanea visitando il[link di acquisto](https://purchase.aspose.com/temporary-license/) sul loro sito web.

### Dove posso trovare supporto per Aspose.PDF?
 Il supporto per Aspose.PDF è disponibile sul loro[forum di supporto](https://forum.aspose.com/c/pdf/10).