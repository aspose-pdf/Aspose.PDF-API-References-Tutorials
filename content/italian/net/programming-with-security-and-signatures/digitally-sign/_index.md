---
title: Firma digitale nel file PDF
linktitle: Firma digitale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come firmare digitalmente un file PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-security-and-signatures/digitally-sign/
---
In questo tutorial, ti guideremo attraverso il processo di firma digitale in un file PDF usando Aspose.PDF per .NET. La firma digitale garantisce l'autenticità e l'integrità del documento, aggiungendo un'impronta digitale elettronica univoca.

## Fase 1: Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Conoscenza di base del linguaggio di programmazione C#
- Installazione di Visual Studio sul tuo computer
- Libreria Aspose.PDF per .NET installata

## Passaggio 2: configurazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Aprire Visual Studio e creare un nuovo progetto C#.
2. Importa gli spazi dei nomi richiesti nel tuo file di codice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Fase 3: Firma digitale

Il primo passo è firmare digitalmente il file PDF. Il codice fornito mostra come creare una firma digitale con Aspose.PDF per .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Questo codice carica un file PDF, crea una firma digitale con un aspetto specificato, quindi salva il file PDF con la firma aggiunta.

## Fase 4: Verifica della firma

Dopo aver aggiunto la firma digitale, puoi verificare se il file PDF contiene una firma valida.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Fai qualcosa
                     }
                 }
             }
         }
     }
}
```

Questo codice verifica la prima firma del file PDF ed esegue azioni aggiuntive se la firma è certificata e dispone di autorizzazioni specifiche.

### Esempio di codice sorgente per la firma digitale tramite Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Utilizzare oggetti PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Imposta l'aspetto della firma
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Crea uno qualsiasi dei tre tipi di firma
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Salva il file PDF di output
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Ci sono firme?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifica prima
				{
					if (signature.IsCertified) // Certificato?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Ottieni l'autorizzazione di accesso
						{
							// Fai qualcosa
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

Congratulazioni! Hai eseguito con successo una firma digitale su un file PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto il processo passo dopo passo, dall'aggiunta della firma digitale alla verifica della sua validità. Ora puoi utilizzare questa funzionalità per proteggere i tuoi file PDF con firme digitali.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial ti guida attraverso il processo di firma digitale di un file PDF usando Aspose.PDF per .NET. Le firme digitali aggiungono un'impronta digitale elettronica per garantire l'autenticità e l'integrità del documento.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di avere una conoscenza di base del linguaggio di programmazione C#, di avere installato Visual Studio e di avere installato la libreria Aspose.PDF per .NET.

#### D: Come si imposta l'ambiente di sviluppo?

R: Seguire i passaggi indicati per configurare l'ambiente di sviluppo, inclusa la creazione di un nuovo progetto C# in Visual Studio e l'importazione degli spazi dei nomi richiesti.

#### D: Come faccio ad aggiungere una firma digitale a un file PDF?

 A: Il codice di esempio fornito dimostra come caricare un file PDF, creare una firma digitale, specificare l'aspetto e salvare il file PDF firmato. La firma digitale viene aggiunta utilizzando`Certify` metodo del`PdfFileSignature` oggetto.

#### D: Come posso verificare la validità di una firma digitale?

A: Dopo aver aggiunto la firma digitale, puoi usare il codice di esempio per verificare la validità della firma. Controlla se la firma è certificata e ha permessi di accesso specifici.

####  D: Cosa significa?`PKCS7` object represent?

 A: Il`PKCS7` object viene utilizzato per fornire la funzionalità crittografica per le firme digitali. Viene utilizzato per creare la firma digitale nel codice di esempio fornito.

#### D: Posso personalizzare l'aspetto della firma digitale?

 A: Sì, puoi personalizzare l'aspetto della firma digitale specificando il percorso di un'immagine nel`SignatureAppearance` proprietà del`PdfFileSignature` oggetto.

#### D: Cosa succede se la firma non è valida?

R: Se la firma non è valida, il processo di verifica fallirà e le azioni corrispondenti all'interno del blocco del codice di verifica non verranno eseguite.

#### D: Come posso garantire la sicurezza delle mie firme digitali?

R: Le firme digitali sono sicure per progettazione e utilizzano tecniche crittografiche per garantire autenticità e integrità. Assicurati di mantenere la tua chiave privata al sicuro e di seguire le best practice per la gestione delle firme digitali.

#### D: Posso aggiungere più firme digitali a un PDF?

 A: Sì, puoi aggiungere più firme digitali a un file PDF utilizzando`PdfFileSignature` oggetto`Sign` O`Certify` metodi. Ogni firma avrà il suo aspetto e la sua configurazione.