---
title: Aggiungi immagine in una cella di tabella
linktitle: Aggiungi immagine in una cella di tabella
second_title: Aspose.PDF per riferimento all'API .NET
description: Aggiungi un'immagine in una cella di tabella con Aspose.PDF per .NET una guida passo passo per la manipolazione precisa delle immagini nei documenti PDF.
type: docs
weight: 10
url: /it/net/programming-with-tables/add-image-in-a-table-cell/
---
In questo tutorial, ti guideremo attraverso il processo di aggiunta di un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito dimostra come ottenere questa funzionalità. Seguendo i passaggi descritti di seguito, sarai in grado di incorporare le immagini nelle celle della tabella in modo efficace.

Prima di immergerci nel codice, assicurati di avere la libreria Aspose.PDF per .NET installata e referenziata nel tuo progetto.

## Passaggio 1: impostazione del documento

 Per iniziare, dobbiamo creare una nuova istanza del file`Document` classe dallo spazio dei nomi Aspose.Pdf. Questa classe rappresenta un documento PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare un oggetto Document
Document pdfDocument = new Document();
```

## Passaggio 2: creazione di una pagina

Successivamente, dobbiamo aggiungere una pagina al documento PDF. Una pagina funge da contenitore per la tabella e altri elementi.

```csharp
// Creare una pagina nel documento pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Passaggio 3: aggiunta di una tabella

 In questo passaggio creeremo una tabella istanziando il file`Table` classe dallo spazio dei nomi Aspose.Pdf.

```csharp
// Istanziare un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Passaggio 4: impostazione del bordo cella predefinito

 Per garantire la coerenza, possiamo impostare un bordo di cella predefinito utilizzando il file`DefaultCellBorder`proprietà della tabella`BorderInfo` oggetto.

```csharp
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Passaggio 5: impostazione della larghezza delle colonne

 Per definire la larghezza di ciascuna colonna nella tabella, possiamo impostare il file`ColumnWidths` proprietà. Specificare le larghezze come una stringa con valori separati da spazi.

```csharp
// Impostato con la larghezza delle colonne della tabella
tab1.ColumnWidths = "100 100 120";
```

## Passaggio 6: aggiunta di un'immagine a una cella di tabella

Ora arriva la parte emozionante, aggiungere un'immagine a una cella della tabella. Per fare ciò, seguiremo questi passaggi secondari:

## Passaggio 6.1: creazione di un oggetto immagine

 Crea un'istanza di`Image` classe dallo spazio dei nomi Aspose.Pdf. Impostare il`File` proprietà al percorso del file immagine che desideri aggiungere.

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
//Aggiungi un'altra cella alla riga
row1.Cells.Add("Previous cell with image");

// Regola l'allineamento verticale della terza cella
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Passaggio 7: salvataggio del documento

 Infine, possiamo salvare il documento modificato in una posizione specifica utilizzando il file`Save` metodo.

```csharp
// Salva il documento
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Congratulazioni! Hai imparato con successo come aggiungere un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Sentiti libero di esplorare ulteriori opzioni di personalizzazione e di integrare questa funzionalità nei tuoi progetti.

### Codice sorgente di esempio per aggiungere un'immagine in una cella di tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare un oggetto Document
Document pdfDocument = new Document();
// Creare una pagina nel documento pdf
Page sec1 = pdfDocument.Pages.Add();
// Istanziare un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungi la tabella nella raccolta paragrafi della pagina desiderata
sec1.Paragraphs.Add(tab1);
// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Impostato con la larghezza delle colonne della tabella
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Crea righe nella tabella e poi celle nelle righe
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

In questo tutorial, abbiamo trattato una guida passo passo su come aggiungere un'immagine a una cella di tabella utilizzando Aspose.PDF per .NET. Abbiamo iniziato impostando il documento, creando una pagina e aggiungendo una tabella. Quindi, impostiamo il bordo della cella e la larghezza della colonna predefiniti. Abbiamo dimostrato come aggiungere un'immagine a una cella di tabella e regolare l'allineamento verticale della cella. Infine, abbiamo salvato il documento modificato. Seguendo questi passaggi, puoi migliorare in modo efficiente i tuoi documenti PDF con immagini nelle celle della tabella.

### Domande frequenti

#### D: Posso aggiungere più immagini a celle diverse all'interno della stessa tabella utilizzando Aspose.PDF per .NET?

R: Sì, puoi aggiungere più immagini a celle diverse all'interno della stessa tabella utilizzando Aspose.PDF per .NET. Segui semplicemente lo stesso processo illustrato nel tutorial per ogni immagine che desideri aggiungere alla tabella.

#### D: Posso personalizzare le dimensioni e la posizione dell'immagine all'interno della cella della tabella?

 R: Sì, puoi personalizzare le dimensioni e la posizione dell'immagine all'interno della cella della tabella regolando le proprietà del file`Image`oggetto. È possibile impostare la larghezza e l'altezza dell'immagine, nonché l'allineamento all'interno della cella.

#### D: Posso aggiungere immagini a una tabella con un numero dinamico di righe e colonne?

R: Sì, puoi aggiungere immagini a una tabella con un numero dinamico di righe e colonne. Aspose.PDF per .NET offre flessibilità nella creazione di tabelle con dimensioni variabili. Puoi aggiungere righe e celle secondo necessità, quindi aggiungere immagini a celle specifiche di conseguenza.

#### D: Quali formati di immagine sono supportati da Aspose.PDF per .NET per aggiungere immagini alle celle della tabella?

R: Aspose.PDF per .NET supporta un'ampia gamma di formati di immagine, inclusi JPEG, PNG, GIF, BMP e TIFF. Puoi utilizzare immagini di uno qualsiasi di questi formati per aggiungerle alle celle della tabella.

#### D: Posso aggiungere immagini alle tabelle in un documento PDF esistente?

R: Sì, puoi aggiungere immagini alle tabelle in un documento PDF esistente utilizzando Aspose.PDF per .NET. Carica semplicemente il documento esistente e segui gli stessi passaggi per aggiungere immagini alla tabella come dimostrato nel tutorial.