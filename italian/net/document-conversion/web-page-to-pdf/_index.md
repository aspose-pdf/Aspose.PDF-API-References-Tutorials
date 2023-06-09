---
title: Pagina Web in PDF
linktitle: Pagina Web in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire la pagina Web in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/document-conversion/web-page-to-pdf/
---

In questo tutorial, ti guideremo passo dopo passo su come convertire una pagina Web in PDF utilizzando la libreria Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti. Alla fine di questo tutorial, sarai in grado di convertire le pagine Web in documenti PDF senza sforzo.

## introduzione
La conversione di pagine Web in formato PDF è un requisito comune in molte applicazioni. Convertendo il contenuto web in PDF, puoi facilmente conservare il layout, la formattazione e le immagini della pagina web originale. Aspose.PDF per .NET è una potente libreria che consente di eseguire questa conversione in modo efficiente e preciso.

## Requisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Visual Studio installato nel tuo computer
- Aspose.PDF per la libreria .NET (puoi scaricarlo dal sito ufficiale di Aspose)
- Conoscenza di base della programmazione C#


## Passaggio 1: definire la directory dei documenti
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso in cui si desidera salvare il file PDF generato.

## Passaggio 2: creare una richiesta Web
```csharp
WebRequest request = WebRequest.Create("https://it.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Crea un oggetto richiesta web e specifica l'URL della pagina web che desideri convertire. È possibile sostituire l'URL con qualsiasi pagina Web desiderata.

## Passaggio 3: ottenere la risposta Web
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Invia la richiesta web e recupera la risposta dal server.

## Passaggio 4: leggere il contenuto Web
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Leggere il contenuto della pagina Web utilizzando a`StreamReader` e memorizzarlo nel`responseFromServer` variabile.

## Passo 5: Converti HTML in PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://it.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Creare un`MemoryStream` oggetto per caricare il contenuto della pagina web. Quindi, crea un'istanza di`HtmlLoadOptions` e passare l'URL di base della pagina web. Quindi, crea un file`Document` oggetto utilizzando il flusso caricato e le opzioni di caricamento HTML. Impostare il`IsLandscape` proprietà a`true` se vuoi che il PDF sia in orientamento orizzontale. Infine, salva il documento PDF nella directory specificata

.

## Passaggio 6: gestire le eccezioni
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Cattura eventuali eccezioni che possono verificarsi durante il processo di conversione e visualizza il messaggio di errore.

### Codice sorgente di esempio per la pagina Web in PDF utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crea una richiesta per l'URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Se richiesto dal server, impostare le credenziali.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Timeout in millisecondi prima del timeout della richiesta
	// Richiesta.Timeout = 100;

	// Ottieni la risposta.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Ottieni il flusso contenente il contenuto restituito dal server.
	Stream dataStream = response.GetResponseStream();
	// Apri lo stream utilizzando uno StreamReader per un facile accesso.
	StreamReader reader = new StreamReader(dataStream);
	// Leggi il contenuto.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Carica il file HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Salva l'output in formato PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire una pagina Web in PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo seguito la guida dettagliata che spiega il codice sorgente C# fornito. Seguendo queste istruzioni, puoi integrare facilmente la funzionalità di conversione da pagina Web a PDF nelle tue applicazioni .NET.