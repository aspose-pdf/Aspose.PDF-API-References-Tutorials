---
title: Aggiungi oggetto SVG
linktitle: Aggiungi oggetto SVG
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi facilmente oggetti SVG ai tuoi file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-tables/add-svg-object/
---

In questo tutorial impareremo come aggiungere un oggetto SVG a un file PDF utilizzando la libreria Aspose.PDF per .NET. SVG (Scalable Vector Graphics) è un formato popolare per la grafica vettoriale che può essere facilmente ridimensionato senza perdere qualità. Con Aspose.PDF, puoi aggiungere oggetti SVG ai tuoi documenti PDF in modo programmatico.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio installato
- Aspose.PDF per la libreria .NET installata

## Passaggio 1: configurare l'ambiente

Innanzitutto, impostiamo l'ambiente creando un nuovo progetto C# in Visual Studio. Apri Visual Studio e segui questi passaggi:

1. Fare clic su "File" > "Nuovo" > "Progetto" per creare un nuovo progetto.
2. Selezionare il modello "App console (.NET Framework)" o "App console (.NET Core)", a seconda della configurazione.
3. Scegli un nome e una posizione adatti per il tuo progetto, quindi fai clic su "Crea".

## Passaggio 2: creare documenti e oggetti immagine

In questo passaggio, creeremo gli oggetti necessari per il nostro documento PDF e l'immagine SVG. Apri il file C# del tuo progetto e aggiungi il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Oggetto documento istantaneo
Document doc = new Document();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Passaggio 3: impostare le proprietà dell'immagine

Successivamente, imposteremo le proprietà per la nostra immagine SVG. Specificheremo il tipo di file come SVG, il percorso del file SVG e le dimensioni dell'immagine. Aggiungi il seguente codice dopo il passaggio precedente:

```csharp
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso per il file di origine
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img. FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
```

## Passaggio 4: creare e configurare la tabella

Ora, creiamo un oggetto tabella e impostiamo le larghezze delle colonne. Creeremo una tabella con due colonne, ciascuna con una larghezza di 100 unità. Aggiungi il seguente codice:

```csharp
// Crea tabella di istanza
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza delle celle della tabella
table. ColumnWidths = "100 100";
```

## Passaggio 5: aggiungi celle alla tabella

In questo passaggio, aggiungeremo una riga e celle alla tabella. Ogni riga rappresenta una riga orizzontale nella tabella e le celle vengono aggiunte alle righe. Aggiungi il seguente codice:

```csharp
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza di riga
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Passaggio 6: aggiungi testo e immagine alle celle

Successivamente, aggiungiamo il testo e l'immagine SVG alle celle della tabella. Aggiungeremo il testo "Prima cella" alla prima cella e l'immagine SVG alla seconda cella. Aggiungi il seguente codice:

```csharp
// Aggiungi un frammento di testo alla raccolta di paragrafi dell'oggetto cella
cell.Paragraphs.Add(new TextFragment("First cell"));
// Aggiungi un'altra cella all'oggetto riga
cell = row. Cells. Add();
// Aggiungi l'immagine SVG alla raccolta di paragrafi dell'istanza di cella aggiunta di recente
cell.Paragraphs.Add(img);
```

## Passaggio 7: creare e aggiungere una pagina al documento

Ora, creiamo un oggetto pagina e aggiungiamolo al documento. La tabella verrà aggiunta alla raccolta dei paragrafi della pagina. Aggiungi il seguente codice:

```csharp
// Crea un oggetto pagina e aggiungilo alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Aggiungi tabella alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(table);
```

## Passaggio 8: salva il file PDF

Infine, salveremo il file PDF nella posizione specificata. Aggiungi il seguente codice:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per aggiungere un oggetto SVG utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso per il file di origine
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img.FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
// Crea un'istanza di tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza delle celle della tabella
table.ColumnWidths = "100 100";
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza di riga
Aspose.Pdf.Cell cell = row.Cells.Add();
// Aggiungi un frammento di testo alla raccolta di paragrafi dell'oggetto cella
cell.Paragraphs.Add(new TextFragment("First cell"));
// Aggiungi un'altra cella all'oggetto riga
cell = row.Cells.Add();
// Aggiungi l'immagine SVG alla raccolta di paragrafi dell'istanza di cella aggiunta di recente
cell.Paragraphs.Add(img);
// Crea un oggetto pagina e aggiungilo alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Aggiungi tabella alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un oggetto SVG a un file PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo coperto il processo passo-passo di creazione di un documento, impostazione dell'ambiente, aggiunta di un'immagine SVG a una cella di tabella e salvataggio del file PDF. Ora puoi incorporare oggetti SVG nei tuoi documenti PDF in modo programmatico.