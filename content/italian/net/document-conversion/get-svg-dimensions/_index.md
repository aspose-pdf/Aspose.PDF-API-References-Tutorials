---
title: Ottieni dimensioni SVG
linktitle: Ottieni dimensioni SVG
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per ottenere dimensioni SVG utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/document-conversion/get-svg-dimensions/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo per ottenere le dimensioni di un file SVG utilizzando Aspose.PDF per .NET. SVG (Scalable Vector Graphics) è un formato immagine basato su XML utilizzato per rappresentare la grafica vettoriale. Utilizzando i passaggi seguenti, sarai in grado di ottenere le dimensioni di un file SVG e salvarle come PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del file SVG
In questo passaggio, caricheremo il file SVG utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file SVG.

## Passaggio 2: regolazione delle dimensioni della pagina
Ora che abbiamo caricato il file SVG, possiamo regolare le dimensioni della pagina per adattarla al contenuto SVG. Utilizza il seguente codice:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Il codice sopra imposta i margini della pagina su zero, consentendo alla dimensione della pagina di adattarsi in base al contenuto SVG.

## Passaggio 3: salvataggio del PDF risultante
Dopo aver regolato le dimensioni della pagina, ora possiamo salvare il documento PDF risultante. Ecco l'ultimo passaggio:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui desideri salvare il file PDF di output.
  
### Codice sorgente di esempio per Ottieni dimensioni SVG utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo trattato il processo passo passo per ottenere le dimensioni di un file SVG utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di ottenere le dimensioni di un file SVG e salvarle nel formato PDF. Questa funzionalità può essere utile quando è necessario misurare le dimensioni di un'immagine vettoriale.

### Domande frequenti

#### D: Cos'è SVG?

R: SVG (Scalable Vector Graphics) è un formato immagine basato su XML utilizzato per rappresentare la grafica vettoriale. A differenza delle immagini raster, i file SVG sono indipendenti dalla risoluzione e possono essere ridimensionati senza perdere qualità. SVG è ampiamente utilizzato per visualizzare la grafica sul Web e può essere modificato e manipolato con facilità.

#### D: Perché utilizzare Aspose.PDF per .NET per la conversione da SVG a PDF?

R: Aspose.PDF per .NET fornisce un modo affidabile ed efficiente per gestire i file SVG e convertirli in formato PDF. Offre varie opzioni e impostazioni per personalizzare il processo di conversione, come la regolazione delle dimensioni della pagina, dei margini e di altre proprietà per garantire una rappresentazione accurata nel PDF.

#### D: Posso convertire file SVG con grafica e testo complessi?

R: Sì, Aspose.PDF per .NET può gestire file SVG con grafica, testo ed elementi vettoriali complessi. Conserva accuratamente i dettagli e la qualità del contenuto SVG durante il processo di conversione, ottenendo documenti PDF di alta qualità.

#### D: È possibile estrarre testo da file SVG con Aspose.PDF per .NET?

R: Sì, Aspose.PDF per .NET ti consente di estrarre testo da file SVG. Puoi utilizzare le funzionalità di estrazione del testo della libreria per estrarre elementi di testo da SVG e salvarli separatamente per un'ulteriore elaborazione.