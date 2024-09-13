---
title: Timbri numerici di pagina nel file PDF
linktitle: Timbri numerici di pagina nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere timbri con i numeri di pagina ai file PDF utilizzando Aspose.PDF per .NET tramite la nostra guida semplice da seguire, completa di esempi di codice.
type: docs
weight: 160
url: /it/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Introduzione

Ti è mai capitato di lottare con un documento PDF, desiderando che avesse i numeri di pagina per una navigazione più semplice? Che tu sia uno studente che condivide appunti, un professionista che presenta report o chiunque gestisca documenti multipagina, aggiungere numeri di pagina può davvero migliorare la chiarezza dei tuoi file PDF. Fortunatamente, con la potente libreria Aspose.PDF per .NET, puoi aggiungere timbri con numeri di pagina ai tuoi documenti PDF con facilità. In questa guida, ti guideremo passo dopo passo attraverso l'intero processo, assicurandoti di essere dotato di tutte le conoscenze di cui hai bisogno. Immergiamoci!

## Prerequisiti

Prima di iniziare ad aggiungere timbri con i numeri di pagina ai tuoi documenti PDF, assicurati di avere i seguenti prerequisiti:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema. Qui scriverai ed eseguirai il tuo codice.
2. .NET Framework: è essenziale avere familiarità con la programmazione C# e con il framework .NET, poiché Aspose.PDF è progettato per le applicazioni .NET.
3.  Libreria Aspose.PDF: puoi scaricare la libreria Aspose.PDF da[Versioni PDF di Aspose](https://releases.aspose.com/pdf/net/). 
4. Nozioni di base sui PDF: non è necessario essere un esperto, ma una conoscenza di base del funzionamento dei file PDF ti aiuterà a comprendere meglio il tutorial.

Una volta impostati questi prerequisiti, sarai pronto per iniziare ad timbrare i numeri di pagina!

## Importa pacchetti

Prima di immergerti nella codifica, devi assicurarti che i pacchetti Aspose.PDF necessari siano importati nel tuo progetto. Questo è fondamentale per sfruttare le funzioni della libreria senza problemi. Ecco come fare:

### Crea un nuovo progetto

1. Aprire Visual Studio.
2.  Fare clic su`File` >`New` >`Project`.
3.  Seleziona un modello adatto per C# (ad esempio, applicazione console), assegnagli un nome e fai clic`Create`.

### Aggiungi riferimento Aspose.PDF

1. Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni.
2.  Fare clic su`Manage NuGet Packages`.
3.  Cercare`Aspose.PDF` e installare la versione più recente.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ora che la libreria è pronta, passiamo alla codifica!

Ora che il nostro ambiente è impostato, è il momento di aggiungere timbri numerici di pagina a un file PDF. Suddivideremo questo processo in passaggi chiari per una migliore comprensione.

## Passaggio 1: specificare la directory dei documenti

Per iniziare, devi specificare la directory in cui si trova il tuo file PDF. Questo è il punto di partenza del tuo progetto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Aggiorna questo percorso
```

 Spiegazione: Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso che porta alla directory contenente il tuo file PDF. Questo è fondamentale perché indica al tuo codice dove trovare il file che vuoi manipolare.

## Passaggio 2: aprire il documento

Successivamente, apriremo il documento PDF esistente al quale vogliamo aggiungere i timbri dei numeri di pagina.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Spiegazione: Qui stiamo usando il`Document` classe fornita da Aspose.PDF per aprire il nostro file PDF specifico. Assicurati che il nome del file corrisponda al file effettivo che hai nella tua directory.

## Passaggio 3: creare un timbro con il numero di pagina

Ora arriva la parte divertente! Creiamo un timbro con il numero di pagina da aggiungere al nostro PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Spiegazione: Il`PageNumberStamp`La classe ci consentirà di creare un timbro che visualizzerà il numero di pagina corrente rispetto al numero totale di pagine del documento.

## Passaggio 4: Configurare il timbro

Ora, dovrai configurare le impostazioni del timbro. Qui è dove progetti l'aspetto e il comportamento del timbro.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Spiegazione:
- `Background = false`: Ciò significa che il francobollo apparirà in primo piano.
- `Format`: Qui stai impostando il formato per visualizzare "Pagina X di Y", dove recuperi dinamicamente il totale delle pagine nel documento.
- `BottomMargin`: Regola la distanza dal fondo della pagina.
- `HorizontalAlignment`: Centra il timbro orizzontalmente.
- `StartingNumber`: Imposta il numero di pagina iniziale, in genere da 1.

## Passaggio 5: imposta le proprietà del testo

Ora puoi personalizzare l'aspetto del testo nel timbro.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Spiegazione: Questi attributi configurano il tipo di carattere, la dimensione del carattere, lo stile (sia grassetto che corsivo) e il colore del testo all'interno del timbro per renderlo visivamente accattivante.

## Passaggio 6: aggiungere il timbro a una pagina specifica

Dopo aver configurato il timbro, è il momento di aggiungerlo a una pagina specifica del documento.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Spiegazione: Questa riga aggiunge il timbro alla prima pagina del PDF. È possibile regolare il`Pages[1]` indice per altre pagine, se necessario.

## Passaggio 7: Salvare il documento di output

Infine, salva il documento PDF modificato in modo che le modifiche siano permanenti.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Spiegazione: stai definendo il percorso del file di output e salvando il documento. La console ti informerà che il timbro è stato aggiunto correttamente e dove è stato salvato il file.

## Conclusione

Aggiungere timbri di numeri di pagina ai tuoi file PDF usando Aspose.PDF per .NET non è solo semplice ma anche altamente personalizzabile. Abbiamo percorso passo dopo passo la creazione di un timbro di numeri di pagina, assicurandoti una guida chiara lungo il percorso. Ora possiedi le conoscenze per migliorare i tuoi documenti PDF, rendendoli più intuitivi e professionali. 

## Domande frequenti

### Posso personalizzare l'aspetto dei numeri di pagina?  
Sì! Puoi cambiare il carattere, la dimensione, il colore e la formattazione dei numeri di pagina come mostrato nella guida.

### Aspose.PDF è gratuito?  
 Aspose.PDF offre una prova gratuita, ma per un uso intensivo avrai bisogno di una licenza. Dai un'occhiata a[acquista pagina](https://purchase.aspose.com/buy) per maggiori informazioni.

### Cosa succede se riscontro problemi durante l'implementazione?  
 Puoi visitare il[Forum di supporto Aspose](https://forum.aspose.com/c/pdf/10) per assistenza.

### Come posso generare automaticamente i numeri di pagina per più pagine?  
Il codice della guida calcola automaticamente il numero totale di pagine, semplificando la personalizzazione di più pagine.

### Posso usare Aspose.PDF in altri linguaggi di programmazione?  
Sebbene questa guida si concentri su .NET, Aspose dispone di librerie per Java, Python e altro ancora.