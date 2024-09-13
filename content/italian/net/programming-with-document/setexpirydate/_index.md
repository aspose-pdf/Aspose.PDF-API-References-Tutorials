---
title: Imposta la data di scadenza nel file PDF
linktitle: Imposta la data di scadenza nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare una data di scadenza nei file PDF usando Aspose.PDF per .NET. Migliora la sicurezza dei documenti con questa guida passo passo.
type: docs
weight: 300
url: /it/net/programming-with-document/setexpirydate/
---
## Introduzione

Nell'era digitale odierna, gestire e proteggere i documenti è più cruciale che mai. Immagina di inviare un PDF che diventa automaticamente inaccessibile dopo una certa data. Sembra magia, vero? Bene, con Aspose.PDF per .NET, puoi facilmente impostare una data di scadenza per i tuoi file PDF. Questa funzionalità è particolarmente utile per i documenti sensibili che devono essere limitati dopo un certo periodo. In questo tutorial, ti guideremo passo dopo passo attraverso il processo di impostazione di una data di scadenza in un file PDF. Quindi, prendi il tuo cappello da programmatore e tuffiamoci!

## Prerequisiti

Prima di iniziare, ecco alcune cose che devi sapere:

1. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET impostato. Potrebbe essere Visual Studio o qualsiasi altro IDE che supporti .NET.
2.  Aspose.PDF per .NET: devi avere installata la libreria Aspose.PDF. Se non l'hai ancora fatto, puoi scaricarla da[Qui](https://releases.aspose.com/pdf/net/).
3. Conoscenza di base di C#: questo tutorial presuppone che tu abbia una conoscenza di base della programmazione in C#. Se sei alle prime armi con C#, non preoccuparti! Lo terremo semplice e diretto.

## Importa pacchetti

Per iniziare con Aspose.PDF, devi importare i namespace necessari nel tuo progetto C#. Ecco come puoi farlo:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Questi namespace forniscono l'accesso alle funzionalità principali necessarie per lavorare con i documenti PDF in Aspose.PDF.

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, devi specificare il percorso della tua directory dei documenti. È qui che verrà salvato il tuo PDF di output. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui vuoi salvare il tuo file PDF. È come dire al tuo programma: "Ehi, è qui che tengo i miei file!"

## Passaggio 2: creare un'istanza dell'oggetto documento

 Successivamente, è necessario creare una nuova istanza di`Document` classe. Questa è la tua tela dove creerai il tuo PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Pensa al`Document` oggetto come un foglio di carta bianco. Puoi aggiungere contenuti come preferisci!

## Passaggio 3: aggiungere una pagina al PDF

Ora che hai impostato il tuo documento, è il momento di aggiungerci una pagina. È qui che andrà il tuo contenuto.

```csharp
doc.Pages.Add();
```

Hai appena creato una nuova pagina nel tuo PDF. È come aggiungere una nuova pagina nel tuo quaderno dove puoi annotare i tuoi pensieri.

## Passaggio 4: aggiungere testo alla pagina

Rendiamo questa pagina un po' più interessante aggiungendo del testo. Aggiungeremo un semplice messaggio "Hello World".

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Questa riga di codice aggiunge un frammento di testo alla prima pagina del tuo PDF. È come scrivere un titolo in cima alla tua pagina!

## Passaggio 5: creare JavaScript per la data di scadenza

Ora arriva la parte divertente! Creerai un'azione JavaScript che controllerà la data di scadenza del PDF. Se la data corrente supera la data di scadenza, un messaggio avviserà l'utente.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Ecco cosa sta succedendo:
- Definisci l'anno e il mese di scadenza.
- Ottieni la data odierna.
- Si confronta la data odierna con la data di scadenza.
- Se la data odierna è successiva alla data di scadenza, verrà visualizzato un messaggio!

## Passaggio 6: imposta JavaScript come azione di apertura PDF

Ora, devi impostare l'azione JavaScript come azione di apertura per il tuo documento PDF. Ciò significa che JavaScript verrà eseguito non appena il PDF verrà aperto.

```csharp
doc.OpenAction = javaScript;
```

Questa riga dice al PDF di eseguire il JavaScript quando qualcuno lo apre. È come impostare un promemoria che si attiva non appena apri il tuo calendario!

## Passaggio 7: Salvare il documento PDF

Infine, è il momento di salvare il documento PDF con la funzione data di scadenza. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Questa riga salva il tuo PDF nella directory specificata con il nome "SetExpiryDate_out.pdf". È come mettere la tua opera d'arte finita in una cornice!

## Conclusione

Ed ecco fatto! Hai creato con successo un file PDF con una data di scadenza usando Aspose.PDF per .NET. Questa funzionalità non solo migliora la sicurezza, ma assicura anche che le informazioni sensibili siano tenute sotto controllo. Che tu stia inviando contratti, report o altri documenti importanti, impostare una data di scadenza può cambiare le carte in tavola.

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire documenti PDF nelle applicazioni .NET.

### Posso usare Aspose.PDF gratuitamente?
 Sì, puoi usare una versione di prova gratuita di Aspose.PDF. Puoi scaricarla[Qui](https://releases.aspose.com/).

### Come posso acquistare Aspose.PDF?
Puoi acquistare Aspose.PDF visitando il[pagina di acquisto](https://purchase.aspose.com/buy).

### Cosa succede se ho bisogno di supporto?
Se hai domande o hai bisogno di assistenza, puoi visitare il[Forum di supporto Aspose](https://forum.aspose.com/c/pdf/10).

### Posso ottenere una licenza temporanea per Aspose.PDF?
 Sì, puoi richiedere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).