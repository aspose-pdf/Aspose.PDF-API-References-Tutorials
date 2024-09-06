---
title: Specificare la pagina durante la visualizzazione
linktitle: Specificare la pagina durante la visualizzazione
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come specificare una pagina quando visualizzi un PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Scopri come specificare una pagina quando visualizzi un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Fase 1: Impostazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Passaggio 3: Specifica della pagina di destinazione

Ottieni l'istanza della pagina di destinazione utilizzando il seguente codice:

```csharp
Page page2 = doc.Pages[2];
```

 Puoi regolare l'indice`[2]` per selezionare la pagina desiderata.

## Passaggio 4: configurazione delle impostazioni dello zoom

Crea una variabile per impostare il fattore di zoom della pagina di destinazione:

```csharp
double zoom = 1;
```

È possibile regolare il valore dello zoom in base alle proprie esigenze.

## Passaggio 5: creare l'azione di navigazione

Crea un'istanza dell'azione di navigazione utilizzando la pagina di destinazione specificata:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Fase 6: Impostazione della destinazione

Imposta la destinazione per andare alla pagina di destinazione utilizzando le coordinate e lo zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Passaggio 7: Configurazione dell'azione di apertura del documento

Imposta l'azione di apertura del documento con l'azione di navigazione creata:

```csharp
doc. OpenAction = action;
```

## Passaggio 8: salvare il documento aggiornato

 Salvare il documento aggiornato utilizzando il`Save` metodo:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Esempio di codice sorgente per Specifica pagina durante la visualizzazione utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Ottieni l'istanza della seconda pagina del documento
Page page2 = doc.Pages[2];
// Crea la variabile per impostare il fattore di zoom della pagina di destinazione
double zoom = 1;
// Crea istanza GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Vai alla pagina 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Imposta l'azione di apertura del documento
doc.OpenAction = action;
// Salva il documento aggiornato
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusione

Congratulazioni! Ora sai come specificare una pagina quando visualizzi un PDF usando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare l'esperienza di visualizzazione dell'utente nei tuoi documenti PDF.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti e approfondire le funzionalità offerte da Aspose.PDF per .NET.

### Domande frequenti 

#### D: Qual è lo scopo di specificare una pagina di destinazione quando si visualizza un file PDF?

A: Specificare una pagina di destinazione consente di controllare quale pagina di un documento PDF viene visualizzata quando il file viene aperto. Ciò può migliorare l'esperienza utente indirizzandolo a una pagina specifica di interesse.

#### D: In che modo può essere utile specificare una pagina di destinazione nei documenti PDF?

R: Specificare una pagina di destinazione è utile quando si desidera indirizzare gli utenti verso una sezione o un contenuto specifico all'interno di un documento PDF senza richiedere loro di navigare manualmente tra le pagine.

#### D: In che modo Aspose.PDF per .NET semplifica la specificazione di una pagina di destinazione per la visualizzazione?

R: Aspose.PDF per .NET fornisce API che consentono di impostare la visualizzazione iniziale di un documento PDF, tra cui la pagina di destinazione, il livello di zoom e altre proprietà di visualizzazione.

#### D: Posso specificare qualsiasi pagina come pagina di destinazione?

R: Sì, puoi specificare qualsiasi pagina all'interno del documento PDF come pagina di destinazione per la visualizzazione. Usa semplicemente l'indice appropriato per selezionare la pagina desiderata.

#### D: Qual è l'importanza del fattore di zoom quando si specifica una pagina di destinazione?

A: Il fattore di zoom determina il livello di ingrandimento applicato alla pagina di destinazione quando il documento PDF viene aperto. Controlla la quantità di contenuto visualizzata all'interno della finestra di visualizzazione.

#### D: Posso impostare diversi fattori di zoom per diverse pagine di destinazione?

A: Sì, puoi impostare diversi fattori di zoom per diverse pagine di destinazione creando pagine separate`GoToAction` istanze e configurandone di conseguenza le destinazioni.

#### D: Ci sono delle limitazioni quando si specifica una pagina di destinazione?

R: Specificare una pagina di destinazione è limitato al controllo della visualizzazione iniziale quando il PDF viene aperto. Non influisce sulle interazioni dell'utente o sulla navigazione una volta visualizzato il PDF.

#### D: Posso usare questa funzionalità per creare presentazioni all'interno di un documento PDF?

R: Sì, puoi utilizzare questa funzionalità per creare esperienze simili a presentazioni all'interno di un documento PDF, guidando gli utenti attraverso diverse sezioni o argomenti.

#### D: Posso personalizzare altri aspetti della vista iniziale, come il layout della pagina?

R: Sì, Aspose.PDF per .NET fornisce proprietà per personalizzare altri aspetti della visualizzazione iniziale, tra cui il layout di pagina, la modalità di pagina e altro ancora.

#### D: Come posso verificare se la pagina di destinazione e il fattore di zoom specificati funzionano come previsto?

R: Dopo aver applicato il codice fornito per specificare la pagina di destinazione e il fattore di zoom, aprire il file PDF modificato e verificare che si apra con la pagina e il livello di zoom corretti.