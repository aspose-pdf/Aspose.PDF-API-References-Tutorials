---
title: Ottieni tutti gli allegati nel file PDF
linktitle: Ottieni tutti gli allegati nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come ottenere tutti gli allegati nel file PDF con Aspose.PDF per .NET. Guida passo passo per una facile gestione.
type: docs
weight: 40
url: /it/net/programming-with-attachments/get-all-the-attachments/
---
In questo tutorial, ti guideremo passo dopo passo attraverso il seguente codice sorgente C# per ottenere tutti gli allegati nel file PDF utilizzando Aspose.PDF per .NET.

Assicurati di aver installato la libreria Aspose.PDF e di configurare il tuo ambiente di sviluppo prima di iniziare. Possiede inoltre una conoscenza base della programmazione C#.

### Passaggio 1: impostazione della directory dei documenti

Nel codice sorgente fornito, è necessario specificare la directory in cui si trova il file PDF da cui si desidera ottenere gli allegati. Modificare la variabile "dataDir" nella directory desiderata.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passaggio 2: apri il documento PDF esistente

Apriamo il documento PDF esistente utilizzando il percorso specificato.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Passaggio 3: ottenere la raccolta di allegati

Otteniamo la raccolta degli allegati dal documento.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Passaggio 4: recupero degli allegati

Esaminiamo la raccolta per ottenere tutti gli allegati e visualizzare le relative informazioni. Salviamo anche gli allegati in singoli file.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Controlla se i parametri dell'oggetto contengono informazioni aggiuntive
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Recuperare l'allegato e salvarlo in un file
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Codice sorgente di esempio per Ottieni tutti gli allegati utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Ottieni la raccolta di file incorporati
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Ottieni il conteggio dei file incorporati
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Sfoglia la raccolta per ottenere tutti gli allegati
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Controlla se l'oggetto parametro contiene i parametri
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// Ottieni l'allegato e scrivi su file o streaming
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusione

In questo tutorial, abbiamo spiegato come ottenere tutti gli allegati da un file PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questa conoscenza per estrarre e manipolare gli allegati dai tuoi file PDF.

## Domande frequenti per ottenere tutti gli allegati nel file PDF

#### D: Perché dovrei recuperare tutti gli allegati da un documento PDF?

R: Il recupero degli allegati consente di accedere e manipolare file aggiuntivi incorporati in un PDF, che possono essere utili per l'archiviazione, la condivisione o l'ulteriore elaborazione.

#### D: Quali tipi di file possono essere allegati a un documento PDF?

R: I documenti PDF possono contenere un'ampia gamma di file allegati, tra cui immagini, documenti, fogli di calcolo, file audio e altro ancora.

#### D: In che modo questo tutorial mi aiuta a recuperare gli allegati da un PDF utilizzando Aspose.PDF per .NET?

R: Questo tutorial fornisce istruzioni dettagliate e codice sorgente C# per accedere e recuperare tutti gli allegati all'interno di un documento PDF.

#### D: Posso recuperare allegati specifici anziché tutti gli allegati utilizzando questo tutorial?

R: Sì, puoi modificare il codice fornito per recuperare selettivamente gli allegati in base alle tue esigenze.

#### D: Quali informazioni su ciascun allegato posso ottenere utilizzando questo tutorial?

R: Questo tutorial mostra come recuperare e visualizzare dettagli come il nome dell'allegato, la descrizione, il tipo MIME, la data di creazione, la data di modifica e la dimensione.

#### D: Come vengono salvati gli allegati recuperati utilizzando questo tutorial?

R: Il tutorial guida l'utente nel salvataggio di ciascun allegato recuperato come file separato nella directory specificata.

#### D: Posso utilizzare queste conoscenze per estrarre allegati da file PDF protetti da password?

R: Sì, puoi applicare principi simili per recuperare allegati da file PDF protetti da password utilizzando Aspose.PDF per .NET.

#### D: In che modo Aspose.PDF per .NET facilita il recupero degli allegati?

R: Aspose.PDF per .NET fornisce un'API intuitiva che consente di accedere e manipolare facilmente gli allegati nei documenti PDF.

#### D: Esistono scenari specifici in cui è consigliabile il recupero degli allegati?

R: Il recupero degli allegati è utile quando è necessario accedere ai file incorporati in un PDF, ad esempio estrarre immagini, file audio o documenti aggiuntivi.