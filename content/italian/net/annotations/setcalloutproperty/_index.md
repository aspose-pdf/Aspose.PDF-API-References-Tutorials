---
title: Imposta la proprietà di callout nel file PDF
linktitle: Imposta la proprietà di callout nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare la proprietà callout in un file PDF utilizzando Aspose.PDF per .NET in questo tutorial dettagliato e passo dopo passo.
type: docs
weight: 130
url: /it/net/annotations/setcalloutproperty/
---
## Introduzione

La creazione di documenti PDF professionali e visivamente accattivanti richiede spesso l'aggiunta di annotazioni che attirino l'attenzione su contenuti specifici. Una di queste annotazioni è il callout, che è come quei fumetti che vedi nei fumetti. Aiutano a chiarire o enfatizzare il testo all'interno del tuo PDF. Aspose.PDF per .NET rende incredibilmente facile aggiungere tali annotazioni ai tuoi documenti e in questo tutorial ti guideremo attraverso come impostare la proprietà callout in un file PDF utilizzando questa potente libreria. Che tu sia uno sviluppatore esperto o alle prime armi, alla fine di questa guida avrai una chiara comprensione di come lavorare con i callout nei file PDF.

## Prerequisiti

Prima di immergerci nel codice, vediamo gli elementi essenziali necessari per iniziare.

1.  Aspose.PDF per .NET: assicurati di avere installata la libreria Aspose.PDF per .NET. Puoi scaricarla da[Qui](https://releases.aspose.com/pdf/net/).
2. IDE: ambiente di sviluppo come Visual Studio.
3. .NET Framework: assicurati di avere .NET installato sul tuo computer.
4. Licenza temporanea: se vuoi provare tutte le funzionalità di Aspose.PDF senza limitazioni, ottieni una[licenza temporanea](https://purchase.aspose.com/temporary-license/).

## Importa pacchetti

Prima di iniziare a scrivere il codice, è necessario importare i pacchetti necessari che consentiranno di lavorare con file PDF e annotazioni.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Queste importazioni ti forniranno tutte le classi e i metodi necessari per manipolare i documenti PDF e creare annotazioni come il callout.

## Passaggio 1: inizializzare il documento PDF

Il primo passo del nostro viaggio è inizializzare un nuovo documento PDF in cui aggiungeremo la nostra annotazione callout. Pensa a questo come all'impostazione di una tela bianca in cui puoi iniziare ad aggiungere elementi.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inizializza un nuovo documento PDF
Document doc = new Document();
```
 Qui stiamo creando un nuovo`Document` oggetto che servirà come nostro file PDF. L'`dataDir` La variabile è impostata sulla directory in cui vuoi salvare il file PDF una volta terminato.

## Passaggio 2: aggiungere una nuova pagina al documento

Un documento PDF può avere più pagine e in questo passaggio aggiungeremo una nuova pagina al nostro documento. Questa pagina sarà quella in cui verrà posizionata la nostra annotazione callout.

```csharp
//Aggiungere una nuova pagina al documento
Page page = doc.Pages.Add();
```
 IL`Pages.Add()`il metodo viene utilizzato per aggiungere una nuova pagina al`doc` oggetto. La nuova pagina viene memorizzata nel`page` variabile, che utilizzeremo in seguito quando aggiungeremo l'annotazione.

## Passaggio 3: definire l'aspetto predefinito

Le annotazioni, come il callout, hanno un aspetto visivo che puoi personalizzare. In questo passaggio, definiremo come dovrebbe apparire il testo all'interno del callout.

```csharp
// Definisci l'aspetto predefinito per l'annotazione
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Creiamo un`DefaultAppearance` oggetto che definisce il colore del testo e la dimensione del carattere. Qui, il testo sarà rosso e la dimensione del carattere è impostata su 10. Questo aspetto verrà applicato all'annotazione del callout.

## Passaggio 4: creare l'annotazione di testo libero

Ora è il momento di creare l'annotazione vera e propria. L'annotazione di testo libero è ciò che ci consente di aggiungere un callout con testo e stile specifici.

```csharp
// Crea un'annotazione FreeText con un callout
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Creiamo un`FreeTextAnnotation` oggetto con coordinate specifiche, definendone la posizione sulla pagina. L'`Intent` è impostato su`FreeTextCallout` , indicando che questa è un'annotazione di callout. Il`EndingStyle` è impostato su`OpenArrow`il che significa che la riga del callout terminerà con una freccia aperta.

## Passaggio 5: definire i punti della linea di callout

Un'annotazione callout ha una linea che punta all'area di interesse. Qui, definiremo i punti che compongono questa linea.

```csharp
// Definire i punti per la linea di callout
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 IL`Callout` la proprietà è un array di`Point` oggetti, ognuno dei quali rappresenta una coordinata sulla pagina. Questi punti definiscono il percorso della linea di callout, conferendole il classico aspetto di fumetto.

## Passaggio 6: aggiungere l'annotazione alla pagina

Dopo aver creato e configurato la nostra annotazione, il passo successivo è aggiungerla alla pagina.

```csharp
// Aggiungi l'annotazione alla pagina
page.Annotations.Add(fta);
```
 IL`Annotations.Add()` metodo viene utilizzato per posizionare l'annotazione sulla pagina creata in precedenza. Questo passaggio "disegna" effettivamente il callout sulla pagina PDF.

## Passaggio 7: imposta il contenuto del testo avanzato

Le annotazioni callout possono includere testo avanzato, consentendo contenuti formattati all'interno della bolla. Aggiungiamo un po' di testo di esempio.

```csharp
// Imposta il testo avanzato per l'annotazione
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Questo è un esempio</span></p></body>";
```
 IL`RichText` la proprietà è impostata con contenuto HTML. Ciò consente una formattazione dettagliata all'interno del callout, come la specificazione di dimensione del carattere, colore e stile.

## Passaggio 8: Salvare il documento PDF

Infine, dopo aver impostato tutto, dobbiamo salvare il documento. Questo passaggio finalizza la creazione del PDF con l'annotazione callout.

```csharp
// Salva il documento
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 IL`Save()` salva il documento nella directory specificata con il nome file "SetCalloutProperty.pdf". Questo passaggio conclude il nostro processo di creazione del PDF.

## Conclusione

Ed ecco fatto! Hai appena creato un documento PDF con un'annotazione callout usando Aspose.PDF per .NET. Questa annotazione può essere incredibilmente utile per evidenziare o spiegare parti specifiche del tuo documento. Aspose.PDF offre una potente API che rende la manipolazione PDF semplice e flessibile. Che tu stia aggiungendo annotazioni, convertendo documenti o gestendo complesse attività PDF, Aspose.PDF ti copre.

## Domande frequenti

### Posso personalizzare ulteriormente l'aspetto del callout?

Assolutamente! Puoi personalizzare vari aspetti come il colore della linea, lo spessore e la famiglia e lo stile del font del testo.

### È possibile aggiungere più callout in una singola pagina?

Sì, puoi aggiungere tutti i callout che desideri ripetendo la procedura per ogni annotazione.

### Come faccio a cambiare la posizione del callout?

 Modifica semplicemente le coordinate nel`Rectangle` E`Callout` proprietà per riposizionare l'annotazione.

### Posso aggiungere altri tipi di annotazioni utilizzando Aspose.PDF?

Sì, Aspose.PDF supporta vari tipi di annotazione, tra cui evidenziazioni, timbri e allegati di file.

### Il contenuto RTF è limitato all'HTML?

 IL`RichText` La proprietà supporta un sottoinsieme di HTML, consentendo di includere testo formattato e formattazione di base.