---
title: Pagina Web in PDF
linktitle: Pagina Web in PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per convertire una pagina Web in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 320
url: /it/net/document-conversion/web-page-to-pdf/
---
In questo tutorial ti guideremo passo dopo passo su come convertire una pagina Web in PDF utilizzando la libreria Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti. Alla fine di questo tutorial sarai in grado di convertire le pagine web in documenti PDF senza sforzo.

## introduzione
La conversione delle pagine Web in formato PDF è un requisito comune in molte applicazioni. Convertendo i contenuti Web in PDF, puoi preservare facilmente il layout, la formattazione e le immagini della pagina Web originale. Aspose.PDF per .NET è una potente libreria che ti consente di eseguire questa conversione in modo efficiente e accurato.

## Requisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Visual Studio installato sul tuo computer
- Libreria Aspose.PDF per .NET (è possibile scaricarla dal sito Web ufficiale di Aspose)
- Conoscenza base della programmazione C#


## Passaggio 1: definire la directory dei documenti
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso in cui desideri salvare il file PDF generato.

## Passaggio 2: crea una richiesta Web
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Crea un oggetto richiesta web e specifica l'URL della pagina web che desideri convertire. Puoi sostituire l'URL con qualsiasi pagina web desiderata.

## Passaggio 3: ottieni la risposta web
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
 Leggere il contenuto della pagina Web utilizzando a`StreamReader` conservarlo nel`responseFromServer` variabile.

## Passaggio 5: converti HTML in PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://it.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Creare un`MemoryStream` oggetto per caricare il contenuto della pagina web. Quindi, crea un'istanza di`HtmlLoadOptions` e passare l'URL di base della pagina web. Successivamente, crea un file`Document` oggetto utilizzando il flusso caricato e le opzioni di caricamento HTML. Impostare il`IsLandscape` proprietà a`true` se vuoi che il PDF sia in orientamento orizzontale. Infine, salva il documento PDF nella directory specificata

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
	// Timeout in millisecondi prima che la richiesta scada
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
In questo tutorial, abbiamo imparato come convertire una pagina Web in PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo seguito la guida passo passo che spiega il codice sorgente C# fornito. Seguendo queste istruzioni, puoi integrare facilmente la funzionalità di conversione della pagina Web in PDF nelle tue applicazioni .NET.

### Domande frequenti

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di lavorare con documenti PDF in applicazioni C#. Fornisce varie funzionalità, inclusa la conversione di pagine Web in PDF.

#### D: Perché dovrei convertire una pagina web in PDF?

R: La conversione delle pagine Web in PDF è utile per preservare il layout, la formattazione e le immagini del contenuto Web originale. Ti consente di creare un'istantanea della pagina Web per la visualizzazione offline o la condivisione con altri.

#### D: Quali sono i prerequisiti per questo tutorial?

R: Per seguire questo tutorial, è necessario che sul computer sia installato Visual Studio, la libreria Aspose.PDF per .NET e una conoscenza di base della programmazione C#.

#### D: Posso convertire qualsiasi pagina web in PDF?

R: Sì, puoi convertire qualsiasi pagina web in PDF fornendo l'URL della pagina web nel codice. Aspose.PDF per .NET recupererà il contenuto Web e lo convertirà in formato PDF.

#### D: Come posso personalizzare l'output PDF, ad esempio l'orientamento della pagina?

 R: Puoi personalizzare l'output PDF utilizzando opzioni come`IsLandscape` per impostare l'orientamento della pagina. Nel codice fornito,`options.PageInfo.IsLandscape = true` viene utilizzato per creare il PDF con orientamento orizzontale.