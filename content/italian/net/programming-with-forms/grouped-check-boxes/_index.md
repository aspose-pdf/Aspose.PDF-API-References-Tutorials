---
title: Caselle di controllo raggruppate nel documento PDF
linktitle: Caselle di controllo raggruppate nel documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare caselle di controllo raggruppate (pulsanti di scelta) in un documento PDF utilizzando Aspose.PDF per .NET con questo tutorial passo dopo passo.
type: docs
weight: 170
url: /it/net/programming-with-forms/grouped-check-boxes/
---
## Introduzione

Creare PDF interattivi non è così difficile come potrebbe sembrare, soprattutto quando hai a disposizione strumenti potenti come Aspose.PDF per .NET. Uno degli elementi interattivi che potresti dover aggiungere ai tuoi documenti PDF sono le caselle di controllo raggruppate o, più specificamente, i pulsanti di scelta che consentono agli utenti di selezionare un'opzione da un set. Questo tutorial ti guiderà attraverso il processo di aggiunta di caselle di controllo raggruppate (pulsanti di scelta) a un documento PDF utilizzando Aspose.PDF per .NET. Che tu sia un principiante o uno sviluppatore esperto, troverai questa guida coinvolgente, dettagliata e facile da seguire.

## Prerequisiti

Prima di addentrarci nella guida dettagliata, vediamo alcuni prerequisiti essenziali:

1.  Aspose.PDF per .NET: assicurati di avere installata la libreria Aspose.PDF. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).
2. IDE: dovresti avere un ambiente di sviluppo configurato, come Visual Studio.
3. .NET Framework: il progetto dovrebbe avere come obiettivo una versione di .NET Framework compatibile con Aspose.PDF.
4. Conoscenza di base del linguaggio C#: per seguire il tutorial senza problemi è richiesta familiarità con il linguaggio C# e con la manipolazione dei PDF.
5.  Licenza: Aspose.PDF richiede una licenza per la piena funzionalità. Puoi[ottenere una licenza temporanea](https://purchase.aspose.com/temporary-license/) se necessario.

## Importa pacchetti

Prima di iniziare, assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Questi pacchetti ti daranno accesso a tutte le classi e ai metodi necessari per manipolare i documenti PDF, inclusa la creazione di pulsanti di scelta e la definizione delle loro proprietà.

In questa sezione, suddivideremo il processo di creazione di caselle di controllo raggruppate (pulsanti di scelta) in passaggi chiari e facili da seguire.

## Passaggio 1: creare un nuovo documento PDF

 Il primo passo è creare un'istanza di`Document` oggetto, che rappresenterà il tuo file PDF. Quindi, aggiungi una pagina vuota al tuo documento in cui inserirai le caselle di controllo raggruppate.

```csharp
// Crea un'istanza dell'oggetto Documento
Document pdfDocument = new Document();

// Aggiungere una pagina al file PDF
Page page = pdfDocument.Pages.Add();
```

In questo modo si creano le basi per aggiungere al PDF qualsiasi elemento, come ad esempio i pulsanti di scelta.

## Passaggio 2: inizializzare il campo del pulsante di scelta

Successivamente, dobbiamo creare un`RadioButtonField` oggetto, che conterrà le caselle di controllo raggruppate (pulsanti di scelta). Questo campo viene aggiunto alla pagina specifica in cui appariranno le caselle di controllo.

```csharp
// Crea un'istanza dell'oggetto RadioButtonField e assegnalo alla prima pagina
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Consideratelo come il contenitore che raggrupperà le singole opzioni dei pulsanti di scelta.

## Passaggio 3: aggiungere le opzioni del pulsante di scelta

 Ora, aggiungiamo le singole opzioni del pulsante di scelta al campo. In questo esempio, aggiungeremo due pulsanti di scelta e specificheremo le loro posizioni utilizzando`Rectangle` oggetto.

```csharp
// Aggiungere la prima opzione del pulsante di scelta e specificare la sua posizione utilizzando Rettangolo
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Imposta i nomi delle opzioni per l'identificazione
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Qui, il`Rectangle` L'oggetto definisce le coordinate e le dimensioni di ciascun pulsante di scelta sulla pagina.

## Passaggio 4: personalizzare lo stile dei pulsanti di scelta

 È possibile personalizzare l'aspetto dei pulsanti di scelta impostandone`Style` proprietà. Ad esempio, potresti volere caselle di controllo a forma quadrata o a forma di croce.

```csharp
// Imposta lo stile dei pulsanti di scelta
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Ciò consente di controllare l'aspetto delle caselle di controllo, rendendole più intuitive e accattivanti.

## Passaggio 5: configurare le proprietà del bordo

I bordi svolgono un ruolo fondamentale nel rendere le caselle di controllo facilmente identificabili. Qui aggiungeremo bordi solidi attorno a ogni opzione del pulsante di scelta e ne definiremo la larghezza e il colore.

```csharp
// Configura il bordo del primo pulsante di scelta
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Configura il bordo del secondo pulsante di scelta
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Questo passaggio garantisce che ogni pulsante di scelta abbia un bordo ben definito, migliorando la leggibilità del documento.

## Passaggio 6: aggiungere le opzioni del pulsante di scelta al modulo

Ora aggiungeremo i pulsanti di scelta al modulo del documento. Questo è il passaggio finale nel raggruppamento delle caselle di controllo sotto un singolo campo.

```csharp
// Aggiungere il campo pulsante di scelta all'oggetto modulo del documento
pdfDocument.Form.Add(radio);
```

L'oggetto modulo funge da contenitore per tutti gli elementi interattivi, comprese le nostre caselle di controllo raggruppate.

## Passaggio 7: Salvare il documento PDF

Infine, una volta impostato tutto, puoi salvare il documento PDF nella posizione desiderata.

```csharp
// Definire il percorso del file di output
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Salva il documento PDF
pdfDocument.Save(dataDir);

// Conferma la creazione riuscita
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Ed ecco fatto! Hai creato con successo un PDF con caselle di controllo raggruppate utilizzando Aspose.PDF per .NET.

## Conclusione

Aggiungere elementi interattivi come caselle di controllo raggruppate ai documenti PDF può sembrare complicato all'inizio, ma con Aspose.PDF per .NET diventa un gioco da ragazzi. Seguendo questa guida passo passo, hai imparato come impostare un documento PDF di base, aggiungere pulsanti di scelta raggruppati, personalizzarne l'aspetto e salvare il risultato finale. Che tu stia creando moduli, sondaggi o qualsiasi altro tipo di PDF interattivo, questa guida ti fornisce una solida base da cui iniziare.

## Domande frequenti

### Posso aggiungere più di due pulsanti di scelta a un gruppo?
 Assolutamente! Basta creare un'istanza aggiuntiva`RadioButtonOptionField` oggetti e aggiungerli al`RadioButtonField` come mostrato nel tutorial.

### Come faccio a gestire più gruppi di caselle di controllo in un documento?
Per creare più gruppi, istanziare separatamente`RadioButtonField` oggetti per ogni gruppo.

### C'è un limite al numero di caselle di controllo che posso aggiungere?
No, Aspose.PDF per .NET non impone alcun limite al numero di caselle di controllo che è possibile aggiungere a un PDF.

### Posso modificare l'aspetto delle caselle di controllo dopo averle aggiunte?
Sì, puoi modificare proprietà come stile, larghezza e colore del bordo dopo aver aggiunto le caselle di controllo.

### È possibile utilizzare le immagini come pulsanti di scelta?
 Sì, Aspose.PDF consente di utilizzare immagini personalizzate come pulsanti di scelta impostando`Appearance` proprietà di ciascuna opzione del pulsante di scelta.