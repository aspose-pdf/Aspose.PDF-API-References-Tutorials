---
title: Estrai le informazioni sulla firma
linktitle: Estrai le informazioni sulla firma
second_title: Aspose.PDF per riferimento API .NET
description: Estrazione delle informazioni sulla firma utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-security-and-signatures/extract-signature-info/
---
Il processo di estrazione delle informazioni sulla firma da un documento PDF può essere molto utile in vari scenari. Se è necessario convalidare l'autenticità di un documento firmato o analizzare il certificato utilizzato per la firma, la libreria Aspose.PDF per .NET fornisce una soluzione conveniente. In questo tutorial, ti guideremo attraverso il processo dettagliato di estrazione delle informazioni sulla firma utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Conoscenza base del linguaggio di programmazione C#.
2. Aspose.PDF per la libreria .NET installata sul tuo sistema.
3. Un documento PDF valido con uno o più campi firma.

Ora, tuffiamoci nei dettagli di implementazione.

## Passaggio 1: importazione delle librerie richieste

 Per iniziare, devi importare le librerie necessarie nel tuo progetto C#. In questo caso, dobbiamo importare il file`Aspose.Pdf` E`System.IO` spazi dei nomi. Questo può essere fatto aggiungendo il seguente codice all'inizio del file C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Passaggio 2: impostazione del percorso del documento

Successivamente, è necessario impostare il percorso del documento PDF da cui si desidera estrarre le informazioni sulla firma. Sostituire`"YOUR DOCUMENTS DIRECTORY"` nel seguente frammento di codice con il percorso effettivo del documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Passaggio 3: estrazione delle informazioni sulla firma

Passiamo ora alla parte principale del codice in cui estraiamo le informazioni sulla firma dal documento PDF. Iteriamo attraverso ogni campo nel modulo del documento e controlliamo se si tratta di un campo firma. Se viene trovato un campo firma, si procede con l'estrazione del certificato. Aggiungi il seguente frammento di codice:

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

In questo passaggio, estraiamo il certificato dal campo della firma e lo salviamo come file. Il certificato estratto può essere ulteriormente analizzato o utilizzato per scopi di convalida. Il frammento di codice seguente mostra il processo di estrazione e salvataggio:

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

## Passaggio 5

: Salvataggio del certificato

Infine, salviamo il certificato estratto come file. In questo esempio, il certificato viene salvato con il nome "input.cer" nella directory specificata. È possibile modificare il codice in base alle proprie esigenze. Ecco lo snippet di codice per salvare il certificato:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Questo è tutto! Hai estratto correttamente le informazioni sulla firma utilizzando Aspose.PDF per .NET. Sentiti libero di integrare questo codice nelle tue applicazioni o modificarlo in base alle tue esigenze.

### Esempio di codice sorgente per estrarre le informazioni sulla firma utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
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

In questo tutorial, abbiamo seguito una guida dettagliata su come estrarre le informazioni sulla firma da un documento PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo coperto il processo di importazione delle librerie richieste, impostazione del percorso del documento, estrazione delle informazioni sulla firma, estrazione del certificato e salvataggio in un file. Seguendo questi passaggi, puoi recuperare facilmente i dettagli della firma e lavorarci secondo necessità.

### FAQ

#### D: Perché dovrei estrarre le informazioni sulla firma da un documento PDF?

R: L'estrazione delle informazioni sulla firma da un documento PDF è utile per convalidare l'autenticità di un documento firmato e analizzare il certificato utilizzato per la firma. Questo processo aiuta a garantire l'integrità del contenuto firmato e può essere essenziale per scopi legali e di sicurezza.

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una libreria che consente agli sviluppatori di lavorare con documenti PDF in applicazioni .NET. Fornisce un'ampia gamma di funzionalità per la creazione, la modifica e l'interazione con i file PDF a livello di programmazione.

#### D: Quali sono i prerequisiti per l'estrazione delle informazioni sulla firma utilizzando Aspose.PDF per .NET?

R: Per estrarre le informazioni sulla firma, è necessaria una conoscenza di base del linguaggio di programmazione C#, della libreria Aspose.PDF per .NET installata nel sistema e di un documento PDF valido contenente uno o più campi firma.

#### D: Come si importano le librerie richieste per il processo di estrazione?

R: Puoi importare le librerie necessarie aggiungendo il file`using` direttive per`Aspose.Pdf` E`System.IO` all'inizio del file C#. Queste direttive consentono di utilizzare le classi ei metodi richiesti per l'estrazione delle informazioni sulla firma.

#### D: Come si specifica il documento PDF per l'estrazione delle informazioni sulla firma?

 R: Puoi impostare il percorso del documento PDF sostituendolo`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo del documento nello snippet di codice fornito. Questo percorso viene utilizzato per caricare il documento PDF da cui si desidera estrarre le informazioni sulla firma.

#### D: Qual è il processo di estrazione delle informazioni sulla firma da un documento PDF?

R: Il processo di estrazione prevede l'iterazione dei campi modulo del documento PDF, il controllo se ogni campo è un campo firma e, in tal caso, l'estrazione del certificato associato. Il certificato estratto può essere salvato come file per ulteriori analisi o validazioni.

#### D: Come viene estratto il certificato da un campo firma?

R: Il certificato viene estratto da un campo firma utilizzando il file`ExtractCertificate()` metodo fornito dal`SignatureField` classe in Aspose.PDF per .NET. Questo metodo restituisce un flusso contenente i dati del certificato.

#### D: Come posso salvare il certificato estratto come file?

 R: È possibile salvare il certificato estratto come file leggendo il flusso del certificato e scrivendone il contenuto in un file utilizzando l'estensione`FileStream` classe. Il codice fornito nell'esercitazione illustra questo processo.

#### D: Posso utilizzare questo certificato estratto per la convalida della firma?

R: Sì, il certificato estratto può essere utilizzato per la convalida della firma. È possibile analizzare i dettagli del certificato e verificarne l'autenticità per garantire l'integrità del documento firmato.

#### D: Come posso integrare questo codice nelle mie applicazioni?

R: Puoi integrare il codice fornito nelle tue applicazioni C# seguendo la guida dettagliata. Modifica i percorsi e i nomi dei file secondo necessità e incorpora il codice nei tuoi progetti esistenti.

#### D: Ci sono altre funzionalità in Aspose.PDF per .NET relative alla gestione delle firme?

R: Sì, Aspose.PDF per .NET offre una gamma di funzionalità per lavorare con le firme digitali, tra cui la firma di documenti, la verifica delle firme e l'aggiunta di informazioni sulla marca temporale. Puoi esplorare la documentazione ufficiale per maggiori dettagli su queste funzionalità.

#### D: Dove posso trovare risorse aggiuntive per l'utilizzo di Aspose.PDF per .NET?

 R: Per ulteriori informazioni, esercitazioni e risorse sull'utilizzo di Aspose.PDF per .NET,[Aspose.PDF per .NET](https://reference.aspose.com/pdf/net/).

#### D: È possibile estrarre firme da documenti PDF crittografati?

R: La capacità di estrarre firme da documenti PDF crittografati può dipendere dalle impostazioni di crittografia e dalle autorizzazioni del documento. Potrebbe essere necessario assicurarsi di disporre delle autorizzazioni necessarie per accedere ed estrarre le informazioni sulla firma.

#### D: Posso estrarre più firme da un singolo documento PDF?

R: Sì, è possibile modificare il codice fornito per scorrere tutti i campi della firma nel documento PDF ed estrarre le informazioni sulla firma da ciascuno di essi. Ciò consente di estrarre informazioni su più firme presenti nel documento.

#### D: Quali sono alcuni casi d'uso pratici per l'estrazione delle informazioni sulla firma?

R: Alcuni casi d'uso pratici per l'estrazione delle informazioni sulla firma includono la convalida dell'autenticità dei documenti firmati digitalmente, l'analisi dei dettagli del certificato ai fini della conformità e la conservazione di un registro delle firme e dei firmatari a fini di controllo.

#### D: Ci sono considerazioni legali quando si estraggono le informazioni sulla firma?

R: L'estrazione delle informazioni sulla firma può avere implicazioni legali, soprattutto quando si gestiscono documenti legalmente vincolanti. Assicurati di rispettare le normative e le leggi pertinenti relative alle firme elettroniche e all'autenticità dei documenti nella tua giurisdizione.