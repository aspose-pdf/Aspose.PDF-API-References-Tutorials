---
title: Aggiungi segnalibro nel file PDF
linktitle: Aggiungi segnalibro nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi facilmente un segnalibro nel file PDF per una migliore navigazione con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/add-bookmark/
---
L'aggiunta di segnalibri in un file PDF consente una navigazione facile e veloce. Con Aspose.PDF per .NET, puoi facilmente aggiungere un segnalibro nel file PDF seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF a cui desideri aggiungere un segnalibro. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un segnalibro utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Passaggio 4: crea un oggetto segnalibro

 In questo passaggio creeremo un oggetto segnalibro utilizzando`OutlineItemCollection` classe e impostarne le proprietà come titolo, attributo corsivo, attributo grassetto e azione da eseguire quando si fa clic. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Passaggio 5: aggiungi il segnalibro al documento

 Infine, aggiungiamo il segnalibro creato alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`Outlines` proprietà. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Codice sorgente di esempio per Aggiungi segnalibro utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Crea un oggetto segnalibro
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Imposta il numero della pagina di destinazione
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Aggiungi segnalibro nella raccolta di strutture del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Salva l'output
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiungere un segnalibro utilizzando Aspose.PDF per .NET. Puoi utilizzare questo codice per migliorare la navigazione nei tuoi documenti PDF aggiungendo segnalibri personalizzati.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.


### Domande frequenti sull'aggiunta di segnalibri nel file PDF

#### D: Cosa sono i segnalibri in un file PDF?

R: I segnalibri, noti anche come contorni, sono elementi interattivi che forniscono navigazione e struttura all'interno di un documento PDF. Consentono agli utenti di passare rapidamente a sezioni o pagine specifiche.

#### D: Perché dovrei aggiungere segnalibri a un file PDF?

R: L'aggiunta di segnalibri a un file PDF migliora l'esperienza dell'utente e rende più semplice per i lettori navigare nel contenuto del documento. I segnalibri possono fungere da sommario o fornire un rapido accesso a sezioni importanti.

#### D: Come posso importare le librerie richieste per il mio progetto C#?

R: Per importare le librerie necessarie per il tuo progetto C#, includi le seguenti direttive di importazione:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Queste direttive consentono di accedere alle classi e ai metodi necessari per lavorare con documenti PDF e segnalibri.

#### D: Come posso specificare il percorso della cartella dei documenti?

 R: Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice sorgente fornito con il percorso effettivo della cartella contenente il file PDF a cui desideri aggiungere un segnalibro.

#### D: Come posso aprire un documento PDF per aggiungere segnalibri?

R: Per aprire un documento PDF per aggiungere segnalibri, utilizzare il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Sostituire`"AddBookmark.pdf"` con il nome effettivo del file.

#### D: Come posso creare un oggetto segnalibro?

 R: Per creare un oggetto segnalibro, utilizzare il file`OutlineItemCollection` classe. Personalizza le sue proprietà come titolo, stile corsivo, stile grassetto e azione da eseguire quando si fa clic.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  D: Qual è lo scopo di`Action` property in a bookmark?

 R: Il`Action` La proprietà specifica l'azione da eseguire quando si fa clic sul segnalibro. In questo esempio utilizziamo il file`GoToAction`class per passare a una pagina specifica (pagina 2 in questo caso).

#### D: Come faccio ad aggiungere il segnalibro al documento?

 R: Usa il`Add` metodo del`Outlines` proprietà per aggiungere il segnalibro creato alla raccolta di segnalibri del documento.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### D: Posso aggiungere più segnalibri utilizzando questo metodo?

R: Sì, puoi ripetere i passaggi da 4 a 8 per aggiungere più segnalibri al documento. Personalizza le proprietà e le azioni di ciascun segnalibro secondo necessità.

#### D: Come posso salvare il file PDF aggiornato?

 R: Salva il file PDF aggiornato utilizzando il file`Save` metodo del`pdfDocument` oggetto:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### D: Come posso verificare che i segnalibri siano stati aggiunti?

R: Apri il file PDF generato per verificare che i segnalibri specificati siano stati aggiunti al documento.

#### D: Esiste un limite al numero di segnalibri che posso aggiungere?

R: Generalmente non esiste un limite rigido al numero di segnalibri che è possibile aggiungere, ma per ottenere prestazioni ottimali è necessario considerare le dimensioni e la complessità del documento.

#### D: Posso personalizzare l'aspetto dei segnalibri?

R: Sì, puoi personalizzare ulteriormente l'aspetto, il colore, lo stile e altri attributi dei segnalibri utilizzando le funzionalità Aspose.PDF.