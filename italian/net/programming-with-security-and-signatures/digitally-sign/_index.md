---
title: Firma digitale
linktitle: Firma digitale
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come firmare digitalmente un file PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-security-and-signatures/digitally-sign/
---

In questo tutorial, ti guideremo attraverso il processo di firma digitale di un file PDF utilizzando Aspose.PDF per .NET. La firma digitale garantisce l'autenticità e l'integrità del documento, mediante l'aggiunta di un'impronta elettronica univoca.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#
- Installazione di Visual Studio sul tuo computer
- Libreria Aspose.PDF per .NET installata

## Passaggio 2: configurazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Apri Visual Studio e crea un nuovo progetto C#.
2. Importa gli spazi dei nomi richiesti nel tuo file di codice:

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

Questo codice carica un file PDF, crea una firma digitale con un aspetto specifico, quindi salva il file PDF con la firma aggiunta.

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

### Esempio di codice sorgente per la firma digitale utilizzando Aspose.PDF per .NET 
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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Usa oggetti PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Imposta l'aspetto della firma
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//Crea uno dei tre tipi di firma
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

Congratulazioni! Hai eseguito con successo una firma digitale su un file PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto il processo passo dopo passo, dall'aggiunta della firma digitale alla verifica della sua validità. Ora puoi utilizzare questa funzione per proteggere i tuoi file PDF con firme digitali.