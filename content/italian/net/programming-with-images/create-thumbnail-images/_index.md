---
title: Crea immagini in miniatura nel file PDF
linktitle: Crea immagini in miniatura nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Crea facilmente un'immagine in miniatura nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-images/create-thumbnail-images/
---
Questa guida ti guiderà passo dopo passo su come creare un'immagine in miniatura nel file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e segui i passaggi seguenti:

## Passaggio 1: definire la directory dei documenti

 Prima di iniziare, assicurati di impostare la directory corretta per i documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory contenente i file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: ottieni i nomi di tutti i file PDF in una directory

 In questo passaggio, recupereremo i nomi di tutti i file PDF presenti nella directory specificata utilizzando C#`Directory` classe. I file verranno archiviati in una matrice di stringhe.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Passaggio 3: sfoglia tutti i file PDF e le relative pagine

 In questo passaggio esamineremo tutti i file PDF e le relative pagine per creare miniature delle immagini. Useremo a`for` loop per scorrere tutti i file.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //Apri il documento PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Scorri tutte le pagine del documento
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Crea uno stream per salvare l'immagine in miniatura
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Creare un oggetto Risoluzione
             Resolution resolution = new Resolution(300);
            
             // Crea un dispositivo JPEG con gli attributi specificati
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Converti una pagina specifica e salva l'immagine nello stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Chiudi il flusso
             imageStream.Close();
         }
     }
}
```

### Codice sorgente di esempio per creare immagini in miniatura utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Recupera i nomi di tutti i file PDF in una directory particolare
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
			//JpegDevice jpegDevice = nuovo JpegDevice(500, 700, risoluzione, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Converti una pagina particolare e salva l'immagine in streaming
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Chiudi flusso
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusione

Congratulazioni! Hai creato con successo miniature di immagini da file PDF utilizzando Aspose.PDF per .NET. Le miniature delle immagini vengono salvate nella directory specificata. Ora puoi utilizzare queste miniature per visualizzare un'anteprima visiva dei tuoi file PDF.

### Domande frequenti per creare immagini in miniatura nel file PDF

#### D: Qual è lo scopo di creare immagini in miniatura da file PDF utilizzando Aspose.PDF per .NET?

R: La creazione di immagini in miniatura da file PDF consente di generare piccole anteprime visive di ogni pagina nel PDF, che possono essere utili per visualizzare rapidamente l'anteprima e navigare nel contenuto.

#### D: In che modo Aspose.PDF per .NET facilita la creazione di immagini in miniatura da file PDF?

R: Aspose.PDF per .NET fornisce un processo passo passo per aprire documenti PDF, scorrere le loro pagine, creare immagini in miniatura e salvarle in una directory specificata utilizzando il comando`JpegDevice` classe.

#### D: Perché è importante definire la directory dei documenti prima di iniziare la creazione delle immagini in miniatura?

R: Specificare la directory dei documenti garantisce che i file PDF siano posizionati correttamente e che le immagini in miniatura risultanti vengano salvate nel percorso di output desiderato.

####  D: Come funziona il`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 R: Il`Document` class ti consente di aprire e manipolare documenti PDF. In questo caso viene utilizzato per caricare i file PDF da cui verranno create le immagini in miniatura.

####  D: Che ruolo ha il`JpegDevice` class play in the creation of thumbnail images?

 R: Il`JpegDevice` è responsabile della conversione delle pagine PDF in immagini JPEG, che vengono utilizzate come immagini in miniatura. Ti consente di specificare attributi come larghezza, altezza, risoluzione e qualità.

#### D: Come viene convertita ciascuna pagina del documento PDF in una singola immagine in miniatura?

 R: Un nidificato`for`loop viene utilizzato per scorrere ogni file PDF e le sue pagine. Per ogni pagina, viene creato un dispositivo JPEG con gli attributi specificati e il file`Process` viene utilizzato per convertire la pagina in un'immagine in miniatura e salvarla nello stream.

#### D: Posso regolare la risoluzione o la qualità delle immagini in miniatura risultanti durante il processo di creazione?

 R: Sì, puoi modificare attributi come risoluzione, larghezza, altezza e qualità configurando il file`JpegDevice` oggetto prima di convertire ogni pagina.

#### D: Come posso utilizzare le immagini in miniatura generate nei miei progetti o applicazioni dopo il processo di creazione?

R: Le immagini in miniatura risultanti possono essere utilizzate per fornire un'anteprima visiva dei file PDF, aiutando gli utenti a identificare e navigare rapidamente nel contenuto.

#### : Esiste un limite al numero di immagini in miniatura che possono essere generate da file PDF utilizzando questo processo di creazione?

R: Il numero di immagini in miniatura generate dipende dal numero di pagine in ciascun documento PDF. Ogni pagina verrà convertita in un'immagine in miniatura separata.