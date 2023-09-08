---
title: Aggiorna le dimensioni della pagina PDF
linktitle: Aggiorna le dimensioni della pagina PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per aggiornare le dimensioni della pagina PDF utilizzando Aspose.PDF per .NET. Controlla le dimensioni in base alle tue esigenze.
type: docs
weight: 150
url: /it/net/programming-with-pdf-pages/update-dimensions/
---
In questo tutorial ti guideremo attraverso il processo passo passo per aggiornare le dimensioni della pagina in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come modificare le dimensioni della pagina in un documento PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento PDF modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Quindi puoi aprire il documento PDF esistente utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Passaggio 3: ottieni la raccolta di pagine
 Ora puoi accedere alla raccolta delle pagine del documento PDF utilizzando il file`Pages` proprietà del`Document` classe.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Passaggio 4: ottieni una pagina specifica
Quindi puoi selezionare una pagina specifica del documento utilizzando l'indice della pagina nella raccolta. In questo esempio utilizziamo la seconda pagina (indice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Passaggio 5: definire le nuove dimensioni della pagina
 Ora puoi impostare la nuova dimensione della pagina utilizzando il file`SetPageSize()` metodo del`Page`oggetto. In questo esempio, impostiamo le dimensioni della pagina su A4 (11,7 x 8,3 pollici), convertite in punti (1 pollice = 72 punti).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Passaggio 6: salva il documento aggiornato
 Infine, puoi salvare il documento PDF aggiornato in un file utilizzando il formato`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Codice sorgente di esempio per Update Dimensions utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Ottieni la raccolta di pagine
PageCollection pageCollection = pdfDocument.Pages;
// Ottieni una pagina particolare
Page pdfPage = pageCollection[1];
// Imposta la dimensione della pagina come A4 (11,7 x 8,3 pollici) e in Aspose.Pdf, 1 pollice = 72 punti
// Quindi le dimensioni A4 in punti saranno (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Salva il documento aggiornato
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusione
In questo tutorial, abbiamo imparato come aggiornare le dimensioni di una pagina in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questa guida passo passo, puoi modificare facilmente le dimensioni di una pagina in un documento PDF secondo necessità. Aspose.PDF offre un'API potente e flessibile per lavorare con file PDF ed eseguire varie manipolazioni, inclusa la modifica delle dimensioni della pagina. Con questa conoscenza, puoi controllare e personalizzare le dimensioni delle tue pagine PDF per soddisfare le tue esigenze specifiche.

### Domande frequenti per l'aggiornamento delle dimensioni della pagina PDF

#### D: Come posso aggiornare le dimensioni di una pagina specifica in un documento PDF utilizzando Aspose.PDF per .NET?

R: Per aggiornare le dimensioni di una pagina specifica in un documento PDF utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Imposta la directory dei documenti specificando il percorso in cui si trova il file PDF originale e dove desideri salvare il file PDF aggiornato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.
2.  Aprire il documento PDF esistente da aggiornare utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento PDF originale.
3.  Accedi alla raccolta delle pagine del documento PDF utilizzando il file`Pages` proprietà del`Document` classe.
4. Seleziona la pagina specifica che desideri aggiornare dalla raccolta di pagine utilizzando l'indice della pagina. Nel codice sorgente C# fornito, utilizziamo la seconda pagina (indice 1).
5.  Definire la nuova dimensione della pagina utilizzando`SetPageSize()` metodo del`Page` oggetto. Nell'esempio, impostiamo le dimensioni della pagina sul formato A4 (11,7 x 8,3 pollici), convertite in punti (1 pollice = 72 punti).
6.  Salvare il documento PDF aggiornato in un file utilizzando il file`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

#### D: Posso aggiornare contemporaneamente le dimensioni di più pagine nel documento PDF?

R: Sì, puoi modificare il codice sorgente fornito per aggiornare contemporaneamente le dimensioni di più pagine nel documento PDF. Invece di selezionare una pagina specifica (come mostrato nel passaggio 4), puoi scorrere tutte le pagine della raccolta di pagine e impostare la dimensione della pagina desiderata per ciascuna pagina.

#### D: Come posso convertire le dimensioni della pagina da pollici a punti quando utilizzo Aspose.PDF per .NET?

 R: In Aspose.PDF per .NET, l'unità di misura utilizzata per le dimensioni della pagina sono i punti, dove 1 pollice equivale a 72 punti. Per convertire i pollici in punti è possibile utilizzare la formula:`points = inches * 72`. Ad esempio, per impostare una dimensione pagina di 11,7 x 8,3 pollici, puoi calcolare le dimensioni corrispondenti in punti come (11,7 * 72) e (8,3 * 72).

#### D: L'aggiornamento delle dimensioni di una pagina influirà sul layout del contenuto del documento PDF?

R: Sì, l'aggiornamento delle dimensioni di una pagina influirà sul layout del contenuto del documento PDF su quella pagina specifica. Quando modifichi le dimensioni della pagina, il contenuto della pagina verrà adattato di conseguenza per adattarsi alle nuove dimensioni.

#### D: È possibile annullare le modifiche e ripristinare le dimensioni originali della pagina dopo averle aggiornate?

R: Sì, se desideri annullare le modifiche e ripristinare le dimensioni originali della pagina, puoi conservare una copia del documento PDF originale prima di apportare modifiche oppure riaprire nuovamente il documento PDF originale senza salvare le modifiche. In questo modo verranno preservate le dimensioni originali.