---
title: Aggiungi data e ora nel file PDF
linktitle: Aggiungi data e ora nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un timbro data e ora ai tuoi file PDF usando Aspose.PDF per .NET con questa guida passo-passo. Perfetto per migliorare l'autenticità dei documenti.
type: docs
weight: 10
url: /it/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Introduzione

Quando si tratta di gestire documenti, in particolare PDF, aggiungere un timbro data e ora può cambiare le carte in tavola. Che tu stia lavorando su documenti legali, report di progetto o fatture, un timbro data e ora non solo aggiunge autenticità, ma fornisce anche una chiara registrazione di quando il documento è stato creato o modificato. In questa guida, ti guideremo attraverso il processo di aggiunta di un timbro data e ora a un file PDF utilizzando la libreria Aspose.PDF per .NET. 

Questo articolo è stato progettato per essere semplice e facile da seguire, quindi anche se sei alle prime armi con la programmazione o la libreria Aspose.PDF, sarai in grado di implementare questa funzionalità con sicurezza. Immergiamoci!

## Prerequisiti

Prima di iniziare, ecco alcuni prerequisiti che devi soddisfare:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Qui è dove scriverai ed eseguirai il tuo codice.
2. Aspose.PDF per .NET: devi scaricare e installare la libreria Aspose.PDF. Puoi trovare l'ultima versione[Qui](https://releases.aspose.com/pdf/net/).
3. Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a comprendere meglio gli esempi, ma non preoccuparti se sei alle prime armi: ti spiegheremo tutto passo dopo passo.
4.  Un file PDF: tieni pronto un file PDF di esempio. Per il nostro esempio, useremo un file denominato`AddTextStamp.pdf`.

Una volta soddisfatti questi prerequisiti, sarai pronto per iniziare ad aggiungere data e ora ai tuoi file PDF!

## Importa pacchetti

Per iniziare, devi importare i namespace necessari nel tuo progetto C#. Ecco come fare:

### Crea un nuovo progetto

1. Apri Visual Studio: avvia l'applicazione Visual Studio.
2. Crea un nuovo progetto: seleziona "Crea un nuovo progetto" dalla schermata iniziale.
3. Scegli App console: seleziona “App console (.NET Framework)” dall’elenco dei modelli di progetto.
4.  Assegna un nome al tuo progetto: dai un nome al tuo progetto, ad esempio,`PDFDateTimeStamp`.

### Aggiungi riferimento Aspose.PDF

1. Fare clic con il pulsante destro del mouse su Riferimenti: in Esplora soluzioni, fare clic con il pulsante destro del mouse sulla cartella "Riferimenti" del progetto.
2. Seleziona “Aggiungi riferimento”: scegli “Aggiungi riferimento” dal menu contestuale.
3. Browse for Aspose.PDF: Vai alla posizione in cui hai scaricato Aspose.PDF e selezionalo. Fai clic su "OK" per aggiungerlo al tuo progetto.

### Importa gli spazi dei nomi richiesti

 In cima al tuo`Program.cs` file, è necessario importare i seguenti namespace:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Ora che abbiamo impostato tutto, scomponiamo il processo di aggiunta di data e ora a un file PDF in passaggi chiari e gestibili.

## Passaggio 1: impostare la directory dei documenti

Per prima cosa, devi specificare la directory in cui si trova il tuo file PDF. Questo è fondamentale perché il codice cercherà il PDF in questa directory.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Sostituisci con il tuo percorso effettivo
```

 Assicurati di sostituire`YOUR DOCUMENT DIRECTORY` con il percorso effettivo del file PDF.

## Passaggio 2: aprire il documento PDF

Successivamente, apri il documento PDF in cui desideri aggiungere la marca temporale. 

```csharp
// Apri documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Questa riga di codice inizializza il`Document` classe e carica il tuo file PDF nel`pdfDocument` oggetto.

## Passaggio 3: creare il timestamp di data e ora

Ora è il momento di generare la data e l'ora. La formatterai per visualizzarla in un modo specifico. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Qui,`DateTime.Now` ottiene la data e l'ora correnti e`ToString` formattalo nel formato desiderato.

## Passaggio 4: creare un timbro di testo

Una volta pronta la stringa di data e ora, puoi creare un timbro di testo che verrà aggiunto al tuo PDF.

```csharp
// Crea timbro di testo
TextStamp textStamp = new TextStamp(annotationText);
```

 Questa riga crea una nuova istanza di`TextStamp` utilizzando la stringa di data e ora formattata.

## Passaggio 5: impostare le proprietà del timbro

Puoi personalizzare l'aspetto e la posizione del timbro. Ecco come impostarne le proprietà:

```csharp
// Imposta le proprietà del timbro
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

In questa fase, impostiamo i margini e allineiamo il timbro all'angolo inferiore destro della pagina PDF.

## Passaggio 6: aggiungere il timbro al PDF

Adesso è il momento di aggiungere il timbro di testo al documento PDF. 

```csharp
// Aggiungere un francobollo alla collezione di francobolli
pdfDocument.Pages[1].AddStamp(textStamp);
```

Questa riga aggiunge il timbro alla prima pagina del PDF. Puoi cambiare il numero di pagina se vuoi posizionarlo su una pagina diversa.

## Passaggio 7: creare un'annotazione di testo libero (facoltativo)

Se vuoi aggiungere un'annotazione al timbro, puoi creare un`FreeTextAnnotation` come segue:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Questo passaggio facoltativo crea un'annotazione di testo libero che può fornire contesto o informazioni aggiuntive sul francobollo.

## Passaggio 8: configurare il bordo dell'annotazione

Se vuoi personalizzare il bordo della tua annotazione, puoi farlo anche tu:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Questo frammento di codice imposta la larghezza del bordo su 0, rendendolo invisibile, e aggiunge l'annotazione al PDF.

## Passaggio 9: Salvare il documento PDF

Infine, è necessario salvare il documento PDF modificato. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Specificare il nome del file di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Questa riga salva il PDF con il timestamp aggiunto in un nuovo file. Puoi controllare la directory specificata per vedere l'output.

## Conclusione

Congratulazioni! Hai aggiunto con successo un timbro data e ora a un file PDF usando Aspose.PDF per .NET. Questa semplice ma efficace funzionalità può migliorare i tuoi documenti, rendendoli più professionali e fornendo una chiara registrazione di quando sono stati creati o modificati. 

## Domande frequenti

### Posso personalizzare il formato della data nel timestamp?
 Sì, puoi modificare il`ToString`metodo per modificare il formato della data in base alle proprie preferenze.

### Aspose.PDF è gratuito?
 Aspose.PDF offre una prova gratuita, ma per le funzionalità complete, è necessario acquistare una licenza. È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Posso aggiungere più timestamp a un PDF?
 Assolutamente! Puoi creare più`TextStamp` istanze e aggiungerle a pagine o posizioni diverse nel PDF.

### Cosa succede se non ho Visual Studio?
È possibile utilizzare qualsiasi IDE C# o editor di testo, ma per l'esecuzione e il debug del progetto è consigliabile Visual Studio.

### Dove posso trovare altri esempi di utilizzo di Aspose.PDF?
 Puoi esplorare altri esempi e tutorial in[Documentazione Aspose.PDF](https://reference.aspose.com/pdf/net/).