---
title: Crea immagini in miniatura nel file PDF
linktitle: Crea immagini in miniatura nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente immagini in miniatura in file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-images/create-thumbnail-images/
---
Questa guida ti guiderà passo dopo passo nella creazione di un'immagine miniatura in un file PDF usando Aspose.PDF per .NET. Assicurati di aver già impostato il tuo ambiente e segui i passaggi sottostanti:

## Passaggio 1: definire la directory dei documenti

Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso alla directory contenente i file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: ottenere i nomi di tutti i file PDF in una directory

 In questo passaggio, recupereremo i nomi di tutti i file PDF presenti nella directory specificata utilizzando C#`Directory`classe. I file verranno archiviati in un array di stringhe.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Passaggio 3: Sfoglia tutti i file PDF e le loro pagine

 In questo passaggio, esamineremo tutti i file PDF e le loro pagine per creare miniature delle immagini. Utilizzeremo un`for` ciclo per scorrere tutti i file.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Apri il documento PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Sfoglia tutte le pagine del documento
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Crea uno stream per salvare l'immagine in miniatura
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Crea un oggetto Risoluzione
             Resolution resolution = new Resolution(300);
            
             // Crea un dispositivo JPEG con gli attributi specificati
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Converti una pagina specifica e salva l'immagine nel flusso
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Chiudi il flusso
             imageStream.Close();
         }
     }
}
```

### Esempio di codice sorgente per creare immagini in miniatura utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Recupera i nomi di tutti i file PDF in una directory particolare
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Scorrere tutte le voci dei file nell'array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Apri documento
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Crea oggetto Risoluzione
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, risoluzione, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Converti una pagina specifica e salva l'immagine in streaming
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Chiudi flusso
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusione

Congratulazioni! Hai creato con successo miniature di immagini da file PDF usando Aspose.PDF per .NET. Le miniature di immagini vengono salvate nella directory specificata. Ora puoi usare queste miniature per visualizzare un'anteprima visiva dei tuoi file PDF.

### FAQ per creare immagini in miniatura in file PDF

#### D: Qual è lo scopo della creazione di immagini in miniatura da file PDF utilizzando Aspose.PDF per .NET?

R: La creazione di immagini in miniatura da file PDF consente di generare piccole anteprime visive di ogni pagina del PDF, utili per visualizzare in anteprima e navigare rapidamente nel contenuto.

#### D: In che modo Aspose.PDF per .NET facilita la creazione di immagini in miniatura da file PDF?

 A: Aspose.PDF per .NET fornisce un processo passo dopo passo per aprire documenti PDF, scorrere le loro pagine, creare immagini in miniatura e salvarle in una directory specificata utilizzando`JpegDevice` classe.

#### D: Perché è importante definire la directory del documento prima di iniziare la creazione delle immagini in miniatura?

R: Specificando la directory del documento si garantisce che i file PDF siano posizionati correttamente e che le immagini in miniatura risultanti vengano salvate nel percorso di output desiderato.

####  D: Come funziona il`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: Il`Document` classe consente di aprire e manipolare documenti PDF. In questo caso, viene utilizzata per caricare i file PDF da cui verranno create le immagini in miniatura.

####  D: Quale ruolo ha il`JpegDevice` class play in the creation of thumbnail images?

 A: Il`JpegDevice` La classe è responsabile della conversione delle pagine PDF in immagini JPEG, che vengono utilizzate come immagini miniatura. Consente di specificare attributi quali larghezza, altezza, risoluzione e qualità.

#### D: Come viene convertita ogni pagina del documento PDF in una singola immagine in miniatura?

 A: Un annidato`for` loop viene utilizzato per scorrere ogni file PDF e le sue pagine. Per ogni pagina, viene creato un dispositivo JPEG con attributi specificati e il`Process` Il metodo viene utilizzato per convertire la pagina in un'immagine in miniatura e salvarla nel flusso.

#### D: Posso modificare la risoluzione o la qualità delle immagini in miniatura risultanti durante il processo di creazione?

A: Sì, puoi modificare attributi come risoluzione, larghezza, altezza e qualità configurando il`JpegDevice` oggetto prima di convertire ogni pagina.

#### D: Come posso utilizzare le immagini in miniatura generate nei miei progetti o nelle mie applicazioni dopo il processo di creazione?

R: Le immagini in miniatura risultanti possono essere utilizzate per fornire un'anteprima visiva dei file PDF, aiutando gli utenti a identificare e navigare rapidamente nel contenuto.

#### : Esiste un limite al numero di immagini in miniatura che possono essere generate da file PDF utilizzando questo processo di creazione?

A: Il numero di miniature generate dipende dal numero di pagine di ogni documento PDF. Ogni pagina verrà convertita in una miniatura separata.