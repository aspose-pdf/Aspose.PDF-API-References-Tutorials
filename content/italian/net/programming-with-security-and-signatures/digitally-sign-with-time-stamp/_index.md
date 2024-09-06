---
title: Firma digitale con marca temporale nel file PDF
linktitle: Firma digitale con marca temporale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come applicare una firma digitale con marca temporale in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
In questo tutorial, ti guideremo attraverso il processo di firma digitale in un file PDF con timestamp usando Aspose.PDF per .NET. La firma digitale con timestamp garantisce l'autenticità e l'integrità del documento, aggiungendo un'impronta digitale elettronica con timestamp.

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
```

## Fase 3: Firma digitale con marca temporale

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

Questo codice carica un file PDF, crea una firma digitale con timestamp utilizzando un file PFX (chiave privata) e i parametri timestamp specificati. La firma viene quindi aggiunta al file PDF e salvata con il suffisso "_fuori".

### Esempio di codice sorgente per firmare digitalmente con timestamp utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // È possibile omettere l'utente/password
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Crea uno qualsiasi dei tre tipi di firma
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Salva il file PDF di output
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusione

Congratulazioni! Hai eseguito con successo una firma digitale con timestamp su un file PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto il processo passo dopo passo dalla creazione della firma al salvataggio del file PDF aggiornato. Ora puoi usare questa funzionalità per aggiungere firme digitali con timestamp ai tuoi file PDF.

### Domande frequenti sulla firma digitale con marca temporale in un file PDF

#### D: Qual è lo scopo della firma digitale con marca temporale?

R: La firma digitale con marca temporale aggiunge un'impronta digitale elettronica con marca temporale a un file PDF, garantendo l'autenticità e l'integrità del documento in un momento specifico.

#### D: Quali prerequisiti sono necessari per iniziare questo tutorial?

R: Prima di iniziare, assicurati di avere una conoscenza di base del linguaggio di programmazione C#, di avere installato Visual Studio e di avere installato la libreria Aspose.PDF per .NET.

#### D: Come posso configurare il mio ambiente di sviluppo?

R: Seguire i passaggi indicati per configurare l'ambiente di sviluppo, inclusa la creazione di un nuovo progetto C# in Visual Studio e l'importazione degli spazi dei nomi necessari.

#### D: Come posso aggiungere una firma digitale con marca temporale a un PDF?

R: Il codice di esempio fornito mostra come caricare un file PDF, creare una firma digitale con marca temporale utilizzando un file PFX (chiave privata) e le impostazioni di marca temporale specificate, aggiungere la firma al file PDF e salvare il file aggiornato.

#### D: Cos'è un file PFX e perché viene utilizzato nell'esempio?

A: Un file PFX (Personal Exchange Format) contiene una chiave privata e un certificato. Viene utilizzato qui per fornire funzionalità crittografiche per le firme digitali. Assicurati di sostituire il segnaposto con il tuo file PFX e la tua password.

#### D: Cosa sono i TimestampSettings?

A: TimestampSettings definisce le impostazioni per il server timestamp utilizzato per aggiungere il timestamp elettronico alla firma. Include l'URL del server timestamp e le credenziali utente facoltative.

#### D: Posso utilizzare un server di marcatura temporale diverso da quello nell'esempio?
 A: Sì, puoi usare qualsiasi server di marca temporale compatibile. Sostituisci l'URL e, se necessario, fornisci le credenziali utente appropriate nel`TimestampSettings` oggetto.

#### D: Qual è lo scopo di specificare il rettangolo della firma?

A: Il rettangolo della firma definisce la posizione e le dimensioni dell'aspetto della firma digitale sulla pagina PDF. Regola questi valori per posizionare la firma come desideri.

#### D: Cosa succede se il server di marcatura temporale non è disponibile durante la firma?

A: Se il server di marcatura temporale non è disponibile durante la firma, il processo potrebbe non riuscire o richiedere più tempo. Assicurati che il tuo server di marcatura temporale sia affidabile e accessibile.

#### D: Come posso verificare la presenza di una marca temporale nel PDF firmato?

 A: Puoi esaminare il PDF firmato utilizzando il codice di esempio fornito.`TimestampSettings` utilizzato durante la firma dovrebbe essere disponibile nei dettagli della firma.

#### D: Le firme digitali con marca temporale sono giuridicamente vincolanti?

R: Le firme digitali con timestamp hanno valore legale in molte giurisdizioni e sono spesso considerate più affidabili delle semplici firme digitali. Consulta gli esperti legali della tua giurisdizione per le normative specifiche.

#### D: Posso aggiungere più firme digitali con marca temporale a un PDF?

R: Sì, puoi aggiungere più firme digitali con timestamp a un file PDF richiamando più volte il processo di creazione della firma. Ogni firma avrà il suo timestamp.