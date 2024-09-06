---
title: Estrai informazioni sulla firma
linktitle: Estrai informazioni sulla firma
second_title: Riferimento API Aspose.PDF per .NET
description: Estrazione delle informazioni sulla firma utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-security-and-signatures/extract-signature-info/
---
Il processo di estrazione delle informazioni sulla firma da un documento PDF può essere molto utile in vari scenari. Sia che tu debba convalidare l'autenticità di un documento firmato o analizzare il certificato utilizzato per la firma, la libreria Aspose.PDF per .NET fornisce una soluzione comoda. In questo tutorial, ti guideremo passo dopo passo nel processo di estrazione delle informazioni sulla firma utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Conoscenza di base del linguaggio di programmazione C#.
2. Libreria Aspose.PDF per .NET installata sul sistema.
3. Un documento PDF valido con uno o più campi firma.

Ora entriamo nei dettagli dell'implementazione.

## Passaggio 1: importazione delle librerie richieste

 Per iniziare, devi importare le librerie necessarie nel tuo progetto C#. In questo caso, dobbiamo importare`Aspose.Pdf` E`System.IO` namespace. Questo può essere fatto aggiungendo il seguente codice all'inizio del tuo file C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Passaggio 2: impostazione del percorso del documento

Successivamente, devi impostare il percorso del documento PDF da cui vuoi estrarre le informazioni sulla firma. Sostituisci`"YOUR DOCUMENTS DIRECTORY"` nel seguente frammento di codice con il percorso effettivo del tuo documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Fase 3: Estrazione delle informazioni sulla firma

Ora, passiamo alla parte principale del codice in cui estraiamo le informazioni sulla firma dal documento PDF. Esaminiamo ogni campo nel modulo del documento e controlliamo se è un campo firma. Se viene trovato un campo firma, procediamo con l'estrazione del certificato. Aggiungiamo il seguente frammento di codice:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Estrarre il certificato
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Passaggio 4: estrazione del certificato

In questo passaggio, estraiamo il certificato dal campo firma e lo salviamo come file. Il certificato estratto può essere ulteriormente analizzato o utilizzato per scopi di convalida. Il frammento di codice seguente illustra il processo di estrazione e salvataggio:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Passo 5

: Salvataggio del certificato

Infine, salviamo il certificato estratto come file. In questo esempio, il certificato viene salvato con il nome "input.cer" nella directory specificata. Puoi modificare il codice in base alle tue esigenze. Ecco il frammento di codice per salvare il certificato:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Ecco fatto! Hai estratto con successo le informazioni sulla firma usando Aspose.PDF per .NET. Sentiti libero di integrare questo codice nelle tue applicazioni o modificarlo in base alle tue esigenze.

### Esempio di codice sorgente per estrarre le informazioni sulla firma utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

In questo tutorial, abbiamo esaminato una guida passo-passo su come estrarre le informazioni sulla firma da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo trattato il processo di importazione delle librerie richieste, l'impostazione del percorso del documento, l'estrazione delle informazioni sulla firma, l'estrazione del certificato e il salvataggio in un file. Seguendo questi passaggi, puoi facilmente recuperare i dettagli della firma e lavorarci come necessario.

### Domande frequenti

#### D: Perché dovrei aver bisogno di estrarre le informazioni sulla firma da un documento PDF?

R: L'estrazione delle informazioni sulla firma da un documento PDF è utile per convalidare l'autenticità di un documento firmato e analizzare il certificato utilizzato per la firma. Questo processo aiuta a garantire l'integrità del contenuto firmato e può essere essenziale per scopi legali e di sicurezza.

#### D: Che cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una libreria che consente agli sviluppatori di lavorare con documenti PDF in applicazioni .NET. Fornisce un'ampia gamma di funzionalità per creare, modificare e interagire con file PDF a livello di programmazione.

#### D: Quali sono i prerequisiti per estrarre le informazioni sulla firma utilizzando Aspose.PDF per .NET?

R: Per estrarre le informazioni sulla firma, è necessaria una conoscenza di base del linguaggio di programmazione C#, la libreria Aspose.PDF per .NET installata sul sistema e un documento PDF valido contenente uno o più campi di firma.

#### D: Come posso importare le librerie necessarie per il processo di estrazione?

A: È possibile importare le librerie necessarie aggiungendo`using` direttive per`Aspose.Pdf` E`System.IO` all'inizio del tuo file C#. Queste direttive ti consentono di usare le classi e i metodi richiesti per estrarre le informazioni sulla firma.

#### D: Come faccio a specificare il documento PDF per estrarre le informazioni sulla firma?

 A: È possibile impostare il percorso del documento PDF sostituendo`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo al tuo documento nel frammento di codice fornito. Questo percorso viene utilizzato per caricare il documento PDF da cui vuoi estrarre le informazioni sulla firma.

#### D: Qual è il processo di estrazione delle informazioni sulla firma da un documento PDF?

R: Il processo di estrazione comporta l'iterazione attraverso i campi del modulo del documento PDF, verificando se ogni campo è un campo di firma e, in tal caso, estraendo il certificato associato. Il certificato estratto può essere salvato come file per ulteriori analisi o convalide.

#### D: Come viene estratto il certificato da un campo firma?

A: Il certificato viene estratto da un campo firma utilizzando il`ExtractCertificate()` metodo fornito dal`SignatureField` classe in Aspose.PDF per .NET. Questo metodo restituisce un flusso contenente i dati del certificato.

#### D: Come posso salvare il certificato estratto come file?

 A: È possibile salvare il certificato estratto come file leggendo il flusso del certificato e scrivendone il contenuto in un file utilizzando`FileStream` classe. Il codice fornito nel tutorial dimostra questo processo.

#### D: Posso utilizzare questo certificato estratto per la convalida della firma?

R: Sì, il certificato estratto può essere utilizzato per la convalida della firma. Puoi analizzare i dettagli del certificato e verificarne l'autenticità per garantire l'integrità del documento firmato.

#### D: Come posso integrare questo codice nelle mie applicazioni?

R: Puoi integrare il codice fornito nelle tue applicazioni C# seguendo la guida passo-passo. Modifica i percorsi e i nomi dei file come necessario e incorpora il codice nei tuoi progetti esistenti.

#### D: Ci sono altre funzionalità in Aspose.PDF per .NET relative alla gestione delle firme?

R: Sì, Aspose.PDF per .NET fornisce una gamma di funzionalità per lavorare con le firme digitali, tra cui la firma di documenti, la verifica delle firme e l'aggiunta di informazioni di marca temporale. Puoi esplorare la documentazione ufficiale per maggiori dettagli su queste funzionalità.

#### D: Dove posso trovare risorse aggiuntive per l'utilizzo di Aspose.PDF per .NET?

 A: Per ulteriori informazioni, tutorial e risorse sull'utilizzo di Aspose.PDF per .NET,[Aspose.PDF per .NET](https://reference.aspose.com/pdf/net/).

#### D: È possibile estrarre le firme dai documenti PDF crittografati?

R: La capacità di estrarre firme da documenti PDF crittografati può dipendere dalle impostazioni di crittografia e dalle autorizzazioni del documento. Potrebbe essere necessario assicurarsi di avere le autorizzazioni necessarie per accedere ed estrarre le informazioni sulla firma.

#### D: Posso estrarre più firme da un singolo documento PDF?

R: Sì, puoi modificare il codice fornito per scorrere tutti i campi firma nel documento PDF ed estrarre le informazioni sulla firma da ognuno di essi. Ciò ti consente di estrarre informazioni su più firme presenti nel documento.

#### D: Quali sono alcuni casi pratici di utilizzo per l'estrazione delle informazioni sulla firma?

R: Alcuni casi di utilizzo pratico per l'estrazione di informazioni sulla firma includono la convalida dell'autenticità di documenti firmati digitalmente, l'analisi dei dettagli del certificato a fini di conformità e la tenuta di un registro delle firme e dei firmatari a fini di audit.

#### D: Ci sono considerazioni legali da tenere in considerazione quando si estraggono informazioni dalla firma?

A: L'estrazione delle informazioni sulla firma può avere implicazioni legali, specialmente quando si gestiscono documenti legalmente vincolanti. Assicurati di rispettare le normative e le leggi pertinenti relative alle firme elettroniche e all'autenticità dei documenti nella tua giurisdizione.