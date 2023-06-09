---
title: Pagine alle immagini
linktitle: Pagine alle immagini
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente le pagine di un documento PDF in immagini con Aspose.PDF per .NET.
type: docs
weight: 200
url: /it/net/programming-with-images/pages-to-images/
---

In questo tutorial, ti guideremo passo dopo passo per convertire le pagine di un documento PDF in singole immagini utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito mostra come aprire un documento PDF, creare immagini da ogni pagina e salvarle. Spiegheremo ogni passaggio in dettaglio per aiutarti a comprendere il processo in profondità.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza base del linguaggio di programmazione C#.
- La libreria Aspose.PDF per .NET installata nel tuo progetto.
- Un documento PDF che desideri convertire in immagini.

## Passaggio 1: impostazione del progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungi un riferimento alla libreria Aspose.PDF nel tuo progetto.

## Passaggio 2: importare gli spazi dei nomi necessari
All'inizio del file C#, importa gli spazi dei nomi richiesti per accedere alle classi e ai metodi di Aspose.PDF. Ecco un esempio:
```csharp
using System;
using Aspose.Pdf;
using System.IO;
```

## Passaggio 3: inizializzazione di variabili e percorsi
Prima di eseguire la conversione, dobbiamo configurare le variabili e i percorsi necessari.
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: conversione delle pagine in immagini
Per convertire le pagine di un documento PDF in immagini, procedi nel seguente modo:
1.  Apri il documento PDF utilizzando il file`Document` classe.
```csharp
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
```
2.  Scorri ogni pagina del documento usando a`for` ciclo continuo.
```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
//Codice per convertire ogni pagina in un'immagine
}
```
3. All'interno del ciclo, crea un flusso di file per ogni immagine da salvare.
```csharp
using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
{
// Codice per convertire la pagina in un'immagine
}
```
4.  Dentro il`using` bloccare, creare un`Resolution` oggetto per impostare la risoluzione dell'immagine.
```csharp
Resolution resolution = new Resolution(300);
```
5.  Creare un`JpegDevice` oggetto utilizzando la risoluzione e la qualità specificate.
```csharp
JpegDevice jpegDevice = new JpegDevice(resolution, 100);
```
6.  Usa il`Process` metodo del`jpegDevice` oggetto per convertire una pagina specifica in un'immagine e salvare l'immagine nello stream.
```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```
7. Chiudi il flusso di immagini.
```csharp
imageStream.Close();
```
8. Ripetere questi passaggi per ogni pagina del documento.
9. Visualizza un messaggio di successo alla fine del processo.
```csharp
Console.WriteLine("PDF pages converted to individual images successfully!");
```

### Esempio di codice sorgente per Pages To Images utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
	{
		// Crea un dispositivo JPEG con gli attributi specificati
		// Larghezza, Altezza, Risoluzione, Qualità
		// Qualità [0-100], 100 è il massimo
		// Crea oggetto Risoluzione
		Resolution resolution = new Resolution(300);
		// JpegDevice jpegDevice = nuovo JpegDevice(500, 700, risoluzione, 100);
		JpegDevice jpegDevice = new JpegDevice(resolution, 100);
		// Converti una pagina specifica e salva l'immagine per lo streaming
		jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Chiudi flusso
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```

## Conclusione
Seguendo questa guida passo passo, hai imparato a convertire le pagine di un documento PDF in singole immagini utilizzando la libreria Aspose.PDF per .NET. Questo processo comporta l'impostazione del progetto, l'importazione degli spazi dei nomi necessari, l'inizializzazione di variabili e percorsi e la conversione delle pagine in immagini. Ora puoi integrare questo codice nei tuoi progetti e modificarlo in base alle tue esigenze specifiche.