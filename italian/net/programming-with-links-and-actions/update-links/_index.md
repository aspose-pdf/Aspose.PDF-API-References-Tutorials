---
title: Aggiorna collegamenti
linktitle: Aggiorna collegamenti
second_title: Aspose.PDF per riferimento API .NET
description: Ulteriori informazioni su come aggiornare i collegamenti in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-links-and-actions/update-links/
---

Scopri come aggiornare i collegamenti in un file PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.

## Passaggio 1: configurazione dell'ambiente

Assicurati di aver configurato il tuo ambiente di sviluppo con un progetto C# e i riferimenti Aspose.PDF appropriati.

## Passaggio 2: caricamento del file PDF

Imposta il percorso della directory dei tuoi documenti e carica il file PDF utilizzando il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Carica il file PDF
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Passaggio 3: modifica del collegamento

Ottenere l'annotazione del collegamento da modificare utilizzando il seguente codice:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Puoi regolare il`[1]` indici per selezionare una pagina o un'annotazione specifica.

Successivamente, modifica il collegamento cambiando la destinazione:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

Il primo parametro rappresenta l'oggetto del documento, il secondo è il numero della pagina di destinazione. Il quinto argomento è il fattore di zoom durante la visualizzazione della rispettiva pagina. Se impostato su 2, la pagina verrà visualizzata con uno zoom del 200%.

## Passaggio 4: salvare il documento con il collegamento aggiornato

Salvare il documento con il collegamento aggiornato utilizzando il file`Save` metodo:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Passaggio 5: visualizzazione del risultato

Visualizza un messaggio che indica che i collegamenti sono stati aggiornati correttamente e specifica la posizione del file salvato:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Codice sorgente di esempio per i collegamenti di aggiornamento utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica il file PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Ottieni la prima annotazione di collegamento dalla prima pagina del documento
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Link di modifica: modifica la destinazione del link
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Specificare la destinazione per l'oggetto collegamento
	// Il primo parametro è l'oggetto documento, il secondo è il numero della pagina di destinazione.
	// L'argomento 5ht è il fattore di zoom quando si visualizza la rispettiva pagina. Quando si utilizza 2, la pagina verrà visualizzata con uno zoom del 200%.
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Salva il documento con il link aggiornato
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusione

Congratulazioni! Ora sai come aggiornare i collegamenti in un file PDF utilizzando Aspose.PDF per .NET. Usa questa conoscenza per personalizzare i collegamenti nei tuoi documenti PDF e creare esperienze interattive per gli utenti.

Ora che hai completato questa guida, puoi applicare questi concetti ai tuoi progetti ed esplorare ulteriormente le funzionalità offerte da Aspose.PDF per .NET.