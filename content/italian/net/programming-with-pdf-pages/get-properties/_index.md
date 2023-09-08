---
title: Ottieni proprietà PDF
linktitle: Ottieni proprietà PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per ottenere proprietà PDF come dimensioni della casella e rotazione utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-pdf-pages/get-properties/
---
In questo tutorial ti guideremo attraverso il processo passo passo per ottenere le proprietà di un PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come accedere alle diverse proprietà di una pagina PDF come art box, crop box, crop box, ecc., utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: imposta la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione del file PDF di cui desideri ottenere le proprietà. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: apri il documento PDF
 Successivamente, è necessario aprire il documento PDF utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del file PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Passaggio 3: accedi alla raccolta di pagine
 Ora puoi accedere alla raccolta delle pagine del documento utilizzando il file`Pages` proprietà del`pdfDocument` oggetto.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Passaggio 4: vai a una pagina specifica
Quindi puoi passare a una pagina specifica utilizzando l'indice della pagina nella raccolta. Nell'esempio seguente accediamo alla seconda pagina (indice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Passaggio 5: ottieni le proprietà della pagina
 Ora puoi ottenere le diverse proprietà della pagina PDF, come art box, crop box, crop box, ecc., utilizzando le proprietà corrispondenti del`pdfPage` oggetto.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Codice sorgente di esempio per Ottieni proprietà utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Ottieni la raccolta di pagine
PageCollection pageCollection = pdfDocument.Pages;
// Ottieni una pagina particolare
Page pdfPage = pageCollection[1];
// Ottieni le proprietà della pagina
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusione
Congratulazioni! Hai ottenuto con successo le proprietà di un PDF utilizzando Aspose.PDF per .NET. Hai imparato come aprire un documento PDF, passare a una pagina specifica e ottenere varie proprietà della pagina, come riquadri delle dimensioni e rotazione. Ora puoi utilizzare queste informazioni per personalizzare la gestione dei tuoi file PDF in base alle loro proprietà.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per .NET per ulteriori informazioni sulle funzionalità avanzate e sulle possibilità di personalizzazione.

### Domande frequenti

#### D: Come posso ottenere le proprietà di un PDF utilizzando Aspose.PDF per .NET?

R: Per ottenere le proprietà di un PDF utilizzando Aspose.PDF per .NET, puoi seguire questi passaggi:

1. Imposta la directory dei documenti specificando il percorso del file PDF di cui desideri recuperare le proprietà.
2.  Aprire il documento PDF utilizzando il file`Document` classe di Aspose.PDF, fornendo il percorso corretto al file PDF.
3.  Accedi alla raccolta delle pagine del documento utilizzando il file`Pages` proprietà del`pdfDocument` oggetto.
4. Passa a una pagina specifica utilizzando l'indice della pagina nella raccolta (l'indicizzazione inizia da 1).
5.  Ottieni le diverse proprietà della pagina PDF, come ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Numero di pagina e Rotazione, utilizzando le proprietà corrispondenti della pagina PDF`pdfPage` oggetto.

#### D: Quali sono le diverse proprietà di una pagina PDF che posso recuperare utilizzando Aspose.PDF per .NET?

R: È possibile recuperare varie proprietà di una pagina PDF utilizzando Aspose.PDF per .NET, come ad esempio:

- ArtBox: rappresenta le dimensioni dell'opera d'arte della pagina.
- BleedBox: rappresenta le dimensioni del margine al vivo della pagina.
- CropBox: rappresenta le dimensioni del contenuto visibile della pagina dopo il ritaglio.
- MediaBox: rappresenta le dimensioni del supporto fisico della pagina.
- TrimBox: rappresenta le dimensioni del contenuto tagliato della pagina.
- Rect: rappresenta le dimensioni del riquadro di delimitazione della pagina.
- Numero di pagina: rappresenta il numero di pagina nel documento.
- Ruota: rappresenta l'angolo di rotazione della pagina.

#### D: Come posso accedere a una pagina specifica nel documento PDF per recuperarne le proprietà?

 R: Per accedere a una pagina specifica nel documento PDF e recuperarne le proprietà, è possibile utilizzare il file`Pages` proprietà del`pdfDocument` oggetto per accedere alla raccolta di pagine del documento. Quindi, puoi utilizzare l'indice della pagina nella raccolta per passare alla pagina desiderata. Ad esempio, per accedere alla seconda pagina, è possibile utilizzare`pdfDocument.Pages[1]` (l'indicizzazione inizia da 1).

#### D: Posso eseguire operazioni sulle proprietà recuperate, come la modifica o il ridimensionamento dei box di pagina?

R: Sì, una volta recuperate le proprietà di una pagina PDF utilizzando Aspose.PDF per .NET, è possibile eseguire varie operazioni su di esse. Ad esempio, è possibile modificare le dimensioni dei box di pagina, ruotare la pagina o utilizzare le informazioni recuperate per l'elaborazione e la manipolazione personalizzata del documento PDF.

#### D: Aspose.PDF per .NET supporta l'estrazione di proprietà da file PDF crittografati o protetti da password?

R: Sì, Aspose.PDF per .NET supporta l'estrazione di proprietà da file PDF crittografati o protetti da password. Finché fornisci la password corretta per aprire il documento PDF, puoi accedere e recuperare le sue proprietà utilizzando lo stesso approccio dimostrato nel tutorial.