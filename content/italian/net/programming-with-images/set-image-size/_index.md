---
title: Imposta la dimensione dell'immagine nel file PDF
linktitle: Imposta la dimensione dell'immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare le dimensioni dell'immagine in un PDF usando Aspose.PDF per .NET. Questa guida passo passo ti aiuterà a ridimensionare le immagini, regolare le proprietà della pagina e salvare i PDF.
type: docs
weight: 270
url: /it/net/programming-with-images/set-image-size/
---
## Introduzione

Lavorare con i PDF è un requisito comune per molte applicazioni e la capacità di manipolare gli elementi all'interno di un file PDF può essere cruciale. Sia che tu stia creando un generatore di report o aggiungendo contenuti dinamici al tuo PDF, controllare le dimensioni delle immagini all'interno del tuo documento è una funzionalità essenziale. In questo tutorial, ti guideremo attraverso come impostare le dimensioni delle immagini in un file PDF utilizzando Aspose.PDF per .NET. Questa potente libreria offre un controllo esteso sul contenuto PDF e la analizzeremo passo dopo passo per mostrarti quanto può essere semplice. Alla fine, sarai in grado di ridimensionare le immagini con sicurezza e di comprendere come questa funzionalità possa migliorare i tuoi flussi di lavoro PDF.


## Prerequisiti

Prima di immergerci nel codice, ecco alcune cose che dovrai sapere per seguire questo tutorial.

1.  Aspose.PDF per .NET: assicurati di avere installata l'ultima versione della libreria Aspose.PDF. Puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).
2. .NET Framework o .NET Core: assicurati di disporre di un ambiente di lavoro con .NET Framework o .NET Core configurato.
3. Conoscenza di base di C#: useremo C# come linguaggio di programmazione, quindi è essenziale avere familiarità con esso.
4. Immagine di esempio: avrai bisogno di un'immagine di esempio da incorporare nel PDF. Puoi usare qualsiasi immagine tu voglia, ma assicurati che sia accessibile nella directory del tuo progetto.

## Importa pacchetti

Per usare Aspose.PDF per .NET, devi prima importare i namespace necessari. Ecco una semplice configurazione:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora che abbiamo capito le basi, passiamo alla creazione e alla modifica di un documento PDF.

## Passaggio 1: inizializza il tuo documento PDF

 La prima cosa che dobbiamo fare è creare un nuovo documento PDF. Useremo il`Document` classe da Aspose.PDF per ottenere questo risultato.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
```
 
 Qui, istanziamo un`Document` oggetto, che rappresenterà il nostro file PDF. Specifichiamo anche la directory in cui si trovano i nostri file utilizzando il`dataDir` variabile. Questo è il punto di partenza per creare qualsiasi PDF con Aspose.PDF.

## Passaggio 2: aggiungi una nuova pagina al tuo PDF

Una volta che abbiamo il nostro documento pronto, dobbiamo aggiungerci una pagina. Ogni PDF deve avere almeno una pagina, quindi aggiungiamone una.

```csharp
// Aggiungi pagina alla raccolta di pagine del file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Aggiungiamo una nuova pagina al documento utilizzando il`Pages.Add()` metodo. Questa pagina fungerà da tela su cui posizioneremo la nostra immagine. Ogni pagina in un PDF è essenzialmente una lavagna vuota su cui puoi aggiungere testo, immagini o altri contenuti.

## Passaggio 3: creare un'istanza di immagine

 Ora è il momento di preparare l'immagine che vogliamo inserire nel PDF. Aspose.PDF fornisce un`Image` classe per gestire le immagini.

```csharp
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Creiamo una nuova istanza di`Image` classe. Questo oggetto conterrà le proprietà dell'immagine che vogliamo aggiungere al PDF. Configureremo la dimensione e il tipo dell'immagine nei passaggi successivi.

## Passaggio 4: imposta le dimensioni dell'immagine (larghezza e altezza)

Ecco dove arriviamo al nocciolo del nostro tutorial: impostare la dimensione dell'immagine. Aspose.PDF consente di specificare la larghezza e l'altezza dell'immagine in punti.

```csharp
// Imposta la larghezza e l'altezza dell'immagine in punti
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 IL`FixWidth` E`FixHeight`Le proprietà consentono di impostare le dimensioni esatte dell'immagine in punti. In questo esempio, stiamo ridimensionando l'immagine a 100x100 punti. Puoi adattare questi valori alle tue esigenze.

## Passaggio 5: specificare il tipo di immagine

A seconda del formato immagine con cui stai lavorando, potresti dover impostare il tipo di immagine. Aspose.PDF supporta vari formati immagine e qui definiamo il tipo di file.

```csharp
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 In questo caso, lasciamo il tipo di file come`Unknown` , che consente alla libreria di rilevare automaticamente il tipo di immagine. Se conosci il tipo di file specifico, puoi impostarlo (ad esempio,`ImageFileType.Jpeg` per le immagini JPEG). Questo passaggio assicura che Aspose sappia come gestire correttamente l'immagine.

## Passaggio 6: imposta il percorso del file immagine

Ora dobbiamo dire ad Aspose dove trovare il file immagine. Assicurati che la tua immagine sia accessibile nella directory specificata.

```csharp
// Percorso per il file sorgente
img.File = dataDir + "aspose-logo.jpg";
```
 
 Qui, impostiamo il percorso del file per l'immagine. L'immagine, in questo caso, si trova in`dataDir` cartella e si chiama`aspose-logo.jpg`Assicurati di sostituirlo con il nome e la posizione effettivi del tuo file immagine.

## Passaggio 7: aggiungere l'immagine alla pagina

Dopo aver configurato l'immagine e impostato il percorso del file, possiamo aggiungere l'immagine alla nostra pagina.

```csharp
// Aggiungi l'immagine alla raccolta dei paragrafi
page.Paragraphs.Add(img);
```
 
 IL`Paragraphs.Add()` metodo ci consente di aggiungere l'immagine alla pagina. Pensate al`Paragraphs` collection come un elenco di elementi che saranno renderizzati sulla pagina PDF. Possiamo aggiungere più elementi a questa collection, come immagini, testo e forme.

## Passaggio 8: Regola le proprietà della pagina

Per assicurarci che la nostra immagine si adatti bene, regoleremo le dimensioni della pagina. Questo assicurerà che le dimensioni della pagina corrispondano al contenuto che stiamo aggiungendo.

```csharp
// Imposta le proprietà della pagina
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Qui, stiamo impostando la larghezza e l'altezza della pagina a 800 punti. Questo passaggio è facoltativo, ma assicura che la pagina accolga l'immagine ridimensionata. Puoi regolare questi valori in base alle tue esigenze specifiche.

## Passaggio 9: Salva il PDF

Infine, dopo aver configurato le proprietà dell'immagine e della pagina, possiamo salvare il PDF.

```csharp
//Salvare il file PDF risultante
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Salviamo il documento modificato come`SetImageSize_out.pdf` nella stessa directory. Questo file conterrà ora l'immagine ridimensionata che hai aggiunto.

## Conclusione

In questo tutorial, abbiamo spiegato come impostare le dimensioni dell'immagine in un PDF usando Aspose.PDF per .NET. Abbiamo spiegato come creare un documento, aggiungere una pagina, configurare un'immagine e salvare il risultato. Questa guida passo passo è solo l'inizio di ciò che puoi fare con Aspose.PDF per .NET. Ora che hai imparato come ridimensionare le immagini, sentiti libero di esplorare altre funzionalità come la formattazione del testo, la creazione di tabelle e persino l'aggiunta di annotazioni al tuo PDF.

## Domande frequenti

### Posso utilizzare formati di immagine diversi con Aspose.PDF per .NET?  
Sì, Aspose.PDF supporta vari formati di immagine, tra cui JPEG, PNG, BMP e SVG.

### Come faccio a mantenere le proporzioni dell'immagine?  
 È possibile mantenere le proporzioni impostando`FixWidth` O`FixHeight` lasciando l'altra dimensione non impostata.

### Posso aggiungere più immagini a una singola pagina PDF?  
Assolutamente! Ripeti semplicemente il processo di aggiunta di un'istanza di immagine e aggiungi ciascuna a`Paragraphs` collezione.

### È possibile impostare le dimensioni dell'immagine in unità diverse dai punti?  
Aspose.PDF funziona principalmente con i punti, ma è possibile convertire altre unità di misura, come pollici o millimetri, in punti (1 pollice = 72 punti).

### Come faccio a posizionare un'immagine in un punto specifico della pagina?  
 Puoi impostare il`Image.LowerLeftX` E`Image.LowerLeftY` proprietà per posizionare l'immagine sulla pagina.