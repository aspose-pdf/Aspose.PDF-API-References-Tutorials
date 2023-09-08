---
title: Eredita il file PDF ingrandito
linktitle: Eredita il file PDF ingrandito
second_title: Aspose.PDF per riferimento all'API .NET
description: Eredita facilmente lo zoom dei segnalibri nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 90
url: /it/net/programming-with-bookmarks/inherit-zoom/
---
L'ereditarietà dello zoom nel file PDF consente di specificare un livello di zoom predefinito per i segnalibri. Con Aspose.PDF per .NET, puoi facilmente ereditare lo zoom seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la necessaria direttiva sulle importazioni:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF da cui desideri ereditare lo zoom. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: apri il documento PDF

Adesso apriremo il documento PDF di cui vogliamo ereditare lo zoom utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: ottieni la raccolta di segnalibri

 In questo passaggio, otterremo la raccolta di segnalibri o punti di riferimento del documento utilizzando il file`Outlines` proprietà del`doc` oggetto. Ecco il codice corrispondente:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Passaggio 5: imposta il livello di zoom

 Ora imposteremo il livello di zoom creando un file`XYZExplicitDestination` oggetto con le coordinate x, y e z specificate. Qui utilizziamo le coordinate (100, 100, 0) con uno zoom di 2. Ecco il codice corrispondente:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Passaggio 6: aggiungi il livello di zoom ai segnalibri

 In questo passaggio aggiungiamo il file`XYZExplicitDestination` oggetto come azione ai segnalibri di`item` collezione. Ecco il codice corrispondente:

```csharp
item. Action = new GoToAction(dest);
```

## Passaggio 7: aggiungi i segnalibri aggiornati al documento

 Infine, aggiungiamo i segnalibri aggiornati alla raccolta di segnalibri del documento utilizzando il file`Add` metodo del`doc.Outlines` oggetto. Ecco il codice corrispondente:

```csharp
doc. Outlines. Add(item);
```

## Passaggio 8: salva il file aggiornato

 Ora salviamo il file PDF aggiornato utilizzando il file`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Codice sorgente di esempio per Inherit Zoom utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document doc = new Document(dataDir + "input.pdf");
// Ottieni una raccolta di contorni/segnalibri di file PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Imposta il livello di zoom su 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Aggiungi XYZExplicitDestination come azione per delineare la raccolta di PDF
item.Action = new GoToAction(dest);
// Aggiungi elemento alla raccolta di contorni del file PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Salva l'output
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per ereditare Zoom con Aspose.PDF per .NET. Puoi utilizzare questo codice per specificare un livello di zoom predefinito per i segnalibri nei tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di manipolazione dei segnalibri.

### Domande frequenti per ereditare lo zoom nel file PDF

#### D: Cos'è l'ereditarietà dello zoom in un file PDF?

R: L'ereditarietà dello zoom si riferisce alla possibilità di specificare un livello di zoom predefinito per i segnalibri in un documento PDF. Ciò consente una navigazione coerente e intuitiva quando gli utenti interagiscono con i segnalibri.

#### D: Perché dovrei ereditare i livelli di zoom per i segnalibri?

R: L'ereditarietà dei livelli di zoom garantisce agli utenti un'esperienza di visualizzazione coerente durante la navigazione tra i segnalibri in un documento PDF. Può essere particolarmente utile quando desideri fornire una visualizzazione specifica per diverse sezioni di un documento.

#### D: Come posso importare le librerie necessarie per il mio progetto C#?

R: Per importare le librerie richieste per il tuo progetto C#, includi le seguenti direttive di importazione:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Queste direttive consentono di accedere alle classi e ai metodi necessari per lavorare con documenti PDF e segnalibri.

#### D: Come posso specificare il percorso della cartella dei documenti?

 R: Nel codice sorgente fornito, sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella contenente il file PDF per il quale desideri ereditare i livelli di zoom.

#### D: Come faccio ad aprire un documento PDF per ereditare i livelli di zoom?

R: Per aprire un documento PDF per ereditare i livelli di zoom, utilizzare il seguente codice:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Sostituire`"input.pdf"` con il nome effettivo del file.

#### D: Come posso impostare il livello di zoom per i segnalibri?

 R: Per impostare il livello di zoom, crea un file`XYZExplicitDestination` oggetto con le coordinate e il fattore di zoom desiderati. Ecco un esempio:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Imposta il livello di zoom su 2 alle coordinate (100, 100).

#### D: Come faccio ad aggiungere il livello di zoom ai segnalibri?

 R: Aggiungi il`XYZExplicitDestination` oggetto come azione per la raccolta di segnalibri:

```csharp
item.Action = new GoToAction(dest);
```

 Dove`item` è un`OutlineItemCollection` che rappresenta un segnalibro.

#### D: Come posso salvare il file PDF aggiornato?

 R: Salva il file PDF aggiornato utilizzando il file`Save` metodo del`doc` oggetto:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### D: Posso personalizzare i livelli di zoom per diversi segnalibri?

 R: Sì, puoi personalizzare i livelli di zoom per diversi segnalibri creandone più`XYZExplicitDestination` oggetti con coordinate e fattori di zoom diversi.

#### D: Esiste un limite al numero di segnalibri a cui posso applicare l'ereditarietà dello zoom?

R: In genere non esiste un limite rigido al numero di segnalibri a cui è possibile applicare l'ereditarietà dello zoom. Tuttavia, documenti molto grandi con un numero eccessivo di segnalibri potrebbero richiedere una gestione efficiente della memoria.

#### D: Come posso verificare che l'ereditarietà dello zoom sia stata applicata?

R: Apri il file PDF generato per verificare che i livelli di zoom specificati siano stati ereditati dai segnalibri.