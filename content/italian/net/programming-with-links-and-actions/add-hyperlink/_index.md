---
title: Aggiungi collegamento ipertestuale nel file PDF
linktitle: Aggiungi collegamento ipertestuale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere facilmente collegamenti ipertestuali ai tuoi PDF utilizzando Aspose.PDF per .NET. Aumenta l'interattività e il coinvolgimento degli utenti nei tuoi documenti.
type: docs
weight: 10
url: /it/net/programming-with-links-and-actions/add-hyperlink/
---
## Introduzione

Aggiungere collegamenti ipertestuali a un file PDF può migliorare notevolmente l'interattività e la navigabilità del documento. Che tu stia creando una fattura che si collega a un portale di pagamento o un report che indirizza i lettori a risorse online pertinenti, i collegamenti ipertestuali possono aggiungere un livello di funzionalità che rende i tuoi PDF più intuitivi. In questa guida, utilizzeremo Aspose.PDF per .NET per mostrarti come aggiungere collegamenti ipertestuali ai tuoi file PDF senza problemi. Quindi, rimboccati le maniche; imparerai tutto punto per punto e passo dopo passo!

## Prerequisiti

Prima di addentrarci nei dettagli dell'aggiunta di collegamenti ipertestuali, ci sono un paio di prerequisiti che devi spuntare dalla tua lista:

1. Installa .NET Framework: assicurati di avere un .NET Framework compatibile installato sul tuo computer. Aspose.PDF funziona con varie versioni, quindi verifica la compatibilità con la versione che stai utilizzando.
2.  Aspose.PDF per la libreria .NET: avrai bisogno della libreria Aspose.PDF. Puoi scaricarla da[pagina di download](https://releases.aspose.com/pdf/net/) se non l'hai ancora fatto.
3. Conoscenze di base del linguaggio C#: la familiarità con la programmazione C# renderà questo tutorial più fluido e comprensibile.
4. Ambiente di sviluppo: predisponi un IDE come Visual Studio per scrivere ed eseguire il codice.

Una volta soddisfatti questi prerequisiti, sei pronto per procedere!

## Importa pacchetti

Per lavorare con Aspose.PDF, devi importare i namespace rilevanti nel tuo progetto C#. Apri il tuo progetto e, in cima al tuo file C#, aggiungi le seguenti direttive using:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Fatta questa premessa, analizziamo passo dopo passo il processo di aggiunta di collegamenti ipertestuali a un PDF.

## Passaggio 1: imposta la directory dei documenti

La prima cosa che vorrai fare è impostare una directory di lavoro in cui risiederanno i tuoi file PDF. Ecco come fare:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`YOUR DOCUMENT DIRECTORY` con il percorso effettivo in cui vuoi salvare i tuoi PDF. Questo percorso ti aiuterà a navigare tra i file mentre leggiamo e scriviamo i nostri PDF.

## Passaggio 2: aprire il documento PDF esistente

 Ora, apriamo il file PDF in cui vuoi aggiungere l'hyperlink. Puoi aprire un PDF esistente utilizzando`Document` classe dalla libreria Aspose.PDF.

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

 Questo frammento legge il tuo file PDF e lo prepara per le modifiche. Assicurati`"AddHyperlink.pdf"` esiste nella directory specificata oppure modifica il nome del file di conseguenza.

## Passaggio 3: accedi alla pagina PDF

Ora, dobbiamo selezionare la pagina all'interno del documento in cui apparirà l'hyperlink. Ad esempio, se aggiungiamo il link alla prima pagina:

```csharp
Page page = document.Pages[1];
```

Ricorda che l'indice delle pagine in Aspose inizia da 1, non da 0. Quindi la prima pagina è la pagina 1.

## Passaggio 4: creare l'oggetto di annotazione del collegamento

Successivamente, devi definire l'area rettangolare in cui sarà cliccabile l'hyperlink. Puoi personalizzare quest'area in base alle tue esigenze:

```csharp
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
```

 Qui stiamo creando un rettangolo che inizia a`(100, 100)` e si estende fino a`(300, 300)`Modifica questi numeri per modificare le dimensioni e la posizione del tuo collegamento.

## Passaggio 5: Configurare il bordo del collegamento

Ora che l'area del link è impostata, dobbiamo dargli uno stile visivo. Puoi creare un bordo, anche se in questo caso lo imposteremo in modo che sia invisibile:

```csharp
Border border = new Border(link);
border.Width = 0;
link.Border = border;
```

In questo modo si crea un bordo di collegamento invisibile, che si integra perfettamente con il design del PDF.

## Passaggio 6: specificare l'azione del collegamento ipertestuale

Dovrai specificare cosa succede quando un utente clicca su questo link. Per il nostro esempio, indirizzeremo gli utenti al sito web di Aspose:

```csharp
link.Action = new GoToURIAction("http://(Italiano)
```

 Assicurati di utilizzare`"http://"` all'inizio di un indirizzo web; in caso contrario, potrebbe non funzionare correttamente.

## Passaggio 7: aggiungere l'annotazione del collegamento alla pagina

questo punto, mettiamo in pratica tutto ciò che abbiamo creato aggiungendo l'hyperlink alla raccolta di annotazioni della pagina specifica:

```csharp
page.Annotations.Add(link);
```

Con questa riga, il tuo collegamento ipertestuale è pronto e in attesa di interazione da parte dell'utente!

## Passaggio 8: creare un'annotazione di testo libero

È utile aggiungere un po' di contesto testuale al tuo collegamento ipertestuale. Questo aiuta gli utenti a capire su cosa stanno cliccando. Aggiungiamo un'annotazione FreeText:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(FontRepository.FindFont("TimesNewRoman"), 10, Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation.Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

Qui definiamo il font, la dimensione e il colore del testo. Puoi modificare queste proprietà in base alle tue esigenze di progettazione.

## Passaggio 9: Salvare il documento

Dopo aver aggiunto tutto, dall'hyperlink all'annotazione di testo, è il momento di salvare il documento in modo che tutte le modifiche vengano applicate:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document.Save(dataDir);
```

 Questo salva il tuo PDF aggiornato come un nuovo file denominato`"AddHyperlink_out.pdf"` nella directory specificata.

## Conclusione

Aggiungere collegamenti ipertestuali ai tuoi documenti PDF usando Aspose.PDF per .NET non solo aumenta la professionalità dei tuoi PDF, ma aumenta anche il coinvolgimento degli utenti. È facile da fare e porta un livello completamente nuovo di interattività che i documenti statici semplicemente non possono eguagliare. Con i passaggi descritti in questa guida, puoi aggiungere con sicurezza collegamenti ipertestuali a qualsiasi PDF che crei o modifichi. 

## Domande frequenti

### Posso modificare lo stile del collegamento ipertestuale?  
Sì, puoi modificare l'aspetto del collegamento ipertestuale e del testo utilizzando diversi tipi di carattere, colori e stili di bordo.

### Cosa succede se voglio creare un collegamento a una pagina interna?  
 Puoi usare`GoToAction` invece di`GoToURIAction` per creare collegamenti a pagine diverse all'interno del PDF.

### Aspose.PDF supporta altri formati di file?  
Sì, Aspose.PDF supporta un'ampia gamma di formati di file e funzionalità per la manipolazione e la conversione di PDF.

### Come posso ottenere una licenza temporanea per lo sviluppo?  
 È possibile ottenere una licenza temporanea visitando[questo collegamento](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare altri tutorial su Aspose.PDF?  
Puoi trovare altri tutorial in[documentazione](https://reference.aspose.com/pdf/net/).