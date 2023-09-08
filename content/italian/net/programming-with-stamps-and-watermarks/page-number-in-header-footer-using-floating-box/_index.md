---
title: Numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile
linktitle: Numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere il numero di pagina nell'intestazione e nel piè di pagina di un documento PDF con Aspose.PDF per .NET.
type: docs
weight: 150
url: /it/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere il numero di pagina nell'intestazione e nel piè di pagina di un documento PDF utilizzando FloatingBox con Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per creare un documento PDF, aggiungere una pagina, creare un FloatingBox, impostarne la posizione e aggiungervi il numero di pagina, quindi salvare il documento PDF modificato.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: creazione del documento PDF e aggiunta di una pagina

Il primo passo è creare un'istanza del documento PDF e aggiungervi una pagina. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare un'istanza del documento PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Aggiungi una pagina al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF.

## Passaggio 3: creazione del FloatingBox e aggiunta del numero di pagina

Ora che la pagina è stata aggiunta al documento PDF, possiamo creare un FloatingBox, impostarne la posizione e aggiungervi il numero di pagina. Ecco come:

```csharp
// Crea un FloatingBox con una larghezza di 140 e un'altezza di 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Imposta la posizione sinistra del paragrafo
box1. Left = 2;

// Imposta la prima posizione del paragrafo
box1. Top = 10;

// Aggiungi il numero di pagina al FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Aggiungi il FloatingBox alla pagina
page.Paragraphs.Add(box1);
```

Il codice sopra crea un FloatingBox con una larghezza di 140 e un'altezza di 80. Successivamente, impostiamo la sua posizione specificando i valori sinistro e superiore. Infine, aggiungiamo il numero di pagina al FloatingBox utilizzando un TextFragment contenente la sintassi "($p/ $P )" che verrà sostituita con il numero di pagina corrente e il numero totale di pagine.

## Passaggio 4: salvataggio del documento PDF modificato

Una volta aggiunto il numero di pagina all'intestazione o al piè di pagina utilizzando FloatingBox, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Codice sorgente di esempio per il numero di pagina nel piè di pagina dell'intestazione utilizzando la casella mobile utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Istanziare l'istanza del documento
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Aggiungi una pagina al documento PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

//Inizializza una nuova istanza della classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valore float che indica la posizione a sinistra del paragrafo
box1.Left = 2;

// Valore float che indica la posizione iniziale del paragrafo
box1.Top = 10;

// Aggiungi le macro alla raccolta paragrafi di FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Aggiungi un floatBox alla pagina
page.Paragraphs.Add(box1);

// Salva il documento
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere il numero di pagina nell'intestazione e nel piè di pagina del documento PDF utilizzando FloatingBox con Aspose.PDF per .NET. Ora puoi personalizzare intestazioni e piè di pagina aggiungendo informazioni dinamiche come il numero di pagina.

### Domande frequenti

#### D: Cos'è un FloatingBox e come viene utilizzato per aggiungere numeri di pagina nell'intestazione o nel piè di pagina di un documento PDF?

R: Un FloatingBox è un elemento di layout versatile in Aspose.PDF che può contenere vari contenuti, inclusi testo e immagini. In questo tutorial viene utilizzato per creare un contenitore per il numero di pagina, consentendo di inserire dinamicamente il numero di pagina corrente e il conteggio totale delle pagine nell'intestazione o nel piè di pagina.

#### D: In che modo il codice sorgente C# fornito riesce ad aggiungere numeri di pagina utilizzando un FloatingBox?

R: Lo snippet di codice mostra come creare un documento PDF, aggiungere una pagina, creare un FloatingBox, impostarne la posizione all'interno della pagina e inserire il numero di pagina utilizzando un TextFragment. La sintassi "($p/ $P )" nel TextFragment viene sostituita con il numero di pagina corrente e il conteggio totale delle pagine.

#### D: Posso personalizzare l'aspetto e la formattazione del numero di pagina aggiunto utilizzando FloatingBox?

R: Sì, puoi personalizzare l'aspetto del numero di pagina modificando le proprietà di TextFragment all'interno di FloatingBox. Puoi modificare la dimensione, il colore, lo stile, l'allineamento e altre opzioni di formattazione del carattere.

#### D: È possibile aggiungere diversi elementi dinamici, come data e ora, all'intestazione o al piè di pagina utilizzando un approccio simile?

R: Assolutamente, puoi aggiungere diversi elementi dinamici come data, ora, metadati del documento o testo personalizzato modificando il contenuto TextFragment all'interno di FloatingBox. Puoi utilizzare macro come "($p/ $P )" per i numeri di pagina o "($date)" per la data corrente.

#### D: Come posso specificare la posizione del FloatingBox all'interno della sezione dell'intestazione o del piè di pagina?
 R: Il codice fornito imposta la posizione del FloatingBox utilizzando il file`Left` E`Top` proprietà. È possibile modificare questi valori per posizionare FloatingBox come desiderato all'interno della sezione dell'intestazione o del piè di pagina.

#### D: Posso utilizzare un carattere o uno stile diverso per il numero di pagina nell'intestazione o nel piè di pagina?

R: Sì, puoi personalizzare il carattere, lo stile e altre proprietà di formattazione del testo del numero di pagina modificando le proprietà TextFragment all'interno di FloatingBox.

#### D: Cosa succede se il contenuto del FloatingBox supera le sue dimensioni?

R: Se il contenuto all'interno del FloatingBox supera le sue dimensioni, potrebbe essere tagliato o potrebbero verificarsi problemi di layout. Assicurati che le dimensioni del FloatingBox siano adatte ad accogliere il contenuto e valuta la possibilità di modificare il layout della pagina, se necessario.

#### D: È possibile aggiungere più FloatingBox con contenuti diversi nell'intestazione o nel piè di pagina della stessa pagina?

R: Sì, puoi aggiungere più FloatingBox con contenuti diversi all'intestazione o al piè di pagina della stessa pagina creando istanze FloatingBox separate e aggiungendole alla raccolta Paragraphs della pagina.

#### D: Posso utilizzare l'approccio FloatingBox per aggiungere contenuto ad altre sezioni del documento PDF, come il corpo o i margini?

R: Sebbene i FloatingBox siano comunemente utilizzati per intestazioni e piè di pagina, puoi anche utilizzarli per aggiungere contenuto ad altre sezioni del documento PDF, come il corpo o i margini, posizionandoli di conseguenza all'interno della pagina.