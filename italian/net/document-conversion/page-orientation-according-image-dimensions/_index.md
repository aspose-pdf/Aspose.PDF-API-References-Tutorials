---
title: Orientamento della pagina in base alle dimensioni dell'immagine
linktitle: Orientamento della pagina in base alle dimensioni dell'immagine
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per impostare l'orientamento della pagina in base alle dimensioni dell'immagine con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/document-conversion/page-orientation-according-image-dimensions/
---

In questo tutorial, ti guideremo attraverso il processo di impostazione dell'orientamento della pagina in base alle dimensioni di un'immagine utilizzando Aspose.PDF per .NET. Passeremo in rassegna un elenco di immagini JPG in una determinata directory e regoleremo automaticamente l'orientamento della pagina in base alla larghezza di ciascuna immagine. Seguire i passaggi seguenti per raggiungere questo obiettivo.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: sfoglia le immagini JPG
A questo punto, esploreremo tutte le immagini JPG in una determinata directory. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un nuovo documento PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//Recupera i nomi di tutti i file JPG in una determinata directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trovano le tue immagini JPG.

## Step 2: Creazione della pagina e dell'immagine
Dopo aver sfogliato i file JPG, creeremo una pagina e un'immagine per ogni file. Usa il seguente codice:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Creare un oggetto Pagina
Aspose.Pdf.Page page = doc.Pages.Add();

// Crea un oggetto Immagine
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Passaggio 3: controllo delle dimensioni dell'immagine
Ora controlliamo le dimensioni di ciascuna immagine per determinare l'orientamento della pagina. Usa il seguente codice:

```csharp
// Crea un oggetto BitMap per ottenere informazioni dal file immagine
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Controlla se la larghezza dell'immagine è maggiore o meno della larghezza della pagina
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Se la larghezza dell'immagine è inferiore alla larghezza della pagina, imposta l'orientamento della pagina su verticale
page.PageInfo.IsLandscape = false;
```

## Passaggio 4: aggiunta dell'immagine al documento PDF
Dopo aver verificato le dimensioni dell'immagine, aggiungeremo l'immagine alla raccolta di paragrafi del documento PDF. Usa il seguente codice:

```csharp
//Aggiungi l'immagine alla raccolta di paragrafi del documento PDF
page.Paragraphs.Add(image1);
```

## Passaggio 5: salvare il file PDF
Dopo aver aggiunto tutte le immagini al documento PDF, ora possiamo salvare il file PDF risultante. Ecco l'ultimo passo:

```csharp
// Salva il file PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory desiderata in cui si desidera salvare il file PDF di output.

### Esempio di codice sorgente per l'orientamento della pagina in base alle dimensioni dell'immagine utilizzando Aspose.Words per .NET

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Recupera i nomi di tutti i file JPG in una particolare directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Crea un oggetto pagina
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Crea un oggetto immagine
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Crea un oggetto BitMap per ottenere le informazioni del file immagine
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Controlla se la larghezza del file immagine è maggiore o meno della larghezza della pagina
	if (myimage.Width > page.PageInfo.Width)
		// Se la larghezza dell'immagine è maggiore della larghezza della pagina, imposta l'orientamento della pagina su Orizzontale
		page.PageInfo.IsLandscape = true;
	else
		// Se la larghezza dell'immagine è inferiore alla larghezza della pagina, impostare l'orientamento della pagina su Verticale
		page.PageInfo.IsLandscape = false;
	// Aggiungi l'immagine alla raccolta di paragrafi del documento PDF
	page.Paragraphs.Add(image1);
}
// Salva il file Pdf
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo coperto il processo dettagliato di impostazione dell'orientamento della pagina in base alle dimensioni di un'immagine utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di creare un documento PDF con l'orientamento della pagina corretto per ogni immagine. Questa funzione è utile quando si dispone di immagini di dimensioni diverse e si desidera incorporarle in un documento PDF.