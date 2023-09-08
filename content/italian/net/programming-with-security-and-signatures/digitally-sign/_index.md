---
title: Accedi digitalmente al file PDF
linktitle: Accedi digitalmente al file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come accedere digitalmente al file PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-security-and-signatures/digitally-sign/
---
In questo tutorial ti guideremo attraverso il processo di firma digitale nel file PDF utilizzando Aspose.PDF per .NET. La firma digitale garantisce l'autenticità e l'integrità del documento, mediante l'apposizione di un'impronta digitale unica.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#
- Installazione di Visual Studio sul tuo computer
- Libreria Aspose.PDF per .NET installata

## Passaggio 2: configurazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Apri Visual Studio e crea un nuovo progetto C#.
2. Importa gli spazi dei nomi richiesti nel file di codice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Passaggio 3: firma digitale

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

## Passaggio 4: verifica della firma

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
                         // Fare qualcosa
                     }
                 }
             }
         }
     }
}
```

Questo codice verifica la prima firma del file PDF ed esegue azioni aggiuntive se la firma è certificata e dispone di autorizzazioni specifiche.

### Codice sorgente di esempio per la firma digitale utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Utilizza oggetti PKCS7/PKCS7Detached
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
			if (sigNames.Count > 0) // Qualche firma?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifica il primo
				{
					if (signature.IsCertified) // Certificato?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Ottieni il permesso di accesso
						{
							// Fare qualcosa
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

R: Questo tutorial ti guida attraverso il processo di firma digitale di un file PDF utilizzando Aspose.PDF per .NET. Le firme digitali aggiungono un'impronta digitale per garantire l'autenticità e l'integrità del documento.

#### D: Quali prerequisiti sono richiesti prima di iniziare?

R: Prima di iniziare, assicurati di avere una conoscenza di base del linguaggio di programmazione C#, di avere installato Visual Studio e di avere installata la libreria Aspose.PDF per .NET.

#### D: Come configuro l'ambiente di sviluppo?

R: seguire i passaggi forniti per configurare l'ambiente di sviluppo, inclusa la creazione di un nuovo progetto C# in Visual Studio e l'importazione degli spazi dei nomi richiesti.

#### D: Come posso aggiungere una firma digitale a un file PDF?

 R: Il codice di esempio fornito dimostra come caricare un file PDF, creare una firma digitale, specificare l'aspetto e salvare il file PDF firmato. La firma digitale viene aggiunta utilizzando il file`Certify` metodo del`PdfFileSignature` oggetto.

#### D: Come posso verificare la validità di una firma digitale?

R: Dopo aver aggiunto la firma digitale, puoi utilizzare il codice di esempio per verificare la validità della firma. Controlla se la firma è certificata e dispone di permessi di accesso specifici.

####  D: Cosa significa`PKCS7` object represent?

 R: Il`PKCS7` L'oggetto viene utilizzato per fornire la funzionalità crittografica per le firme digitali. Viene utilizzato per creare la firma digitale nel codice di esempio fornito.

#### D: Posso personalizzare l'aspetto della firma digitale?

 R: Sì, puoi personalizzare l'aspetto della firma digitale specificando il percorso di un'immagine nel file`SignatureAppearance` proprietà del`PdfFileSignature` oggetto.

#### D: Cosa succede se la firma non è valida?

R: Se la firma non è valida, il processo di verifica fallirà e le azioni corrispondenti all'interno del blocco di codice di verifica non verranno eseguite.

#### D: Come posso garantire la sicurezza delle mie firme digitali?

R: Le firme digitali sono sicure fin dalla progettazione e utilizzano tecniche crittografiche per garantire autenticità e integrità. Assicurati di mantenere la tua chiave privata sicura e di seguire le migliori pratiche per la gestione delle firme digitali.

#### D: Posso aggiungere più firme digitali a un PDF?

 R: Sì, puoi aggiungere più firme digitali a un file PDF utilizzando il file`PdfFileSignature` dell'oggetto`Sign` O`Certify` metodi. Ogni firma avrà il proprio aspetto e configurazione.