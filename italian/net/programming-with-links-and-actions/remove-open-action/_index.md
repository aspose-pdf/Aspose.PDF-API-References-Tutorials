---
title: Rimuovi azione aperta
linktitle: Rimuovi azione aperta
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come rimuovere l'azione aperta da un PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-links-and-actions/remove-open-action/
---

Scopri come rimuovere l'azione aperta da un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Passaggio 1: configurazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Apri il documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Passaggio 3: eliminazione dell'azione aperta

 Rimuovere l'azione aperta dal documento impostando il file`OpenAction` proprietà a null:

```csharp
document. OpenAction = null;
```

## Passaggio 4: salvare il documento aggiornato

 Salvare il documento aggiornato utilizzando il file`Save` metodo:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Passaggio 5: visualizzazione del risultato

Visualizza un messaggio che indica che l'azione aperta è stata rimossa con successo e specifica la posizione del file salvato:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Esempio di codice sorgente per Rimuovi azione aperta utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Rimuovi l'azione di apertura del documento
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Salva documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusione

Congratulazioni! Ora sai come rimuovere l'azione aperta da un PDF utilizzando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare le proprietà e il comportamento dei file PDF nei tuoi progetti.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti ed esplorare ulteriormente le funzionalità offerte da Aspose.PDF per .NET.