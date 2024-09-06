---
title: Adattamento automatico alla finestra
linktitle: Adattamento automatico alla finestra
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per utilizzare Aspose.PDF per .NET e ottenere l'adattamento automatico alla finestra nella generazione di PDF.
type: docs
weight: 50
url: /it/net/programming-with-tables/auto-fit-to-window/
---
Il seguente articolo è una guida passo passo su come utilizzare il codice sorgente C# fornito per ottenere la funzionalità Auto Fit To Window tramite la libreria Aspose.PDF per .NET. La funzione Auto Fit To Window consente di generare file PDF con un layout adattato alla finestra di visualizzazione. Questa funzionalità è particolarmente utile quando si desidera che il documento PDF si adatti automaticamente alle dimensioni della finestra del lettore PDF utilizzata dall'utente.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, devi installare la libreria Aspose.PDF per .NET sul tuo computer. Assicurati anche di importare i namespace necessari nel tuo progetto.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creazione di un documento PDF

 Per iniziare, è necessario creare un`Document` oggetto chiamando il suo costruttore predefinito.

```csharp
Document doc = new Document();
```

 Quindi, crea una sezione in`Pdf` oggetto.

```csharp
Page sec1 = doc.Pages.Add();
```

## Passaggio 3: aggiunta di una tabella al documento

 In questo passaggio, aggiungeremo una tabella al nostro documento PDF. Per prima cosa creiamo un`Table` oggetto.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Successivamente, aggiungi la tabella alla raccolta dei paragrafi della sezione.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Passaggio 4: personalizzazione dell'aspetto della tabella

È possibile personalizzare l'aspetto della tabella impostando proprietà quali bordi e margini delle celle.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Passaggio 4: aggiunta di righe e celle alla tabella

Ora aggiungiamo righe e celle alla nostra tabella. Iniziamo creando una riga e aggiungendo celle a quella riga.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Passaggio 5: salvataggio del documento

Infine, specificare il percorso del file di output e salvare il documento.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Adattamento automatico alla finestra utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare l'oggetto Pdf chiamando il suo costruttore vuoto
Document doc = new Document();
// Crea la sezione nell'oggetto Pdf
Page sec1 = doc.Pages.Add();

// Creare un'istanza di un oggetto tabella
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Aggiungere la tabella nella raccolta di paragrafi della sezione desiderata
sec1.Paragraphs.Add(tab1);

// Impostato con le larghezze delle colonne della tabella
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Imposta il bordo predefinito della cella utilizzando l'oggetto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Imposta il bordo della tabella utilizzando un altro oggetto BorderInfo personalizzato
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Crea l'oggetto MarginInfo e imposta i suoi margini sinistro, inferiore, destro e superiore
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Imposta la spaziatura predefinita delle celle sull'oggetto MarginInfo
tab1.DefaultCellPadding = margin;

// Crea righe nella tabella e poi celle nelle righe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come usare Aspose.PDF per .NET per generare un file PDF con la funzionalità Auto Fit To Window. Questa funzionalità è estremamente utile quando vuoi che il tuo documento PDF si adatti automaticamente alle dimensioni della finestra di visualizzazione. Aspose.PDF per .NET offre molte altre potenti funzionalità per generare e manipolare file PDF. Ti incoraggio a esplorare ulteriormente questa libreria per scoprire tutte le sue capacità.

### Domande frequenti

#### D: Qual è lo scopo della funzione Adatta automaticamente alla finestra nella generazione di PDF?

R: La funzionalità Auto Fit To Window nella generazione di PDF assicura che il layout del documento PDF si adatti automaticamente alle dimensioni della finestra del lettore PDF utilizzata dall'utente. Ciò consente una migliore visualizzazione e assicura che il contenuto si adatti perfettamente all'area di visualizzazione disponibile.

#### D: Posso personalizzare l'aspetto della tabella, ad esempio la dimensione del carattere e i colori?

R: Sì, puoi personalizzare l'aspetto della tabella nel documento PDF usando Aspose.PDF per .NET. Il frammento di codice fornito mostra come impostare proprietà come bordi delle celle, margini e larghezze delle colonne. Puoi personalizzare ulteriormente la dimensione del carattere, i colori e altri aspetti di stile della tabella e del suo contenuto.

#### D: Come posso integrare Aspose.PDF per .NET nel mio progetto C#?

R: Per usare Aspose.PDF per .NET nel tuo progetto C#, devi prima installare la libreria Aspose.PDF per .NET sul tuo computer. Quindi, puoi aggiungere un riferimento alla libreria nel tuo progetto C#. Infine, importa i namespace necessari per accedere alle classi e ai metodi forniti da Aspose.PDF per .NET.

#### D: Aspose.PDF per .NET è compatibile con le applicazioni .NET Core?

R: Sì, Aspose.PDF per .NET è compatibile con le applicazioni .NET Core. Supporta varie piattaforme .NET, tra cui .NET Framework, .NET Core e .NET 5.0+.

#### D: Posso aggiungere altre tabelle al documento PDF?

R: Sì, puoi aggiungere più tabelle a un documento PDF seguendo passaggi simili a quelli illustrati nel frammento di codice. Crea semplicemente nuove istanze di`Aspose.Pdf.Table` classe e aggiungerli a diverse sezioni o pagine del documento PDF.