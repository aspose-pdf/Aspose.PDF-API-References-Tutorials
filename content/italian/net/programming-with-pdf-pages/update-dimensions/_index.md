---
title: Aggiorna le dimensioni della pagina PDF
linktitle: Aggiorna le dimensioni della pagina PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per aggiornare le dimensioni della pagina PDF usando Aspose.PDF per .NET. Controlla le dimensioni in base alle tue esigenze.
type: docs
weight: 150
url: /it/net/programming-with-pdf-pages/update-dimensions/
---
In questo tutorial, ti guideremo passo dopo passo nel processo per aggiornare le dimensioni di pagina in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come modificare le dimensioni di pagina in un documento PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Una conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Per prima cosa, devi impostare il percorso della tua directory dei documenti. Questa è la posizione in cui vuoi salvare il tuo documento PDF modificato. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: aprire il documento PDF
 Quindi puoi aprire il documento PDF esistente utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del documento.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Passaggio 3: Ottieni la raccolta di pagine
 Ora puoi accedere alla raccolta di pagine del documento PDF utilizzando`Pages` proprietà del`Document` classe.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Passaggio 4: Ottieni una pagina specifica
Quindi puoi selezionare una pagina specifica del documento usando l'indice della pagina nella raccolta. In questo esempio, stiamo usando la seconda pagina (indice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Passaggio 5: definire le nuove dimensioni della pagina
 Ora puoi impostare la nuova dimensione della pagina utilizzando`SetPageSize()` metodo del`Page`oggetto. In questo esempio, stiamo impostando le dimensioni della pagina su A4 (11,7 x 8,3 pollici), convertite in punti (1 pollice = 72 punti).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Passaggio 6: Salvare il documento aggiornato
 Infine, puoi salvare il documento PDF aggiornato in un file utilizzando`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Update Dimensions utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Ottieni la raccolta di pagine
PageCollection pageCollection = pdfDocument.Pages;
// Ottieni una pagina specifica
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
In questo tutorial, abbiamo imparato come aggiornare le dimensioni di una pagina in un documento PDF usando Aspose.PDF per .NET. Seguendo questa guida passo passo, puoi facilmente modificare le dimensioni di una pagina in un documento PDF in base alle tue esigenze. Aspose.PDF offre un'API potente e flessibile per lavorare con file PDF ed eseguire varie manipolazioni, tra cui la modifica delle dimensioni della pagina. Con questa conoscenza, puoi controllare e personalizzare le dimensioni delle tue pagine PDF per soddisfare le tue esigenze specifiche.

### FAQ per aggiornare le dimensioni delle pagine PDF

#### D: Come posso aggiornare le dimensioni di una pagina specifica in un documento PDF utilizzando Aspose.PDF per .NET?

A: Per aggiornare le dimensioni di una pagina specifica in un documento PDF utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Imposta la directory dei documenti specificando il percorso in cui si trova il tuo file PDF originale e dove vuoi salvare il file PDF aggiornato. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.
2.  Aprire il documento PDF esistente da aggiornare utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto al documento PDF originale.
3.  Accedi alla raccolta di pagine del documento PDF utilizzando`Pages` proprietà del`Document` classe.
4. Seleziona la pagina specifica che vuoi aggiornare dalla raccolta di pagine usando l'indice della pagina. Nel codice sorgente C# fornito, stiamo usando la seconda pagina (indice 1).
5.  Definisci la nuova dimensione della pagina utilizzando`SetPageSize()` metodo del`Page` oggetto. Nell'esempio, abbiamo impostato le dimensioni della pagina su formato A4 (11,7 x 8,3 pollici), convertite in punti (1 pollice = 72 punti).
6.  Salvare il documento PDF aggiornato in un file utilizzando`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

#### D: Posso aggiornare contemporaneamente le dimensioni di più pagine del documento PDF?

R: Sì, puoi modificare il codice sorgente fornito per aggiornare le dimensioni di più pagine nel documento PDF contemporaneamente. Invece di selezionare una pagina specifica (come mostrato nel passaggio 4), puoi scorrere tutte le pagine nella raccolta di pagine e impostare la dimensione di pagina desiderata per ogni pagina.

#### D: Come faccio a convertire le dimensioni di una pagina da pollici a punti quando utilizzo Aspose.PDF per .NET?

 A: In Aspose.PDF per .NET, l'unità di misura utilizzata per le dimensioni della pagina è il punto, dove 1 pollice equivale a 72 punti. Per convertire i pollici in punti, puoi usare la formula:`points = inches * 72`Ad esempio, per impostare una dimensione di pagina di 11,7 x 8,3 pollici, è possibile calcolare le dimensioni corrispondenti in punti come (11,7 * 72) e (8,3 * 72).

#### D: L'aggiornamento delle dimensioni di una pagina inciderà sul layout del contenuto del documento PDF?

R: Sì, l'aggiornamento delle dimensioni di una pagina inciderà sul layout del contenuto del documento PDF su quella pagina specifica. Quando modifichi le dimensioni della pagina, il contenuto della pagina verrà regolato di conseguenza per adattarsi alle nuove dimensioni.

#### D: È possibile annullare le modifiche e ripristinare le dimensioni originali della pagina dopo averle aggiornate?

R: Sì, se vuoi annullare le modifiche e ripristinare le dimensioni originali della pagina, puoi conservare una copia del documento PDF originale prima di apportare modifiche o riaprire il documento PDF originale senza salvare le modifiche. In questo modo, le dimensioni originali saranno conservate.