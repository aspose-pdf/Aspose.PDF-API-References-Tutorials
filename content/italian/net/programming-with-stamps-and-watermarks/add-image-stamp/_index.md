---
title: Aggiungi timbro immagine nel file PDF
linktitle: Aggiungi timbro immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un timbro immagine ai file PDF utilizzando Aspose.PDF per .NET con istruzioni dettagliate e codice di esempio.
type: docs
weight: 20
url: /it/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## Introduzione

Quando si tratta di manipolare file PDF, pochi strumenti sono così robusti e intuitivi come Aspose.PDF per .NET. Che tu voglia aggiungere annotazioni, creare moduli o timbrare immagini, questa libreria fornisce funzionalità estese per soddisfare varie esigenze di manipolazione PDF. In questo tutorial, ci concentreremo su un'attività specifica: aggiungere un timbro immagine a un file PDF. Non si tratta solo di schiaffeggiare un'immagine su una pagina; si tratta di migliorare i tuoi documenti con branding e appeal visivo!

## Prerequisiti

Prima di immergerci nei dettagli del codice, assicuriamoci di avere tutto ciò di cui hai bisogno. Ecco cosa ti servirà:

1. Visual Studio o qualsiasi IDE .NET: è necessario disporre di un ambiente di sviluppo .NET per implementare i frammenti di codice.
2.  Aspose.PDF per la libreria .NET: questo è lo strumento principale che utilizzeremo. Puoi scaricare l'ultima versione della libreria da[Pagina di rilascio di Aspose](https://releases.aspose.com/pdf/net/).
3. Conoscenza di base di C#: una conoscenza fondamentale della programmazione C# ti aiuterà a navigare senza problemi nel codice.
4. Un file immagine: hai bisogno di un file immagine che vuoi usare come timbro. Assicurati che sia in un formato supportato (come JPEG, PNG, ecc.).
5. File PDF esistente: avere un file PDF di esempio in cui aggiungere il timbro dell'immagine.

Ora che è tutto pronto, passiamo al codice!

## Importa pacchetti

Prima di tutto, prima di fare qualsiasi cosa, devi importare i namespace necessari. Nel tuo codice C#, puoi farlo aggiungendo la seguente direttiva using all'inizio del tuo file:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

Ciò consentirà di accedere alle varie classi e metodi forniti dalla libreria Aspose.PDF.

## Passaggio 1: imposta la directory dei documenti

 Il primo passo è specificare il percorso per i tuoi documenti. Vorrai memorizzare il tuo documento e le immagini in una directory ben definita. Per semplicità, dichiara una variabile`dataDir` come questo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del tuo sistema.

## Passaggio 2: aprire il documento PDF

Poi, dobbiamo aprire il documento PDF che vogliamo modificare. È qui che Aspose.PDF brilla! Hai bisogno solo di poche righe di codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

 Questa linea crea una nuova`Document`oggetto caricando il file PDF specificato. Assicurati che il file esista nella directory specificata; altrimenti, incontrerai un errore di file non trovato!

## Passaggio 3: creare il timbro immagine

Ora arriva la parte divertente: aggiungere il timbro immagine! Per prima cosa, dobbiamo creare un oggetto timbro immagine usando il tuo file immagine:

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 Questa riga inizializza un`ImageStamp` oggetto che rappresenta l'immagine che vuoi aggiungere. È fondamentale controllare che il percorso del file immagine sia corretto.

## Passaggio 4: configurare le proprietà del timbro immagine

Ecco dove puoi dare sfogo alla tua creatività e personalizzare il tuo timbro. Puoi impostare proprietà come posizione, dimensione, rotazione e opacità. Ecco un esempio di come farlo:

```csharp
imageStamp.Background = true; // Impostare su vero se si desidera che il timbro sia sullo sfondo
imageStamp.XIndent = 100; // Posizione da sinistra
imageStamp.YIndent = 100; // Posizione dall'alto
imageStamp.Height = 300; // Imposta l'altezza del timbro
imageStamp.Width = 300; // Imposta la larghezza del timbro
imageStamp.Rotate = Rotation.on270; // Ruotare se necessario
imageStamp.Opacity = 0.5; // Imposta l'opacità
```

Sentiti libero di modificare questi valori in base alle tue esigenze! Questa personalizzazione ti consente di posizionare il tuo timbro esattamente dove vuoi.

## Passaggio 5: aggiungere il timbro a una pagina specifica

Ora che abbiamo configurato il nostro timbro, il passo successivo è specificare dove vogliamo posizionarlo nel documento PDF. In questo esempio, lo aggiungeremo alla prima pagina:

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Questo frammento di codice dice ad Aspose di aggiungere il timbro alla prima pagina del documento.

## Passaggio 6: Salvare il documento

Una volta applicato il timbro, è il momento di salvare le modifiche. Devi specificare un percorso per il file PDF di output:

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

Il documento è ora salvato con il nuovo timbro immagine applicato!

## Passaggio 7: confermare la modifica

Infine, è sempre bene confermare che l'operazione è andata a buon fine. Puoi farlo con un semplice messaggio della Console:

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

Questo messaggio ti informerà che il timbro immagine è stato aggiunto e ti indicherà dove trovare il PDF appena modificato.

## Conclusione

Congratulazioni! Hai appena aggiunto un timbro immagine a un PDF usando Aspose.PDF per .NET. Potrebbe sembrare complicato all'inizio, ma con un po' di pratica puoi personalizzare i tuoi documenti PDF in una miriade di modi. La chiave qui è sperimentare le varie proprietà offerte da Aspose: il limite è la tua immaginazione.

## Domande frequenti

### Aspose.PDF per .NET è gratuito?  
 Aspose.PDF offre una prova gratuita, ma è richiesta una licenza per l'uso continuato dopo il periodo di prova. Puoi controllare il[opzioni di prezzo qui](https://purchase.aspose.com/buy).

### Posso aggiungere più timbri a un singolo PDF?  
 Assolutamente! Puoi creare più`ImageStamp` oggetti e aggiungerli a qualsiasi pagina del PDF.

### Quali formati di immagine sono supportati per i francobolli?  
Aspose.PDF supporta vari formati di immagine, tra cui JPEG, PNG e BMP.

### Come posso ruotare un timbro con immagine?  
 Puoi impostare il`Rotate` proprietà del`ImageStamp` oggetto per ruotare l'immagine all'angolazione desiderata. Le opzioni includono`Rotation.on90`, `Rotation.on180`, ecc.

### Dove posso trovare ulteriore documentazione su Aspose.PDF?  
 Puoi esplorare il riferimento API completo e la documentazione[Qui](https://reference.aspose.com/pdf/net/).