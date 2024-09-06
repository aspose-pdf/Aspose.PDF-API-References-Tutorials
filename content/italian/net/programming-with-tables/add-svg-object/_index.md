---
title: Aggiungi oggetto SVG nel file PDF
linktitle: Aggiungi oggetto SVG nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Aggiungi facilmente oggetti SVG nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-tables/add-svg-object/
---
In questo tutorial, impareremo come aggiungere un oggetto SVG in un file PDF usando la libreria Aspose.PDF per .NET. SVG (Scalable Vector Graphics) è un formato popolare per la grafica vettoriale che può essere facilmente ridimensionato senza perdere qualità. Con Aspose.PDF, puoi aggiungere oggetti SVG ai tuoi documenti PDF in modo programmatico.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio installato
- Aspose.PDF per la libreria .NET installata

## Passaggio 1: impostare l'ambiente

Per prima cosa, impostiamo l'ambiente creando un nuovo progetto C# in Visual Studio. Apri Visual Studio e segui questi passaggi:

1. Fare clic su "File" > "Nuovo" > "Progetto" per creare un nuovo progetto.
2. Selezionare il modello "App console (.NET Framework)" o "App console (.NET Core)", a seconda della configurazione.
3. Scegli un nome e un percorso adatti per il tuo progetto, quindi fai clic su "Crea".

## Passaggio 2: creare oggetti documento e immagine

In questo passaggio, creeremo gli oggetti necessari per il nostro documento PDF e l'immagine SVG. Apri il file C# del tuo progetto e aggiungi il seguente codice:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Oggetto Documento istantaneo
Document doc = new Document();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Passaggio 3: imposta le proprietà dell'immagine

Successivamente, imposteremo le proprietà per la nostra immagine SVG. Specifichiamo il tipo di file come SVG, il percorso al file SVG e le dimensioni dell'immagine. Aggiungiamo il seguente codice dopo il passaggio precedente:

```csharp
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso per il file sorgente
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img. FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
```

## Passaggio 4: creare e configurare la tabella

Ora, creiamo un oggetto tabella e impostiamo le larghezze delle colonne. Creeremo una tabella con due colonne, ciascuna con una larghezza di 100 unità. Aggiungiamo il seguente codice:

```csharp
// Crea tabella istanza
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza per le celle della tabella
table. ColumnWidths = "100 100";
```

## Passaggio 5: aggiungere celle alla tabella

In questo passaggio, aggiungeremo una riga e delle celle alla tabella. Ogni riga rappresenta una riga orizzontale nella tabella e le celle vengono aggiunte alle righe. Aggiungere il seguente codice:

```csharp
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza di riga
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Passaggio 6: aggiungere testo e immagine alle celle

Ora aggiungiamo il testo e l'immagine SVG alle celle della tabella. Aggiungeremo il testo "First cell" alla prima cella e l'immagine SVG alla seconda cella. Aggiungiamo il seguente codice:

```csharp
// Aggiungi textfragment alla raccolta di paragrafi dell'oggetto cella
cell.Paragraphs.Add(new TextFragment("First cell"));
// Aggiungi un'altra cella all'oggetto riga
cell = row. Cells. Add();
// Aggiungi l'immagine SVG alla raccolta di paragrafi dell'istanza di cella aggiunta di recente
cell.Paragraphs.Add(img);
```

## Passaggio 7: creare e aggiungere una pagina al documento

Ora, creiamo un oggetto pagina e aggiungiamolo al documento. La tabella verrà aggiunta alla raccolta di paragrafi della pagina. Aggiungi il seguente codice:

```csharp
// Crea un oggetto pagina e aggiungilo alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Aggiungi tabella alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(table);
```

## Passaggio 8: Salvare il file PDF

Infine, salveremo il file PDF nella posizione specificata. Aggiungiamo il seguente codice:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Esempio di codice sorgente per aggiungere un oggetto SVG utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// Crea un'istanza di immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso per il file sorgente
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img.FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
// Crea istanza tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza per le celle della tabella
table.ColumnWidths = "100 100";
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza di riga
Aspose.Pdf.Cell cell = row.Cells.Add();
// Aggiungi textfragment alla raccolta di paragrafi dell'oggetto cella
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

In questo tutorial, abbiamo imparato come aggiungere un oggetto SVG a un file PDF usando la libreria Aspose.PDF per .NET. Abbiamo trattato il processo passo dopo passo di creazione di un documento, impostazione dell'ambiente, aggiunta di un'immagine SVG a una cella di tabella e salvataggio del file PDF. Ora puoi incorporare oggetti SVG nei tuoi documenti PDF a livello di programmazione.

### Domande frequenti per aggiungere un oggetto SVG nel file PDF

#### D: Posso aggiungere più oggetti SVG al documento PDF?

 A: Sì, puoi aggiungere più oggetti SVG al documento PDF. Basta creare e configurare altri`Aspose.Pdf.Image` istanze per ogni immagine SVG che vuoi aggiungere e poi aggiungile alle celle della tabella o ai paragrafi desiderati nel documento PDF.

#### D: Come posso regolare le dimensioni e la posizione dell'immagine SVG nella cella della tabella?

 A: Per regolare le dimensioni e la posizione dell'immagine SVG nella cella della tabella, puoi modificare`FixWidth` E`FixHeight` proprietà del`Aspose.Pdf.Image`istanza. Puoi anche usare altre proprietà come`HorizontalAlignment` E`VerticalAlignment` della cella della tabella per controllarne il posizionamento.

#### D: È possibile aggiungere del testo accanto all'immagine SVG nella stessa cella della tabella?

 A: Sì, è possibile aggiungere testo accanto all'immagine SVG nella stessa cella della tabella. Puoi usare`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` Metodo per aggiungere testo alla cella insieme all'immagine SVG.

#### D: Posso aggiungere collegamenti ipertestuali all'immagine SVG?

 A: Sì, puoi aggiungere collegamenti ipertestuali all'immagine SVG utilizzando`Hyperlink` proprietà del`Aspose.Pdf.Image` istanza. Imposta l'URL o l'azione dell'hyperlink per rendere l'immagine cliccabile.

#### D: Aspose.PDF per .NET è compatibile con .NET Core 3.1 o versioni successive?

R: Sì, Aspose.PDF per .NET è compatibile con .NET Core 3.1 e versioni successive. Puoi utilizzarlo sia nelle applicazioni .NET Framework che .NET Core.