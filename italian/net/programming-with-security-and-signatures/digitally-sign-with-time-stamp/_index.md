---
title: Firma digitale con timestamp
linktitle: Firma digitale con timestamp
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come eseguire una firma digitale con timestamp su un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

In questo tutorial, ti guideremo attraverso il processo di firma digitale di un file PDF con timestamp utilizzando Aspose.PDF per .NET. La firma digitale con marca temporale garantisce l'autenticità e l'integrità del documento, mediante l'aggiunta di un'impronta digitale elettronica con marca temporale.

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
```

## Passaggio 3: Firma digitale con timestamp

Il primo passo è eseguire la firma digitale con timestamp sul file PDF. Il codice fornito mostra come ottenere questa firma con Aspose.PDF per .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Questo codice carica un file PDF, crea una firma digitale con timestamp utilizzando un file PFX (chiave privata) e i parametri di timestamp specificati. La firma viene quindi aggiunta al file PDF e salvata con il suffisso "_fuori".

### Codice sorgente di esempio per la firma digitale con timestamp utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Utente/Password può essere omesso
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Crea uno dei tre tipi di firma
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Salva il file PDF di output
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusione

Congratulazioni! Hai eseguito correttamente una firma digitale con timestamp su un file PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto il processo passo dopo passo dalla creazione della firma al salvataggio del file PDF aggiornato. Ora puoi utilizzare questa funzione per aggiungere firme digitali con timestamp ai tuoi file PDF.