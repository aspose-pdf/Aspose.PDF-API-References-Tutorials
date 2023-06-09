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