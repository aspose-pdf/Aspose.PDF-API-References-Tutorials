---
title: Aggiungi segnalibro figlio nel file PDF
linktitle: Aggiungi segnalibro figlio nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi facilmente un segnalibro figlio nel file PDF per una navigazione più organizzata con Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/programming-with-bookmarks/add-child-bookmark/
---
L'aggiunta di segnalibri secondari nel file PDF consente un'organizzazione e una navigazione più strutturate. Con Aspose.PDF per .NET, puoi facilmente aggiungere un sottosegnalibro seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF a cui desideri aggiungere un sottosegnalibro. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Ora apriremo il documento PDF a cui vogliamo aggiungere un sottosegnalibro utilizzando il seguente codice:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Passaggio 4: crea un oggetto segnalibro principale

 In questo passaggio, creeremo un oggetto segnalibro principale utilizzando il file`OutlineItemCollection` classe e impostarne le proprietà come titolo, attributo corsivo e attributo grassetto. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Passaggio 5: crea un oggetto segnalibro figlio

In questo passaggio, creeremo nuovamente un oggetto sotto-segnalibro utilizzando il file`OutlineItemCollection` classe e impostarne le proprietà. Ecco il codice corrispondente:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Passaggio 6: aggiungi il segnalibro secondario al segnalibro principale

 Infine, aggiungiamo il sottosegnalibro creato alla raccolta di sottosegnalibri del segnalibro principale utilizzando il file`Add` metodo dell'oggetto genitore. Ecco il codice corrispondente:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Passaggio 7: aggiungi il segnalibro principale alla raccolta di segnalibri del documento

 Infine, aggiungiamo il segnalibro principale alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`Outlines` proprietà. Ecco il codice corrispondente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Codice sorgente di esempio per Aggiungi segnalibro figlio utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Crea un oggetto segnalibro principale
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Crea un oggetto segnalibro figlio
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Aggiungi il segnalibro figlio nella raccolta dei segnalibri genitore
pdfOutline.Add(pdfChildOutline);
// Aggiungi il segnalibro principale nella raccolta di strutture del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Salva l'output
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per aggiungere un sottosegnalibro con Aspose.PDF per .NET. Puoi utilizzare questo codice per organizzare e strutturare i tuoi segnalibri nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.

### Domande frequenti sull'aggiunta di un segnalibro secondario nel file PDF

#### D: Cosa sono i segnalibri secondari in un file PDF?

R: I segnalibri secondari, noti anche come segnalibri secondari, sono elementi di navigazione all'interno di un documento PDF strutturati gerarchicamente sotto un segnalibro principale. Forniscono un modo per creare un sommario più organizzato e dettagliato per il documento.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

R: Per importare le librerie richieste per il tuo progetto C#, puoi utilizzare la seguente direttiva di importazione:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Queste librerie forniscono le classi e le funzioni necessarie per lavorare con documenti PDF e funzionalità interattive.

#### D: Come posso specificare il percorso della cartella dei documenti?

 R: Nel codice sorgente fornito, è necessario sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella contenente il file PDF con cui desideri lavorare. Ciò garantisce che il codice individui correttamente il file PDF di destinazione.

#### D: Posso creare più livelli di segnalibri secondari?

R: Sì, puoi creare più livelli di segnalibri secondari estendendo il processo descritto nel tutorial. Creando segnalibri principali con sottosegnalibri e nidificandoli ulteriormente, è possibile creare una struttura gerarchica di segnalibri per documenti PDF complessi.

####  D: Qual è lo scopo di`OutlineItemCollection` class?

 R: Il`OutlineItemCollection` La classe in Aspose.PDF per .NET viene utilizzata per creare e gestire i contorni, che sono essenzialmente segnalibri in un documento PDF. Questa classe consente di impostare proprietà come titolo, stile del carattere e azioni per i segnalibri.

#### D: Come posso aggiungere un segnalibro secondario a un segnalibro principale?

 R: Per aggiungere un segnalibro secondario a un segnalibro principale, creane uno nuovo`OutlineItemCollection` oggetto per il sottosegnalibro e impostarne le proprietà. Quindi, usi il file`Add` metodo del segnalibro principale`OutlineItemCollection` per aggiungere il sottosegnalibro alla raccolta del genitore.

#### D: Posso personalizzare l'aspetto dei segnalibri secondari?

R: Sì, analogamente ai segnalibri principali, puoi personalizzare l'aspetto dei segnalibri secondari impostando proprietà come titolo, stile del carattere e altri attributi. Ciò consente di creare segnalibri visivamente distintivi e informativi.

#### D: Aspose.PDF per .NET è compatibile con altri linguaggi di programmazione?

R: Aspose.PDF per .NET è progettato specificamente per ambienti C# e .NET. Tuttavia, Aspose offre librerie simili per altri linguaggi di programmazione come Java e Android, ciascuna su misura per le rispettive piattaforme.

#### D: In che modo i segnalibri secondari migliorano la navigazione nei PDF?

R: I segnalibri secondari migliorano la navigazione nei PDF fornendo un sommario più strutturato e organizzato. Gli utenti possono accedere rapidamente a sezioni specifiche del documento attraverso la struttura gerarchica dei segnalibri.