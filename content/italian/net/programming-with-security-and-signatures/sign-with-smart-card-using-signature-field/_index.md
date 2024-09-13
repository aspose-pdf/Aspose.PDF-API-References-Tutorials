---
title: Firma con la smart card utilizzando il campo firma
linktitle: Firma con la smart card utilizzando il campo firma
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come firmare in modo sicuro i PDF utilizzando una smart card con Aspose.PDF per .NET. Segui la nostra guida passo passo per una facile implementazione.
type: docs
weight: 120
url: /it/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Introduzione

Nel mondo digitale odierno, proteggere i documenti è più importante che mai. Che tu sia uno sviluppatore, un imprenditore o semplicemente qualcuno che gestisce informazioni sensibili, sapere come firmare i PDF elettronicamente può farti risparmiare tempo e garantire che i tuoi documenti siano autenticati. In questa guida, ti guideremo attraverso il processo di firma di un PDF utilizzando una smart card e un campo firma con Aspose.PDF per .NET. 

## Prerequisiti

Prima di addentrarci nei dettagli del processo di firma, assicuriamoci che tu abbia tutto ciò che ti serve per iniziare. Ecco una checklist dei prerequisiti:

1. Aspose.PDF per .NET: assicurati di avere la libreria Aspose.PDF installata nel tuo ambiente .NET. Puoi scaricarla da[sito](https://releases.aspose.com/pdf/net/).

2. Visual Studio: avrai bisogno di un IDE per scrivere ed eseguire il tuo codice .NET. Visual Studio Community Edition è un'ottima opzione gratuita.

3. Una Smart Card: è essenziale per firmare il tuo PDF. Assicurati di avere un lettore di smart card e i certificati necessari installati sul tuo computer.

4. Conoscenza di base del linguaggio C#: la familiarità con la programmazione C# ti aiuterà a comprendere i frammenti di codice che utilizzeremo.

5. Esempio di documento PDF: tieni pronto un esempio di documento PDF per il test. Puoi creare un PDF vuoto o usarne uno esistente.

## Importa pacchetti

Prima di iniziare a scrivere codice, importiamo i pacchetti necessari. Dovrai includere i seguenti namespace nel tuo file C#:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Questi namespace ti daranno accesso alle classi e ai metodi necessari per lavorare con i PDF e gestire le firme digitali.

## Guida passo passo per firmare un PDF con una smart card

Ora che abbiamo sistemato i nostri prerequisiti, scomponiamo il processo di firma in passaggi gestibili. Analizzeremo ogni passaggio in dettaglio, assicurandoci che tu capisca cosa sta succedendo sotto il cofano.

### Passaggio 1: imposta la directory dei documenti

Cosa fare: definire il percorso della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Spiegazione: Sostituisci`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo in cui si trovano i tuoi file PDF. Qui leggeremo il PDF vuoto e salveremo il documento firmato.

### Passaggio 2: Copia il PDF vuoto

Cosa fare: crea una copia del tuo PDF vuoto con cui lavorare.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Spiegazione: Questa riga copia il`blank.pdf`file in un nuovo file denominato`externalSignature1.pdf` . IL`true` il parametro consente la sovrascrittura se il file esiste già.

### Passaggio 3: aprire il documento PDF

Cosa fare: aprire il PDF copiato per leggerlo e scriverlo.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Ulteriori passaggi andranno qui
    }
}
```

 Spiegazione: Utilizziamo un`FileStream` per aprire il nostro file PDF. Il`Document` La classe di Aspose.PDF ci consente di manipolare il contenuto del PDF.

### Passaggio 4: creare un campo firma

Cosa fare: definire un campo firma nel PDF in cui verrà inserita la firma.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Spiegazione: Qui creiamo un`SignatureField` nella seconda pagina (l'indice delle pagine inizia da 1) del PDF. Il`Rectangle` definisce la posizione e la dimensione del campo firma.

### Passaggio 5: accedere all'archivio certificati della smart card

Cosa fare: aprire l'archivio certificati per selezionare il certificato della smart card.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Spiegazione: accediamo all'archivio certificati per l'utente corrente. È qui che sono archiviati i certificati della tua smart card.

### Passaggio 6: selezionare il certificato

Cosa fare: chiedere all'utente di selezionare un certificato dall'archivio.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Spiegazione: Questa riga apre una finestra di dialogo per selezionare un certificato. Puoi scegliere il certificato associato alla tua smart card.

### Passaggio 7: creare una firma esterna

 Cosa fare: creare un'istanza di`ExternalSignature` utilizzando il certificato selezionato.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Spiegazione: Inizializziamo il`ExternalSignature` con il certificato selezionato. Puoi anche impostare l'autorità, il motivo della firma e le informazioni di contatto.

### Passaggio 8: aggiungere il campo firma al documento

Cosa fare: aggiungere il campo firma al documento.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Spiegazione: Diamo un nome al campo firma e lo aggiungiamo alla prima pagina del documento. Questo prepara il PDF per la firma.

### Fase 9: Firmare il documento

Cosa fare: utilizzare la firma esterna per firmare il PDF.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Spiegazione: Questa riga firma il documento utilizzando la firma esterna e salva le modifiche nel PDF. Il tuo documento è ora firmato!

### Passaggio 10: verifica la firma

Cosa fare: verificare che la firma sia valida.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Spiegazione: Creiamo un'istanza di`PdfFileSignature` per verificare le firme nel documento. Se la firma non è valida, viene generata un'eccezione.

## Conclusione

Congratulazioni! Hai appena imparato a firmare un documento PDF utilizzando una smart card e un campo firma con Aspose.PDF per .NET. Questo processo non solo protegge i tuoi documenti, ma ne garantisce anche l'autenticità, rendendolo un'abilità essenziale nel panorama digitale odierno. Che tu stia firmando contratti, fatture o altri documenti importanti, sapere come implementare le firme digitali può farti risparmiare tempo e darti tranquillità.

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire documenti PDF nelle applicazioni .NET.

### Ho bisogno di una smart card per firmare i PDF?
Sì, per firmare i PDF in modo sicuro con un certificato digitale è necessaria una smart card.

### Posso usare Aspose.PDF gratuitamente?
 Aspose.PDF offre una prova gratuita, che puoi scaricare[Qui](https://releases.aspose.com/).

### Come posso verificare un PDF firmato?
 Puoi usare il`PdfFileSignature` classe in Aspose.PDF per verificare le firme nel documento PDF.

### Dove posso trovare ulteriore documentazione su Aspose.PDF?
 Puoi controllare il[Documentazione Aspose.PDF](https://reference.aspose.com/pdf/net/) per maggiori dettagli ed esempi.