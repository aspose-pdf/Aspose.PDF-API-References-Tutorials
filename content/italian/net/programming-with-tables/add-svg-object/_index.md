---
title: Aggiungi oggetto SVG nel file PDF
linktitle: Aggiungi oggetto SVG nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi facilmente oggetti SVG nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-tables/add-svg-object/
---
In questo tutorial impareremo come aggiungere un oggetto SVG nel file PDF utilizzando la libreria Aspose.PDF per .NET. SVG (Scalable Vector Graphics) è un formato popolare per la grafica vettoriale che può essere facilmente ridimensionato senza perdere qualità. Con Aspose.PDF, puoi aggiungere oggetti SVG ai tuoi documenti PDF a livello di codice.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio installato
- Aspose.PDF per la libreria .NET installata

## Passaggio 1: impostare l'ambiente

Innanzitutto, configuriamo l'ambiente creando un nuovo progetto C# in Visual Studio. Apri Visual Studio e segui questi passaggi:

1. Fare clic su "File" > "Nuovo" > "Progetto" per creare un nuovo progetto.
2. Selezionare il modello "App console (.NET Framework)" o "App console (.NET Core)", a seconda della configurazione.
3. Scegli un nome e una posizione adatti per il tuo progetto, quindi fai clic su "Crea".

## Passaggio 2: crea oggetti documento e immagine

In questo passaggio creeremo gli oggetti necessari per il nostro documento PDF e l'immagine SVG. Apri il file C# del tuo progetto e aggiungi il seguente codice:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Oggetto documento istantaneo
Document doc = new Document();
// Crea un'istanza dell'immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Passaggio 3: imposta le proprietà dell'immagine

Successivamente, imposteremo le proprietà per la nostra immagine SVG. Specificheremo il tipo di file come SVG, il percorso del file SVG e le dimensioni dell'immagine. Aggiungi il seguente codice dopo il passaggio precedente:

```csharp
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso del file di origine
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img. FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
```

## Passaggio 4: crea e configura la tabella

Ora creiamo un oggetto tabella e impostiamo la larghezza delle colonne. Creeremo una tabella con due colonne, ciascuna con una larghezza di 100 unità. Aggiungi il seguente codice:

```csharp
// Crea tabella di istanze
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza per le celle della tabella
table. ColumnWidths = "100 100";
```

## Passaggio 5: aggiungi celle alla tabella

In questo passaggio aggiungeremo una riga e delle celle alla tabella. Ogni riga rappresenta una riga orizzontale nella tabella e le celle vengono aggiunte alle righe. Aggiungi il seguente codice:

```csharp
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza della riga
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Passaggio 6: aggiungi testo e immagine alle celle

Successivamente, aggiungiamo il testo e l'immagine SVG alle celle della tabella. Aggiungeremo il testo "Prima cella" alla prima cella e l'immagine SVG alla seconda cella. Aggiungi il seguente codice:

```csharp
// Aggiungi textfragment alla raccolta di paragrafi dell'oggetto cella
cell.Paragraphs.Add(new TextFragment("First cell"));
// Aggiungi un'altra cella all'oggetto riga
cell = row. Cells. Add();
// Aggiungi l'immagine SVG alla raccolta di paragrafi dell'istanza di cella aggiunta di recente
cell.Paragraphs.Add(img);
```

## Passaggio 7: crea e aggiungi una pagina al documento

Ora creiamo un oggetto pagina e aggiungiamolo al documento. La tabella verrà aggiunta alla raccolta di paragrafi della pagina. Aggiungi il seguente codice:

```csharp
// Crea un oggetto pagina e aggiungilo alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Aggiungi la tabella alla raccolta di paragrafi dell'oggetto pagina
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

### Codice sorgente di esempio per aggiungere un oggetto SVG utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare l'oggetto Documento
Document doc = new Document();
// Crea un'istanza dell'immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Imposta il tipo di immagine come SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Percorso del file di origine
img.File = dataDir + "SVGToPDF.svg";
// Imposta la larghezza per l'istanza dell'immagine
img.FixWidth = 50;
// Imposta l'altezza per l'istanza dell'immagine
img.FixHeight = 50;
// Crea istanza di tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza per le celle della tabella
table.ColumnWidths = "100 100";
//Crea un oggetto riga e aggiungilo all'istanza della tabella
Aspose.Pdf.Row row = table.Rows.Add();
// Crea un oggetto cella e aggiungilo all'istanza della riga
Aspose.Pdf.Cell cell = row.Cells.Add();
// Aggiungi textfragment alla raccolta di paragrafi dell'oggetto cella
cell.Paragraphs.Add(new TextFragment("First cell"));
// Aggiungi un'altra cella all'oggetto riga
cell = row.Cells.Add();
// Aggiungi l'immagine SVG alla raccolta di paragrafi dell'istanza di cella aggiunta di recente
cell.Paragraphs.Add(img);
// Crea un oggetto pagina e aggiungilo alla raccolta di pagine dell'istanza del documento
Page page = doc.Pages.Add();
// Aggiungi la tabella alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Salva file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un oggetto SVG a un file PDF utilizzando la libreria Aspose.PDF per .NET. Abbiamo coperto il processo passo passo di creazione di un documento, configurazione dell'ambiente, aggiunta di un'immagine SVG a una cella di tabella e salvataggio del file PDF. Ora puoi incorporare oggetti SVG nei tuoi documenti PDF a livello di codice.

### Domande frequenti per aggiungere oggetti SVG nel file PDF

#### D: Posso aggiungere più oggetti SVG al documento PDF?

 R: Sì, puoi aggiungere più oggetti SVG al documento PDF. Basta creare e configurare ulteriori`Aspose.Pdf.Image` istanze per ogni immagine SVG che desideri aggiungere, quindi aggiungile alle celle o ai paragrafi della tabella desiderati nel documento PDF.

#### D: Come posso regolare le dimensioni e la posizione dell'immagine SVG nella cella della tabella?

 R: Per regolare la dimensione e la posizione dell'immagine SVG nella cella della tabella, puoi modificare il file`FixWidth` E`FixHeight` proprietà del`Aspose.Pdf.Image`esempio. Puoi anche utilizzare altre proprietà come`HorizontalAlignment` E`VerticalAlignment` della cella della tabella per controllarne il posizionamento.

#### D: È possibile aggiungere testo accanto all'immagine SVG nella stessa cella della tabella?

 R: Sì, è possibile aggiungere testo accanto all'immagine SVG nella stessa cella della tabella. Puoi usare il`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metodo per aggiungere testo alla cella insieme all'immagine SVG.

#### D: Posso aggiungere collegamenti ipertestuali all'immagine SVG?

 R: Sì, puoi aggiungere collegamenti ipertestuali all'immagine SVG utilizzando il file`Hyperlink` proprietà del`Aspose.Pdf.Image` esempio. Imposta l'URL del collegamento ipertestuale o l'azione per rendere l'immagine cliccabile.

#### D: Aspose.PDF per .NET è compatibile con .NET Core 3.1 o versioni successive?

R: Sì, Aspose.PDF per .NET è compatibile con .NET Core 3.1 e versioni successive. È possibile usarlo sia nelle applicazioni .NET Framework che .NET Core.