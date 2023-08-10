---
title: Aggiungi annotazione lnk
linktitle: Aggiungi annotazione lnk
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere la funzionalità di annotazione a penna ai documenti PDF in C# utilizzando Aspose.PDF per .NET con guida dettagliata e codice sorgente completo.
type: docs
weight: 20
url: /it/net/annotations/addlnkannotation/
---
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di eseguire varie operazioni PDF. Una di queste operazioni è l'aggiunta di annotazioni a penna ai documenti PDF. In questo articolo, forniremo una guida dettagliata per spiegare il codice sorgente C# per l'aggiunta di annotazioni a penna usando Aspose.PDF per .NET. Iniziamo!

## Comprensione della funzionalità di annotazione a penna di Aspose.PDF per .NET

Prima di addentrarci nel codice sorgente C#, capiamo innanzitutto cos'è l'annotazione a penna e i suoi usi.

L'annotazione a penna è un modo per disegnare annotazioni a penna libera sui documenti PDF. Ti consente di creare annotazioni con uno stilo o un mouse. Questa funzione è utile in situazioni in cui è necessario disegnare diagrammi, schizzi o altri tipi di annotazioni.

## Passaggio 1: creazione di un nuovo documento

Il primo passaggio nell'aggiunta di Annotazioni a penna a un documento PDF consiste nel creare una nuova istanza della classe Document. Ciò si ottiene utilizzando il seguente frammento di codice:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Qui, creiamo una nuova istanza della classe Document e vi aggiungiamo una nuova pagina.

## Passaggio 2: creazione di annotazioni a penna

Il passaggio successivo consiste nel creare un'istanza della classe InkAnnotation. Questo viene fatto utilizzando il seguente frammento di codice:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Qui, per prima cosa creiamo un rettangolo usando la classe System.Drawing.Rectangle e lo convertiamo in Aspose.Pdf.Rectangle usando il metodo FromRect. Creiamo quindi un'istanza della classe InkAnnotation utilizzando il rettangolo, un elenco di punti e la pagina in cui viene aggiunta l'annotazione.

Quindi impostiamo varie proprietà di InkAnnotation, come il titolo, il colore, lo stile del cappuccio, il bordo e l'opacità. Infine, aggiungiamo l'annotazione alla pagina utilizzando il metodo Annotations.Add.

## Passaggio 3: salvare il documento

Il passaggio finale consiste nel salvare il documento PDF con l'annotazione a penna aggiunta. Ciò si ottiene utilizzando il seguente frammento di codice:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Qui, concateniamo il nome del file di output nella directory dei dati e salviamo il documento utilizzando il metodo Save.

### Codice sorgente di esempio per l'aggiunta di annotazioni a penna utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Salva il file di output
doc.Save(dataDir);
```

## Conclusione

In questo tutorial, abbiamo esplorato come aggiungere annotazioni a inchiostro a un documento PDF utilizzando Aspose.PDF per .NET. Seguendo la guida dettagliata e il codice sorgente C# fornito, gli sviluppatori possono facilmente implementare la funzionalità di annotazione a penna nelle proprie applicazioni di elaborazione PDF.

### FAQ

#### D: Cos'è un'annotazione a penna in un documento PDF?

R: Un'annotazione a penna in un documento PDF consente agli utenti di disegnare annotazioni a penna libera utilizzando uno stilo o un mouse. Viene comunemente utilizzato per aggiungere schizzi, diagrammi o altre annotazioni a mano libera a un PDF.

#### D: Posso personalizzare l'aspetto dell'annotazione a penna?

R: Sì, Aspose.PDF per .NET fornisce varie proprietà per personalizzare l'aspetto dell'annotazione a inchiostro, come colore, opacità, stile del cappuccio, larghezza del bordo e altro. Gli sviluppatori possono regolare queste proprietà per soddisfare i loro requisiti specifici.

#### D: È possibile aggiungere più annotazioni a penna a una singola pagina PDF?

R: Sì, puoi aggiungere più annotazioni a inchiostro a una singola pagina PDF utilizzando Aspose.PDF per .NET. Ciascuna annotazione a inchiostro può avere il proprio set di punti e un aspetto personalizzato.

#### D: Posso aggiungere annotazioni a penna ai documenti PDF esistenti?

R: Sì, Aspose.PDF per .NET consente di aggiungere annotazioni a inchiostro sia ai documenti PDF appena creati che ai file PDF esistenti. È possibile aprire un PDF esistente, aggiungere annotazioni a penna e salvare il documento aggiornato.

#### D: Quali sono alcuni casi d'uso comuni per le annotazioni a penna nei documenti PDF?

R: Le annotazioni a penna sono utili per un'ampia gamma di applicazioni, tra cui l'aggiunta di firme o note scritte a mano ai moduli PDF, l'annotazione di progetti architettonici o disegni tecnici e la marcatura di documenti per la revisione collaborativa.