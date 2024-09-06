---
title: Imposta collegamento di destinazione nel file PDF
linktitle: Imposta collegamento di destinazione nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare un collegamento di destinazione in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-links-and-actions/set-target-link/
---
Scopri come impostare un collegamento di destinazione in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Fase 1: Impostazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Passaggio 3: modifica del collegamento di destinazione

Ottieni l'annotazione del collegamento da modificare utilizzando il seguente codice:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Puoi regolare il`[1]` indici per selezionare una pagina o un'annotazione specifica.

Quindi, aggiorna la destinazione senza aggiornare il file:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

E se vuoi anche aggiornare il file:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Passaggio 4: salvare il documento con il collegamento aggiornato

 Salvare il documento con il collegamento aggiornato utilizzando il`Save` metodo:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Fase 5: Visualizzazione del risultato

Visualizza un messaggio che indica che il collegamento di destinazione è stato configurato correttamente e specifica il percorso del file salvato:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Esempio di codice sorgente per Set Target Link utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Aggiorna la destinazione della riga successiva, non aggiornare il file
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

Congratulazioni! Ora sai come impostare un collegamento di destinazione in un file PDF usando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare i collegamenti nei tuoi documenti PDF e creare esperienze interattive per gli utenti.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti e approfondire le funzionalità offerte da Aspose.PDF per .NET.

### Domande frequenti per impostare il collegamento di destinazione nel file PDF

#### D: Cos'è un collegamento di destinazione in un file PDF?

R: Un collegamento di destinazione in un file PDF è un collegamento cliccabile che indirizza il lettore a una destinazione specifica all'interno dello stesso documento o a un altro file PDF.

#### D: Perché dovrei voler impostare un collegamento di destinazione in un file PDF?

R: L'impostazione di collegamenti di destinazione consente di creare un'esperienza di navigazione fluida all'interno di un documento PDF o di creare collegamenti a sezioni o pagine specifiche all'interno di altri file PDF.

#### D: In che modo Aspose.PDF per .NET aiuta a impostare i collegamenti di destinazione?

A: Aspose.PDF per .NET fornisce API per manipolare vari aspetti dei file PDF, tra cui la creazione e la modifica di link. Questo tutorial mostra come impostare un link di destinazione usando il codice C#.

#### D: Posso impostare collegamenti di destinazione per navigare verso pagine specifiche all'interno dello stesso documento?

R: Sì, Aspose.PDF per .NET consente di impostare collegamenti di destinazione per navigare verso pagine specifiche all'interno dello stesso documento.

#### D: Posso impostare collegamenti di destinazione per navigare verso pagine specifiche in un altro file PDF?

R: Sì, puoi impostare collegamenti di destinazione per navigare verso pagine specifiche all'interno di un altro file PDF utilizzando Aspose.PDF per .NET.

#### D: Ci sono delle limitazioni nell'impostazione dei link di destinazione?

R: I link di destinazione possono navigare solo all'interno dello stesso documento o verso pagine specifiche all'interno di altri file PDF. Non possono collegarsi direttamente a contenuti specifici all'interno di altri documenti.

#### D: Come posso personalizzare l'aspetto di un collegamento di destinazione?

R: L'aspetto di un collegamento di destinazione, ad esempio il colore e lo stile, può essere personalizzato utilizzando le proprietà fornite da Aspose.PDF per .NET.

#### D: Posso impostare più collegamenti di destinazione nello stesso documento PDF?

R: Sì, puoi impostare più link di destinazione nello stesso documento PDF. Ripeti semplicemente il processo per ogni link che vuoi creare.

#### D: Posso impostare un collegamento di destinazione utilizzando una forma o un testo specifico?

R: Sì, è possibile allegare un collegamento di destinazione a forme o testo specifici all'interno del documento PDF utilizzando le proprietà e i metodi appropriati forniti da Aspose.PDF per .NET.

#### D: Come posso verificare se il collegamento di destinazione funziona come previsto?

R: Dopo aver impostato il collegamento di destinazione utilizzando il codice fornito, apri il PDF modificato e clicca sul collegamento per assicurarti che indirizzi alla destinazione desiderata.

#### D: Posso impostare collegamenti di destinazione nei PDF protetti da password?

R: Sì, puoi impostare collegamenti di destinazione nei PDF protetti da password, a condizione di fornire le credenziali appropriate per accedere e modificare il documento.