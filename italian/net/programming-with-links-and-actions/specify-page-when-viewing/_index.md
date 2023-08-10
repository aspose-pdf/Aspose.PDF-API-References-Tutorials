---
title: Specifica pagina durante la visualizzazione
linktitle: Specifica pagina durante la visualizzazione
second_title: Aspose.PDF per riferimento API .NET
description: Ulteriori informazioni su come specificare una pagina durante la visualizzazione di un PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Scopri come specificare una pagina durante la visualizzazione di un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Passaggio 1: configurazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Passaggio 3: specificare la pagina di destinazione

Ottieni l'istanza della pagina di destinazione utilizzando il seguente codice:

```csharp
Page page2 = doc.Pages[2];
```

 È possibile regolare l'indice`[2]` per selezionare la pagina desiderata.

## Passaggio 4: configurazione dell'impostazione dello zoom

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

## Passaggio 6: impostazione della destinazione

Imposta la destinazione per andare alla pagina di destinazione utilizzando le coordinate e lo zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Passaggio 7: configurazione dell'azione di apertura del documento

Imposta l'azione di apertura del documento con l'azione di navigazione creata:

```csharp
doc. OpenAction = action;
```

## Passaggio 8: salvare il documento aggiornato

 Salvare il documento aggiornato utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Esempio di codice sorgente per Specifica pagina durante la visualizzazione utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Ottieni l'istanza della seconda pagina del documento
Page page2 = doc.Pages[2];
// Crea la variabile per impostare il fattore di zoom della pagina di destinazione
double zoom = 1;
// Crea un'istanza GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Vai alla pagina 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Impostare l'azione di apertura del documento
doc.OpenAction = action;
// Salva documento aggiornato
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusione

Congratulazioni! Ora sai come specificare una pagina durante la visualizzazione di un PDF utilizzando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare l'esperienza di visualizzazione dell'utente nei tuoi documenti PDF.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti ed esplorare ulteriormente le funzionalità offerte da Aspose.PDF per .NET.

### FAQ 

#### D: Qual è lo scopo di specificare una pagina di destinazione durante la visualizzazione di un file PDF?

R: Specificare una pagina di destinazione consente di controllare quale pagina di un documento PDF viene visualizzata all'apertura del file. Ciò può migliorare l'esperienza dell'utente indirizzandolo a una pagina di interesse specifica.

#### D: In che modo può essere utile specificare una pagina di destinazione nei documenti PDF?

R: Specificare una pagina di destinazione è vantaggioso quando si desidera guidare gli utenti a una particolare sezione o contenuto all'interno di un documento PDF senza richiedere loro di navigare manualmente tra le pagine.

#### D: In che modo Aspose.PDF per .NET facilita la specifica di una pagina di destinazione per la visualizzazione?

R: Aspose.PDF per .NET fornisce API che consentono di impostare la visualizzazione iniziale di un documento PDF, inclusa la pagina di destinazione, il livello di zoom e altre proprietà di visualizzazione.

#### D: Posso specificare qualsiasi pagina come pagina di destinazione?

R: Sì, puoi specificare qualsiasi pagina all'interno del documento PDF come pagina di destinazione per la visualizzazione. Basta utilizzare l'indice appropriato per selezionare la pagina desiderata.

#### D: Qual è il significato del fattore di zoom quando si specifica una pagina di destinazione?

R: Il fattore di zoom determina il livello di ingrandimento applicato alla pagina di destinazione quando viene aperto il documento PDF. Controlla la quantità di contenuto visualizzato all'interno del viewport.

#### D: Posso impostare diversi fattori di zoom per diverse pagine di destinazione?

R: Sì, puoi impostare diversi fattori di zoom per diverse pagine di destinazione creando pagine separate`GoToAction` istanze e configurando le loro destinazioni di conseguenza.

#### D: Esistono limitazioni alla specifica di una pagina di destinazione?

R: La specifica di una pagina di destinazione è limitata al controllo della visualizzazione iniziale all'apertura del PDF. Non influisce sulle interazioni dell'utente o sulla navigazione una volta visualizzato il PDF.

#### D: Posso utilizzare questa funzione per creare presentazioni all'interno di un documento PDF?

R: Sì, puoi utilizzare questa funzione per creare esperienze simili a presentazioni all'interno di un documento PDF, guidando gli utenti attraverso diverse sezioni o argomenti.

#### D: Posso personalizzare altri aspetti della vista iniziale, come il layout della pagina?

R: Sì, Aspose.PDF per .NET fornisce proprietà per personalizzare altri aspetti della visualizzazione iniziale, inclusi layout di pagina, modalità di pagina e altro.

#### D: Come posso verificare se la pagina di destinazione specificata e il fattore di zoom funzionano come previsto?

R: Dopo aver applicato il codice fornito per specificare la pagina di destinazione e il fattore di zoom, aprire il file PDF modificato e verificare che si apra con la pagina e il livello di zoom corretti.