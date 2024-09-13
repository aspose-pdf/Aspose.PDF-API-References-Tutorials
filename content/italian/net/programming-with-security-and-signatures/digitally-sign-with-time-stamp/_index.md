---
title: Firma digitale con marca temporale nel file PDF
linktitle: Firma digitale con marca temporale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come firmare digitalmente un PDF con un timestamp usando Aspose.PDF per .NET. Questa guida passo passo copre i prerequisiti, la configurazione del certificato, il timestamping e altro ancora.
type: docs
weight: 50
url: /it/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Introduzione

Hai mai avuto bisogno di firmare digitalmente un PDF e includere una marca temporale per una maggiore sicurezza? Che tu stia lavorando su documenti legali, contratti o qualsiasi cosa che richieda un'autenticazione sicura, una firma digitale con una marca temporale aggiunge un ulteriore livello di credibilità. In questo tutorial, spiegheremo in dettaglio come puoi usare Aspose.PDF per .NET per aggiungere una firma digitale insieme a una marca temporale ai tuoi documenti PDF. Non preoccuparti, lo faremo passo dopo passo!

## Prerequisiti

Prima di immergerci nel codice, ci sono alcune cose che dovrai impostare per seguire. Ecco una rapida checklist dei prerequisiti per iniziare:

-  Libreria Aspose.PDF per .NET: avrai bisogno della libreria Aspose.PDF per .NET installata nel tuo progetto. Puoi[scarica l'ultima versione qui](https://releases.aspose.com/pdf/net/) oppure aggiungilo al tuo progetto tramite NuGet.
- Un documento PDF: avrai bisogno di un file PDF di esempio con cui lavorare. Assicurati di avere un file nella directory del tuo progetto che vuoi firmare.
-  Certificato digitale (file PFX): assicurati di avere un certificato digitale (un`.pfx` file) per firmare digitalmente il documento.
- URL di marcatura temporale: si tratta di un servizio di marcatura temporale online che verrà utilizzato per allegare una marca temporale alla firma digitale. 
- Conoscenza di base di C#: non è necessario essere un esperto, ma conoscere le basi di C# ti aiuterà a comprendere e personalizzare il codice.

Una volta spuntate tutte queste caselle, sei pronto per iniziare a programmare!

## Importa pacchetti

Per iniziare, dovrai importare i seguenti namespace nel tuo progetto C#. Questo ti assicura di avere accesso alle classi e alle funzioni Aspose.PDF pertinenti.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Passaggio 1: caricare il documento PDF

La prima cosa che dobbiamo fare è caricare il documento PDF che vogliamo firmare. Ecco come fare:

```csharp
// Definisci il percorso verso la directory dei tuoi documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Questo passaggio è piuttosto semplice. Stiamo semplicemente definendo il percorso verso il documento che vogliamo firmare. Il`Document` La classe di Aspose.PDF gestisce il caricamento del file.

## Passaggio 2: impostare la firma digitale

Successivamente, creeremo la firma digitale utilizzando la classe PKCS7 e caricheremo il file PFX. Questo file PFX contiene il tuo certificato e la tua chiave privata, necessari per firmare il documento.

```csharp
// Percorso al tuo file .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Inizializzare l'oggetto firma
PdfFileSignature signature = new PdfFileSignature(document);

// Carica il file PFX con una password
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 A questo punto, stai dicendo ad Aspose di usare il tuo certificato digitale per firmare il documento.`PKCS7`object gestisce tutto il lavoro crittografico per te, così non devi preoccuparti dei dettagli minuziosi.

## Passaggio 3: aggiungere le impostazioni del timestamp

Uno dei componenti chiave di una firma digitale robusta è il timestamp. Questo assicura che la firma del documento possa essere verificata anche dopo la scadenza del certificato. Impostiamo il timestamp utilizzando un'autorità di timestamping online.

```csharp
// Definisci le impostazioni del timestamp
TimestampSettings timestampSettings = new TimestampSettings("https://il_tuo_timestamp_url", "utente:password");

// Aggiungere impostazioni di timestamp all'oggetto PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Qui, stai specificando l'URL per il servizio di marcatura temporale, che fornirà automaticamente un orario e una data alla tua firma. Questo può essere fatto con o senza autenticazione.

## Passaggio 4: definire la posizione e l'aspetto della firma

Ora, definiremo dove apparirà la firma nel PDF e le sue dimensioni. Puoi personalizzare la posizione della casella della firma sulla pagina, così come le dimensioni.

```csharp
//Definire l'aspetto e la posizione della firma (pagina 1, con rettangolo specificato)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Qui, stiamo definendo un rettangolo che posiziona la firma alle coordinate (100, 100) sulla prima pagina del PDF, con una larghezza di 200 e un'altezza di 100. Puoi modificare questi valori per adattarli al tuo design.

## Passaggio 5: firmare il documento PDF

Una volta impostato tutto, è il momento di applicare effettivamente la firma digitale al PDF. Questo passaggio combina il certificato, la marca temporale e il posizionamento in un semplice comando.

```csharp
// Firmare il documento sulla prima pagina
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Ecco cosa sta succedendo:
- 1: Indica che la firma deve essere apposta sulla prima pagina.
- "Motivo della firma": qui puoi specificare il motivo per cui stai firmando il documento.
- "Contatto": Inserisci le informazioni di contatto del firmatario.
- "Posizione": specificare la posizione del firmatario.
- true: questo valore booleano indica se la firma è visibile nel documento.
- rect: Il rettangolo definito in precedenza specifica la dimensione e la posizione della firma.
- pkcs: l'oggetto PKCS7 contiene le impostazioni del certificato digitale e della marca temporale.

## Passaggio 6: Salva il PDF firmato

Una volta firmato il documento, non resta che salvarlo. Puoi scegliere un nuovo nome file per conservare sia la versione originale che quella firmata.

```csharp
// Salvare il documento PDF firmato
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Il tuo PDF appena firmato e con marca temporale è ora salvato nella directory specificata!

## Conclusione

Ed ecco fatto! Hai firmato digitalmente con successo un PDF con un timestamp usando Aspose.PDF per .NET. Questo processo assicura l'autenticità e l'integrità dei tuoi documenti, dando tranquillità sia a te che al destinatario. Le firme digitali stanno diventando sempre più essenziali nel mondo digitale odierno, quindi padroneggiare questo processo è sicuramente un'abilità che vale la pena avere.

## Domande frequenti

### Posso utilizzare un formato di file diverso per il certificato?  
Sì, ma il tutorial si concentra sull'utilizzo di un file PFX, che è il formato più comune per i certificati digitali.

### Ho bisogno di una connessione Internet per applicare la marca temporale?  
Sì, poiché la marca temporale viene recuperata da un'autorità di marcatura temporale online, avrai bisogno di un accesso a Internet.

### Posso firmare più pagine di un PDF?  
 Assolutamente! Puoi modificare il`signature.Sign()` Metodo per selezionare più pagine o per scorrere tutte le pagine.

### Cosa succede se la password del file PFX è errata?  
Se la password è errata, riceverai un'eccezione, quindi assicurati di averla inserita correttamente.

### Posso rendere invisibile la firma?  
 Sì, puoi passare`false` al`Sign` parametro visibility del metodo per rendere invisibile la firma.