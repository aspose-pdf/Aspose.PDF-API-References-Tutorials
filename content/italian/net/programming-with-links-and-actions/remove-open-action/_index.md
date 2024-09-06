---
title: Rimuovi azione aperta
linktitle: Rimuovi azione aperta
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come rimuovere l'azione di apertura da un PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-links-and-actions/remove-open-action/
---
Scopri come rimuovere l'azione di apertura da un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Fase 1: Impostazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Passaggio 3: eliminazione dell'azione aperta

 Rimuovi l'azione aperta dal documento impostando`OpenAction` proprietà a null:

```csharp
document. OpenAction = null;
```

## Passaggio 4: salvare il documento aggiornato

 Salvare il documento aggiornato utilizzando il`Save` metodo:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Fase 5: Visualizzazione del risultato

Visualizza un messaggio che indica che l'azione aperta è stata rimossa correttamente e specifica il percorso del file salvato:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Esempio di codice sorgente per Remove Open Action utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Rimuovi azione di apertura documento
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Salva il documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Ora sai come rimuovere l'azione di apertura da un PDF usando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare le proprietà e il comportamento dei file PDF nei tuoi progetti.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti e approfondire le funzionalità offerte da Aspose.PDF per .NET.

### Domande frequenti 

#### D: Cos'è l'"azione aperta" in un file PDF?

R: L'"azione di apertura" in un file PDF è un'istruzione che specifica cosa dovrebbe accadere quando il PDF viene aperto. Può includere azioni come la navigazione verso una pagina o posizione specifica all'interno del documento, l'avvio di un'applicazione esterna o la visualizzazione di una vista specifica.

#### D: Perché dovrei voler rimuovere l'azione di apertura da un file PDF?

R: La rimozione dell'azione di apertura può migliorare la sicurezza, l'esperienza utente e il controllo su come il PDF viene presentato quando viene aperto. Ad esempio, potresti voler impedire la navigazione automatica o disabilitare determinate azioni all'apertura del documento.

#### D: In che modo Aspose.PDF per .NET aiuta a rimuovere l'azione di apertura?

A: Aspose.PDF per .NET fornisce API per manipolare vari aspetti dei file PDF. Questo tutorial mostra come rimuovere l'azione open usando il codice C#.

#### D: Ci sono potenziali rischi o considerazioni da tenere in considerazione quando si rimuove l'azione aperta?

R: La rimozione dell'azione di apertura può alterare il comportamento predefinito del PDF, quindi assicurati che sia allineato con l'esperienza utente prevista. Testa attentamente il PDF modificato per confermare che la rimozione non influisca su altre funzionalità.

#### D: Posso personalizzare l'azione aperta per eseguire altre azioni?

R: Sì, Aspose.PDF per .NET consente di personalizzare l'azione di apertura impostandola su vari tipi di azioni, come la navigazione verso una pagina specifica o l'esecuzione di JavaScript.

#### D: Posso rimuovere le azioni aperte dai PDF protetti da password?
R: Sì, puoi rimuovere le azioni aperte dai PDF protetti da password, a condizione di fornire le credenziali appropriate per accedere e modificare il documento.

#### D: La rimozione dell'azione aperta è reversibile?

R: No, una volta rimossa l'azione aperta e salvato il PDF, l'azione aperta originale non può essere ripristinata dal PDF modificato.

#### D: Come posso verificare che l'azione aperta sia stata rimossa correttamente?

R: Dopo aver rimosso l'azione di apertura utilizzando il codice fornito, aprire il PDF modificato e verificare che non si verifichi alcuna azione specifica al momento dell'apertura.

#### D: Posso rimuovere azioni aperte da più file PDF contemporaneamente?

R: Sì, è possibile utilizzare lo stesso approccio per rimuovere azioni aperte da più file PDF in uno scenario di elaborazione batch.