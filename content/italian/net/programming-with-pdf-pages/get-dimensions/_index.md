---
title: Ottieni le dimensioni della pagina PDF
linktitle: Ottieni le dimensioni della pagina PDF
second_title: Riferimento API Aspose.PDF per .NET
description: In questo tutorial, spieghiamo come ottenere le dimensioni della pagina PDF ed eseguire manipolazioni usando Aspose.PDF per .NET. Sono forniti passaggi dettagliati per guidarti attraverso il processo.
type: docs
weight: 60
url: /it/net/programming-with-pdf-pages/get-dimensions/
---
## Introduzione

Hai mai avuto bisogno di manipolare le dimensioni di pagina di un documento PDF? Forse hai voluto ridimensionare una pagina o ruotarla per adattarla alle tue esigenze? Se è così, sei nel posto giusto! In questo tutorial, ti guideremo attraverso il recupero e la modifica delle dimensioni di pagina PDF utilizzando Aspose.PDF per .NET. Che tu sia un principiante o uno sviluppatore esperto, troverai questa guida semplice e facile da seguire.

Aspose.PDF per .NET è una potente libreria che ti consente di creare, manipolare e trasformare file PDF senza sforzo. È come avere un coltellino svizzero per i PDF: puoi modificare ogni piccolo dettaglio per adattarlo alle tue esigenze specifiche. Quindi, tuffiamoci subito e impariamo come recuperare e aggiornare le dimensioni delle pagine PDF usando questo fantastico strumento!

## Prerequisiti

Prima di iniziare, per seguire questo tutorial senza problemi, devi avere a disposizione alcuni elementi:

1.  Aspose.PDF per .NET: puoi[scarica l'ultima versione qui](https://releases.aspose.com/pdf/net/) . Se non hai la patente, non preoccuparti! Puoi richiederne una[prova gratuita](https://releases.aspose.com/) , oppure optare per un[licenza temporanea](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: l'ambiente di sviluppo che utilizzerai per scrivere ed eseguire il codice.
3. Conoscenza di base di C#: anche se semplificheremo le cose, una certa familiarità con C# renderà il processo più fluido.
4. File PDF con cui lavorare: prendi un file PDF di esempio o creane uno nuovo per testarlo.

## Importa pacchetti

Per lavorare con Aspose.PDF per .NET, devi importare alcuni namespace essenziali. Questo prepara il terreno per interagire con i documenti PDF. Ecco come fare:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Queste importazioni garantiscono l'accesso alle classi principali necessarie per manipolare i file PDF, in particolare per la gestione delle pagine e il recupero delle loro dimensioni.

Ora che abbiamo tutto a posto, scomponiamo il processo in passaggi facili da seguire.

## Passaggio 1: definire il percorso del file e caricare il documento

Il primo passo è specificare il percorso del tuo documento PDF e caricarlo usando Aspose.PDF. Questo ti permetterà di interagire con le pagine nel file PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

In questo passaggio, stai essenzialmente aprendo il file PDF su cui vuoi lavorare. Se hai mai aperto un libro a una pagina specifica, è abbastanza simile, ma invece stai aprendo un documento PDF per accedere alle sue pagine.

## Passaggio 2: aggiungere una pagina vuota se non esistono pagine

E se il tuo documento non ha pagine? Non preoccuparti! Possiamo aggiungere una pagina vuota al documento e lavorarci. Ecco come controllare se esiste una pagina e aggiungerne una nuova se necessario:

```csharp
// Aggiunge una pagina vuota al documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Questa riga di codice controlla se c'è già una pagina nel documento. In caso affermativo, sceglie la prima pagina (`Pages[1]`). Altrimenti, crea una pagina vuota e la aggiunge al PDF.

Immagina di aprire un quaderno vuoto e di scrivere sulla prima pagina se non c'è niente: facile, vero?

## Passaggio 3: ottenere informazioni su altezza e larghezza della pagina

 Ora che abbiamo una pagina con cui lavorare, recuperiamo le dimensioni della pagina. Useremo il`GetPageRect()` metodo per ottenere altezza e larghezza.

```csharp
// Ottieni informazioni su altezza e larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Qui,`GetPageRect(true)` restituisce un rettangolo che include l'altezza e la larghezza della pagina. È come misurare un foglio di carta con un righello. L'output verrà visualizzato nella console, dandoti le dimensioni correnti della pagina.

## Passaggio 4: ruotare la pagina di 90 gradi

Vuoi ruotare la pagina? Nessun problema! Con una semplice proprietà, puoi ruotare la pagina di 90 gradi.

```csharp
// Ruota la pagina di 90 gradi
page.Rotate = Rotation.on90;
```

Questo passaggio ruota la pagina in senso orario di 90 gradi. Immagina di girare un foglio stampato sulla tua scrivania: ora è in modalità orizzontale!

## Passaggio 5: ricontrollare le dimensioni della pagina dopo la rotazione

Dopo aver ruotato la pagina, è una buona idea controllare di nuovo le dimensioni. Perché? Perché la rotazione può influenzare il modo in cui interpreti l'altezza e la larghezza.

```csharp
// Ottieni informazioni su altezza e larghezza della pagina
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Ora, le dimensioni della pagina saranno aggiornate in base al nuovo orientamento. È come ruotare una foto sul telefono: all'improvviso, la larghezza diventa l'altezza e viceversa.


## Conclusione

Congratulazioni! Hai imparato con successo come recuperare e modificare le dimensioni di una pagina PDF usando Aspose.PDF per .NET. A questo punto, dovresti essere in grado di caricare un PDF, controllare le dimensioni della pagina e persino ruotare la pagina se necessario.

Manipolare i PDF non deve essere complicato. Con Aspose.PDF, è semplice come seguire alcuni passaggi e usare metodi intuitivi. Quindi la prossima volta che dovrai gestire le dimensioni delle pagine PDF, saprai esattamente cosa fare!

## Domande frequenti

### Posso ruotare la pagina di angolazioni diverse da 90 gradi?
 Sì, Aspose.PDF consente di ruotare le pagine di 0, 90, 180 o 270 gradi utilizzando`Rotation` proprietà.

### Cosa succede se il mio PDF non ha pagine?
 Se il tuo PDF non ha pagine, puoi aggiungere una pagina vuota utilizzando`Pages.Add()` metodo, come mostrato in questo tutorial.

### Posso manipolare più pagine contemporaneamente?
Sì, puoi scorrere più pagine e applicare trasformazioni, come ridimensionamenti o rotazioni, a tutte.

### Le dimensioni della pagina influiscono sul contenuto del PDF?
Le dimensioni della pagina cambiano solo la dimensione della tela, non il contenuto. Tuttavia, il ridimensionamento potrebbe alterare il modo in cui il contenuto appare sulla pagina.

### Dove posso trovare maggiori informazioni su Aspose.PDF per .NET?
 Puoi visitare il[documentazione qui](https://reference.aspose.com/pdf/net/) per informazioni più dettagliate e casi d'uso avanzati.