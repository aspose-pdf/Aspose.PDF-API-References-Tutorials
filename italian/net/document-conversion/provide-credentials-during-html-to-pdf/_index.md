---
title: Fornire credenziali durante l'HTML in PDF
linktitle: Fornire credenziali durante l'HTML in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per convertire HTML in PDF fornendo credenziali con Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/document-conversion/provide-credentials-during-html-to-pdf/
---

In questo tutorial, ti guideremo attraverso il processo di conversione di un file HTML in PDF fornendo le credenziali quando accedi a un URL sicuro utilizzando Aspose.PDF per .NET. Seguendo i passaggi seguenti, sarai in grado di convertire il contenuto HTML in PDF utilizzando le credenziali appropriate.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: recupera contenuti HTML protetti
In questo passaggio, recupereremo contenuto HTML protetto da un URL utilizzando le credenziali appropriate. Usa il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea una richiesta per l'URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Se necessario per il server, impostare le credenziali.
request.Credentials = CredentialCache.DefaultCredentials;
// Ottieni la risposta.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Ottieni il flusso contenente il contenuto restituito dal server.
Stream dataStream = response. GetResponseStream();
// Apri lo stream utilizzando uno StreamReader per un facile accesso.
StreamReader reader = new StreamReader(dataStream);
// Leggi il contenuto.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si desidera salvare il file PDF risultante.

## Passaggio 2: converti HTML in PDF fornendo le credenziali
Ora caricheremo il contenuto HTML recuperato e lo convertiremo in formato PDF fornendo le credenziali appropriate. Usa il seguente codice:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Carica il file HTML
Document pdfDocument = new Document(stream, options);
```

## Passaggio 3: salvare il file PDF risultante
Infine, salveremo il file PDF risultante. Usa il seguente codice:

```csharp
// Salva il file PDF risultante
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Il codice sopra salva il file PDF risultante con il nome del file`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Codice sorgente di esempio per fornire credenziali durante l'HTML in PDF utilizzando Aspose.PDF per .NET

```csharp
try
{
	
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crea una richiesta per l'URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Se richiesto dal server, impostare le credenziali.
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Carica il file HTML
	Document pdfDocument = new Document(stream, options);
	// Salva il file risultante
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione
In questo tutorial, abbiamo coperto il processo passo-passo di conversione di un file HTML in PDF fornendo le credenziali quando si accede a un URL sicuro utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, sarai in grado di convertire correttamente il contenuto HTML in PDF fornendo le credenziali corrette.