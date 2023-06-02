---
title: Aggiungi immagine in una cella di tabella
linktitle: Aggiungi immagine in una cella di tabella
second_title: Aspose.PDF per riferimento API .NET
description: Aggiungi un'immagine in una cella di tabella con Aspose.PDF per .NET una guida passo-passo per la manipolazione precisa delle immagini nei documenti PDF.
type: docs
weight: 10
url: /it/net/programming-with-tables/add-image-in-a-table-cell/
---

In questo tutorial, ti guideremo attraverso il processo di aggiunta di un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra come ottenere questa funzionalità. Seguendo i passaggi descritti di seguito, sarai in grado di incorporare efficacemente le immagini nelle celle della tabella.

Prima di immergerci nel codice, assicurati di avere la libreria Aspose.PDF per .NET installata e referenziata nel tuo progetto.

## Passaggio 1: impostazione del documento

 Per iniziare, dobbiamo creare una nuova istanza del file`Document` class dallo spazio dei nomi Aspose.Pdf. Questa classe rappresenta un documento PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un oggetto Document
Document pdfDocument = new Document();
```

## Passaggio 2: creazione di una pagina

Successivamente, dobbiamo aggiungere una pagina al documento PDF. Una pagina funge da contenitore per la tabella e altri elementi.

```csharp
// Crea una pagina nel documento pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Passaggio 3: aggiunta di una tabella

In questo passaggio, creeremo una tabella istanziando il file`Table` class dallo spazio dei nomi Aspose.Pdf.

```csharp
// Crea un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Passaggio 4: impostazione del bordo cella predefinito

 Per garantire la coerenza, possiamo impostare un bordo di cella predefinito utilizzando il`DefaultCellBorder` proprietà della tabella`BorderInfo` oggetto.

```csharp
// Imposta il bordo della cella predefinito utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Passaggio 5: impostazione della larghezza delle colonne

 Per definire la larghezza di ogni colonna nella tabella, possiamo impostare il`ColumnWidths` proprietà. Specificare le larghezze come una stringa con valori separati da spazi.

```csharp
// Impostare con le larghezze delle colonne della tabella
tab1.ColumnWidths = "100 100 120";
```

## Passaggio 6: aggiunta di un'immagine a una cella della tabella

Ora arriva la parte interessante, l'aggiunta di un'immagine a una cella della tabella. Per fare ciò, seguiremo questi passaggi secondari:

## Passaggio 6.1: creazione di un oggetto immagine

 Crea un'istanza di`Image` class dallo spazio dei nomi Aspose.Pdf. Impostare il`File` property al percorso del file immagine che si desidera aggiungere.

```csharp
// Crea un oggetto Immagine
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Passaggio 6.2: creazione di una riga e di celle

Per aggiungere l'immagine alla tabella, dobbiamo prima creare una riga e le celle necessarie.

```csharp
// Crea una riga nella tabella
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Aggiungi una cella di testo alla riga
row1.Cells.Add("Sample text in cell");

// Aggiungi la cella che contiene l'immagine
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Passaggio 6.3: aggiunta dell'immagine alla cella della tabella

Infine, possiamo aggiungere l'immagine alla cella della tabella aggiungendola come paragrafo all'interno della cella.

```csharp
// Aggiungi l'immagine alla cella della tabella
cell2.Paragraphs.Add(img);
```

## Passaggio 6.4: aggiunta di celle aggiuntive

Dopo aver aggiunto la cella dell'immagine, possiamo aggiungere più celle alla riga, se necessario.

```csharp
// Aggiungi un'altra cella alla riga
row1.Cells.Add("Previous cell with image");

// Regola l'allineamento verticale della terza cella
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Passaggio 7: salvare il documento

 Infine, possiamo salvare il documento modificato in una posizione specificata utilizzando il file`Save` metodo.

```csharp
// Salva il documento
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Congratulazioni! Hai imparato con successo come aggiungere un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Sentiti libero di esplorare ulteriori opzioni di personalizzazione e integrare questa funzionalità nei tuoi progetti.

### Esempio di codice sorgente per aggiungere un'immagine in una cella di tabella utilizzando Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza di un oggetto Document
Document pdfDocument = new Document();
// Crea una pagina nel documento pdf
Page sec1 = pdfDocument.Pages.Add();
// Crea un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungi la tabella nella raccolta di paragrafi della pagina desiderata
sec1.Paragraphs.Add(tab1);
// Imposta il bordo della cella predefinito utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Impostare con le larghezze delle colonne della tabella
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Crea righe nella tabella e quindi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Aggiungi la cella che contiene l'immagine
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Aggiungi l'immagine alla cella della tabella
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Salva il documento
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Conclusione

In questo tutorial, abbiamo trattato una guida dettagliata su come aggiungere un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Abbiamo iniziato impostando il documento, creando una pagina e aggiungendo una tabella. Quindi, impostiamo il bordo della cella predefinito e le larghezze delle colonne. Abbiamo dimostrato come aggiungere un'immagine a una cella di tabella e regolare l'allineamento verticale della cella. Infine, abbiamo salvato il documento modificato. Seguendo questi passaggi, puoi migliorare i tuoi documenti PDF con immagini nelle celle della tabella in modo efficiente.