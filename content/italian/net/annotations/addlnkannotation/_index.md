---
title: Aggiungi annotazione collegamento
linktitle: Aggiungi annotazione collegamento
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere la funzionalità di annotazione input penna ai documenti PDF in C# utilizzando Aspose.PDF per .NET con guida passo passo e codice sorgente completo.
type: docs
weight: 20
url: /it/net/annotations/addlnkannotation/
---
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di eseguire varie operazioni PDF. Una di queste operazioni è l'aggiunta di annotazioni input penna ai documenti PDF. In questo articolo, forniremo una guida passo passo per spiegare il codice sorgente C# per aggiungere annotazioni input penna utilizzando Aspose.PDF per .NET. Iniziamo!

## Comprensione della funzionalità di annotazione dell'input penna di Aspose.PDF per .NET

Prima di immergerci nel codice sorgente C#, comprendiamo innanzitutto cos'è l'annotazione input penna e i suoi usi.

Annotazione input penna è un modo per disegnare annotazioni input penna a mano libera sui documenti PDF. Ti consente di creare annotazioni con uno stilo o un mouse. Questa funzionalità è utile nelle situazioni in cui è necessario disegnare diagrammi, schizzi o altri tipi di annotazioni.

## Passaggio 1: creazione di un nuovo documento

Il primo passaggio per aggiungere annotazioni input penna a un documento PDF è creare una nuova istanza della classe Document. Ciò si ottiene utilizzando il seguente frammento di codice:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Qui creiamo una nuova istanza della classe Document e vi aggiungiamo una nuova pagina.

## Passaggio 2: creazione di annotazioni input penna

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

Qui, creiamo prima un rettangolo utilizzando la classe System.Drawing.Rectangle e lo convertiamo in Aspose.Pdf.Rectangle utilizzando il metodo FromRect. Creiamo quindi un'istanza della classe InkAnnotation utilizzando il rettangolo, un elenco di punti e la pagina in cui viene aggiunta l'annotazione.

Impostiamo quindi varie proprietà di InkAnnotation, come titolo, colore, stile del cappuccio, bordo e opacità. Infine, aggiungiamo l'annotazione alla pagina utilizzando il metodo Annotations.Add.

## Passaggio 3: salvataggio del documento

Il passaggio finale consiste nel salvare il documento PDF con l'annotazione inchiostro aggiunta. Ciò si ottiene utilizzando il seguente frammento di codice:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Qui, concateniamo il nome del file di output nella directory dei dati e salviamo il documento utilizzando il metodo Save.

### Codice sorgente di esempio per l'aggiunta di annotazioni input penna utilizzando Aspose.PDF per .NET

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

In questo tutorial, abbiamo esplorato come aggiungere annotazioni input penna a un documento PDF utilizzando Aspose.PDF per .NET. Seguendo la guida passo passo e il codice sorgente C# fornito, gli sviluppatori possono facilmente implementare la funzionalità di annotazione input penna nelle loro applicazioni di elaborazione PDF.

### Domande frequenti

#### D: Cos'è un'annotazione input penna in un documento PDF?

R: Un'annotazione input penna in un documento PDF consente agli utenti di disegnare annotazioni input penna a mano libera utilizzando uno stilo o un mouse. Viene comunemente utilizzato per aggiungere schizzi disegnati a mano, diagrammi o altre annotazioni a mano libera a un PDF.

#### D: Posso personalizzare l'aspetto dell'annotazione inchiostro?

R: Sì, Aspose.PDF per .NET fornisce varie proprietà per personalizzare l'aspetto dell'annotazione inchiostro, come colore, opacità, stile del cappuccio, larghezza del bordo e altro. Gli sviluppatori possono modificare queste proprietà per soddisfare i loro requisiti specifici.

#### D: È possibile aggiungere più annotazioni input penna a una singola pagina PDF?

R: Sì, puoi aggiungere più annotazioni input penna a una singola pagina PDF utilizzando Aspose.PDF per .NET. Ogni annotazione inchiostro può avere il proprio set di punti e un aspetto personalizzato.

#### D: Posso aggiungere annotazioni input penna a documenti PDF esistenti?

R: Sì, Aspose.PDF per .NET ti consente di aggiungere annotazioni input penna sia ai documenti PDF appena creati che ai file PDF esistenti. È possibile aprire un PDF esistente, aggiungere annotazioni input penna e salvare il documento aggiornato.

#### D: Quali sono alcuni casi d'uso comuni per le annotazioni input penna nei documenti PDF?

R: Le annotazioni input penna sono utili per un'ampia gamma di applicazioni, tra cui l'aggiunta di firme o note scritte a mano ai moduli PDF, l'annotazione di progetti architettonici o disegni tecnici e la marcatura di documenti per la revisione collaborativa.