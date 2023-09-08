---
title: Imposta la proprietà del callout nel file PDF
linktitle: Imposta la proprietà del callout nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come impostare la proprietà callout nel file PDF utilizzando Aspose.PDF per .NET. Personalizza le annotazioni con linee di didascalia, colore del testo e stili finali.
type: docs
weight: 130
url: /it/net/annotations/setcalloutproperty/
---
 Aspose.PDF per .NET è una potente libreria per creare, manipolare e convertire documenti PDF in C#. Una delle funzionalità fornite da questa libreria è la possibilità di impostare proprietà di callout per annotazioni di testo libero nei documenti PDF. Questo può essere fatto utilizzando il`FreeTextAnnotation` classe, che ti consente di creare annotazioni con callout.

In questo tutorial ti guideremo attraverso il processo di impostazione delle proprietà di callout per un'annotazione di testo libero utilizzando Aspose.PDF per .NET in C#. Segui i passaggi seguenti per iniziare.

## Installa Aspose.PDF per .NET

 Se non lo hai già fatto, dovrai farlo[scaricamento](https://releases.aspose.com/pdf/net/) e installare Aspose.PDF per .NET dalle versioni Aspose o tramite il gestore pacchetti NuGet.

## Passaggio 1: crea un nuovo documento PDF

 Crea un nuovo documento PDF utilizzando il file`Document`classe fornita da Aspose.PDF per .NET.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: aggiungi una nuova pagina al documento

 Aggiungi una nuova pagina al documento utilizzando il file`Pages` raccolta del`Document` classe.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 3: imposta l'aspetto predefinito

 Imposta l'aspetto predefinito per l'annotazione a testo libero creandone una nuova`DefaultAppearance` oggetto e impostandone le proprietà come`TextColor` E`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Passaggio 4: crea un'annotazione di testo libero con callout

 Crea una nuova annotazione di testo libero con callout utilizzando il comando`FreeTextAnnotation` classe. Impostare il`Intent` proprietà a`FreeTextIntent.FreeTextCallout` per specificare che si tratta di un'annotazione di callout. Impostare il`EndingStyle` proprietà a`LineEnding.OpenArrow` per specificare lo stile della freccia alla fine del callout. Impostare il`Callout` proprietà in un array di`Point` oggetti che rappresentano i punti della pagina in cui deve essere tracciata la linea di callout.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Passaggio 5: aggiungi l'annotazione di testo libero alla pagina

 Aggiungi l'annotazione di testo libero alla pagina utilizzando il comando`Annotations` raccolta del`Page` classe.

```csharp
page.Annotations.Add(fta);
```

## Passaggio 6: aggiungi testo all'annotazione

 Aggiungi testo all'annotazione impostando il file`RichText`proprietà in una stringa di XML formattato. In questo tutorial, impostiamo il colore del testo su rosso e la dimensione del carattere su 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Passaggio 7: salva il documento

Ora salva il documento utilizzando il seguente codice:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Codice sorgente di esempio per Imposta proprietà callout utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Questo è un esempio</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusione

In questo tutorial, abbiamo esplorato come impostare le proprietà di callout per un'annotazione di testo libero in un documento PDF utilizzando Aspose.PDF per .NET. Le annotazioni di richiamo sono utili per fornire informazioni aggiuntive o spiegazioni relative ad aree specifiche di un documento. Aspose.PDF per .NET fornisce un'ampia gamma di caratteristiche e capacità per lavorare con file PDF, inclusa la creazione e la personalizzazione di annotazioni, come i callout. Seguendo la guida passo passo e utilizzando il codice sorgente C# fornito, gli sviluppatori possono facilmente implementare annotazioni di richiamo nei propri documenti PDF, migliorando l'usabilità e la chiarezza dei propri documenti. Aspose.PDF per .NET è una libreria versatile e affidabile per le operazioni PDF nelle applicazioni .NET, che offre potenti strumenti per gestire in modo efficiente varie attività relative ai PDF.

### Domande frequenti sull'impostazione della proprietà del callout nel file PDF

#### D: Cos'è un'annotazione di richiamo in un documento PDF?

R: Un'annotazione di richiamo in un documento PDF è un tipo di annotazione che consente di creare una casella di testo con una linea guida che punta a un'area specifica del documento. Viene comunemente utilizzato per fornire informazioni aggiuntive o commenti relativi a una particolare sezione o elemento del documento.

#### D: Posso personalizzare l'aspetto dell'annotazione del callout utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare varie proprietà dell'annotazione del callout, come il colore, la dimensione del carattere, l'allineamento del testo, lo stile della linea, lo stile della freccia e altro ancora.

#### D: Come posso aggiungere testo all'annotazione del callout?

 R: Per aggiungere testo all'annotazione del callout, puoi impostare il file`RichText` proprietà del`FreeTextAnnotation` oggetto. IL`RichText` La proprietà accetta una stringa XML formattata che rappresenta il testo da visualizzare nell'annotazione del callout.

#### D: Posso aggiungere più annotazioni di callout a un documento PDF utilizzando Aspose.PDF per .NET?

 R: Sì, puoi creare più annotazioni di richiamo in un documento PDF creando più istanze del file`FreeTextAnnotation`oggetto e aggiungendoli a pagine o posizioni diverse nel documento.