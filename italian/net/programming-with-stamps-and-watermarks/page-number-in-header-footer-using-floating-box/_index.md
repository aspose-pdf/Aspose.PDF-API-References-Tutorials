---
title: Numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile
linktitle: Numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere il numero di pagina nell'intestazione e nel piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere il numero di pagina nell'intestazione e nel piè di pagina di un documento PDF utilizzando FloatingBox con Aspose.PDF per .NET. Useremo il codice sorgente C# fornito per creare un documento PDF, aggiungere una pagina, creare un FloatingBox, impostarne la posizione e aggiungere il numero di pagina, quindi salvare il documento PDF modificato.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: creazione del documento PDF e aggiunta di una pagina

Il primo passaggio consiste nel creare un'istanza del documento PDF e aggiungervi una pagina. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare un'istanza del documento PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Aggiungi una pagina al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

## Passaggio 3: creazione di FloatingBox e aggiunta del numero di pagina

Ora che la pagina è stata aggiunta al documento PDF, possiamo creare un FloatingBox, impostarne la posizione e aggiungervi il numero di pagina. Ecco come:

```csharp
// Crea un FloatingBox con una larghezza di 140 e un'altezza di 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Imposta la posizione a sinistra del paragrafo
box1. Left = 2;

// Imposta la posizione in alto del paragrafo
box1. Top = 10;

// Aggiungi il numero di pagina al FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Aggiungi il FloatingBox alla pagina
page.Paragraphs.Add(box1);
```

Il codice sopra crea un FloatingBox con una larghezza di 140 e un'altezza di 80. Successivamente, impostiamo la sua posizione specificando i valori sinistro e superiore. Infine, aggiungiamo il numero di pagina al FloatingBox utilizzando un TextFragment contenente la sintassi "($p/ $P )" che verrà sostituita con il numero di pagina corrente e il numero totale di pagine.

## Passaggio 4: salvare il documento PDF modificato

Una volta aggiunto il numero di pagina all'intestazione o al piè di pagina utilizzando il FloatingBox, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Codice sorgente di esempio per il numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanza documento istanza
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Aggiungi una pagina nel documento pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inizializza una nuova istanza della classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valore float che indica la posizione a sinistra del paragrafo
box1.Left = 2;

// Valore float che indica la posizione in alto del paragrafo
box1.Top = 10;

// Aggiungi le macro alla raccolta di paragrafi di FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Aggiungi un floatingBox alla pagina
page.Paragraphs.Add(box1);

// Salva il documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere il numero di pagina nell'intestazione e nel piè di pagina del documento PDF utilizzando FloatingBox con Aspose.PDF per .NET. Ora puoi personalizzare intestazioni e piè di pagina aggiungendo informazioni dinamiche come il numero di pagina.
