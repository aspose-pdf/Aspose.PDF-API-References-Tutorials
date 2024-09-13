---
title: Estrai informazioni sulla firma
linktitle: Estrai informazioni sulla firma
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre firme digitali e informazioni sui certificati da documenti PDF usando Aspose.PDF per .NET. Una guida completa passo dopo passo per sviluppatori C#.
type: docs
weight: 80
url: /it/net/programming-with-security-and-signatures/extract-signature-info/
---
## Introduzione

Nel mondo digitale odierno, garantire la sicurezza e l'integrità dei documenti è fondamentale. Uno dei metodi più comuni utilizzati per proteggere i PDF è l'aggiunta di una firma digitale. Tuttavia, recuperare e verificare i dettagli della firma può a volte essere una sfida, soprattutto quando si ha a che fare con vari certificati. In questa guida, ti guideremo attraverso il processo di estrazione delle informazioni sulla firma dai documenti PDF utilizzando Aspose.PDF per .NET, rendendo l'attività un gioco da ragazzi. Imparerai come accedere ai campi della firma, estrarre le informazioni del certificato e salvarle in un file.

## Prerequisiti

Prima di iniziare, assicuriamoci che tutto sia pronto per iniziare.

-  Aspose.PDF per la libreria .NET: se non lo hai ancora, puoi scaricarlo da[Pagina di download di Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/). 
- Ambiente di sviluppo .NET: avrai bisogno di un IDE come Visual Studio.
- Conoscenza di base del linguaggio C#: la familiarità con il linguaggio C# è utile per comprendere i frammenti di codice presenti in questo tutorial.
- Documento PDF con firma digitale: a scopo di test, assicurati di disporre di un file PDF che contenga almeno una firma digitale.

## Importazione degli spazi dei nomi richiesti

Prima di passare al codice, è importante importare i namespace necessari. Questi namespace ti consentiranno di accedere alla funzionalità Aspose.PDF e di lavorare con i documenti PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Ora che hai impostato gli elementi essenziali, passiamo al processo effettivo di estrazione delle informazioni sulla firma da un PDF.

## Passaggio 1: impostazione della directory dei documenti

 Prima di lavorare su un documento PDF, devi specificare la posizione del file che utilizzerai. Puoi sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui sono archiviati i PDF.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Qui specifichiamo la directory contenente il file PDF e il nome del file stesso. Assicuratevi che il file esista in quella directory!

## Passaggio 2: caricamento del documento PDF

 Ora che hai impostato la tua directory, il passo successivo è caricare il documento PDF utilizzando`Document` classe da Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Elabora il PDF qui.
}
```

 Questa riga di codice inizializza un`Document`oggetto che rappresenta il file PDF. L'`using` L'istruzione garantisce che le risorse vengano ripulite dopo l'elaborazione del documento.

## Passaggio 3: accesso ai campi del modulo

In questo passaggio, faremo un ciclo attraverso tutti i campi modulo nel documento PDF. Poiché le firme sono solitamente archiviate come campi modulo, questo passaggio ci aiuterà a identificare i campi firma.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identificare qui i campi della firma.
}
```

 Iterando attraverso il`Form` proprietà del`Document` oggetto, possiamo esaminare ogni campo del modulo per verificare se si tratta di un campo firma.

## Passaggio 4: identificazione dei campi della firma

 Una volta effettuato l'accesso ai campi del modulo, il passo successivo è identificare quali sono i campi della firma. Possiamo farlo eseguendo il cast di ogni campo in un`SignatureField` oggetto.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Estrarre le informazioni sulla firma.
}
```

 Qui utilizziamo il`as` parola chiave per tentare di convertire ogni campo del modulo in un`SignatureField`Se il cast ha successo, sappiamo che il campo è una firma.

## Passaggio 5: estrazione del certificato

Ora che hai identificato il campo firma, il compito successivo è estrarre il certificato dalla firma. I certificati contengono informazioni cruciali sul firmatario e sulla validità della firma.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 IL`ExtractCertificate` il metodo restituisce un`Stream` oggetto contenente i dati del certificato. Questo flusso può essere utilizzato per salvare il certificato per ulteriori analisi o archiviazione.

## Passaggio 6: salvataggio del certificato in un file

 Una volta estratto il certificato, il passaggio finale è salvarlo in un file. In questo caso, salveremo il certificato come`.cer` file.

```csharp
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

In questo blocco di codice:

1. Controllare che il flusso del certificato non sia nullo.
2. Leggere i dati del certificato in un array di byte.
3.  Scrivere l'array di byte in un`.cer` file nella directory dei documenti.

## Conclusione

Estrarre firme digitali e le relative informazioni sui certificati da documenti PDF utilizzando Aspose.PDF per .NET è piuttosto semplice se suddiviso in semplici passaggi. Che tu stia verificando documenti, verificando firme o semplicemente archiviando certificati per sicurezza, questo tutorial ti fornisce le conoscenze per farlo in modo efficiente. Ricorda, proteggere e verificare i documenti è fondamentale nel mondo digitale odierno e utilizzare strumenti come Aspose.PDF per .NET semplifica notevolmente la gestione.

## Domande frequenti

### Posso estrarre più firme da un PDF utilizzando Aspose.PDF per .NET?
Sì, il codice esegue un ciclo su tutti i campi del modulo nel documento, consentendo di estrarre più firme, se presenti.

### Cosa succede se non viene trovata alcuna firma nel PDF?
Se non sono presenti campi firma, il codice li ignorerà semplicemente senza generare errori.

### Posso usare questo approccio per verificare la validità di una firma?
Sebbene sia possibile estrarre il certificato, la verifica della validità di una firma richiede passaggi aggiuntivi, come il controllo della catena di attendibilità del certificato.

### È possibile estrarre altri dati dai campi del modulo utilizzando Aspose.PDF per .NET?
Sì, Aspose.PDF consente di accedere e manipolare vari tipi di campi modulo in un PDF, non solo i campi firma.

### Come posso visualizzare i dettagli del certificato estratto?
 Una volta che il certificato è stato salvato come`.cer` file, è possibile aprirlo utilizzando qualsiasi visualizzatore di certificati oppure importarlo in un archivio certificati di sistema per un'ulteriore analisi.