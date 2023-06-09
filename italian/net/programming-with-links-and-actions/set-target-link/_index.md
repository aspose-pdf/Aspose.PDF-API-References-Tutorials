---
title: Imposta il collegamento di destinazione
linktitle: Imposta il collegamento di destinazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare un collegamento di destinazione in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-links-and-actions/set-target-link/
---

Scopri come impostare un collegamento di destinazione in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Passaggio 1: configurazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Passaggio 3: modifica del collegamento di destinazione

Ottenere l'annotazione del collegamento da modificare utilizzando il seguente codice:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Puoi regolare il`[1]` indici per selezionare una pagina o un'annotazione specifica.

Successivamente, aggiorna la destinazione senza aggiornare il file:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

E se vuoi anche aggiornare il file:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Passaggio 4: salvare il documento con il collegamento aggiornato

Salvare il documento con il collegamento aggiornato utilizzando il file`Save` metodo:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Passaggio 5: visualizzazione del risultato

Visualizza un messaggio che indica che il collegamento di destinazione è stato configurato correttamente e specifica la posizione del file salvato:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Esempio di codice sorgente per Set Target Link utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Destinazione dell'aggiornamento della riga successiva, non aggiornare il file
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// File di aggiornamento della riga successiva
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Salva il documento con il link aggiornato
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

Congratulazioni! Ora sai come impostare un collegamento di destinazione in un file PDF utilizzando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare i collegamenti nei tuoi documenti PDF e creare esperienze interattive per gli utenti.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti ed esplorare ulteriormente le funzionalità offerte da Aspose.PDF per .NET.