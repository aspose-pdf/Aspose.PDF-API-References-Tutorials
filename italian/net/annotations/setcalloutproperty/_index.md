---
title: Imposta proprietà callout nel file PDF
linktitle: Imposta proprietà callout nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare la proprietà Callout nel file PDF utilizzando Aspose.PDF per .NET. Personalizza le annotazioni con linee di richiamo, colore del testo e stili finali.
type: docs
weight: 130
url: /it/net/annotations/setcalloutproperty/
---
 Aspose.PDF per .NET è una potente libreria per creare, manipolare e convertire documenti PDF in C#. Una delle funzionalità fornite da questa libreria è la possibilità di impostare le proprietà dei callout per le annotazioni di testo libero nei documenti PDF. Questo può essere fatto usando il`FreeTextAnnotation` class, che consente di creare annotazioni con callout.

In questo tutorial, ti guideremo attraverso il processo di impostazione delle proprietà di callout per un'annotazione di testo libero utilizzando Aspose.PDF per .NET in C#. Segui i passaggi seguenti per iniziare.

## Installa Aspose.PDF per .NET

 Se non l'hai già fatto, dovrai farlo[scaricamento](https://releases.aspose.com/pdf/net/) e installa Aspose.PDF per .NET dalle versioni di Aspose o tramite il gestore di pacchetti NuGet.

## Passaggio 1: crea un nuovo documento PDF

 Creare un nuovo documento PDF utilizzando il file`Document`classe fornita da Aspose.PDF per .NET.

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

 Imposta l'aspetto predefinito per l'annotazione di testo libero creando un nuovo file`DefaultAppearance` oggetto e impostando le sue proprietà come`TextColor` E`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Passaggio 4: creare un'annotazione di testo libero con callout

 Crea una nuova annotazione di testo libero con callout utilizzando il file`FreeTextAnnotation` classe. Impostare il`Intent` proprietà a`FreeTextIntent.FreeTextCallout` per specificare che si tratta di un'annotazione callout. Impostare il`EndingStyle` proprietà a`LineEnding.OpenArrow` per specificare lo stile della freccia alla fine del richiamo. Impostare il`Callout` proprietà a un array di`Point` oggetti che rappresentano i punti della pagina in cui deve essere disegnata la linea di callout.

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

 Aggiungere l'annotazione di testo libero alla pagina utilizzando il file`Annotations` raccolta del`Page` classe.

```csharp
page.Annotations.Add(fta);
```

## Passaggio 6: aggiungere testo all'annotazione

 Aggiungi testo all'annotazione impostando il file`RichText`property in una stringa di XML formattato. In questo tutorial, impostiamo il colore del testo su rosso e la dimensione del carattere su 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Passaggio 7: salvare il documento

Ora salva il documento utilizzando il seguente codice:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Esempio di codice sorgente per Set Callout Property utilizzando Aspose.PDF per .NET

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

In questo tutorial, abbiamo esplorato come impostare le proprietà del callout per un'annotazione di testo libero in un documento PDF utilizzando Aspose.PDF per .NET. Le annotazioni di callout sono utili per fornire ulteriori informazioni o spiegazioni relative ad aree specifiche in un documento. Aspose.PDF per .NET offre un'ampia gamma di funzionalità e capacità per lavorare con i file PDF, inclusa la creazione e la personalizzazione di annotazioni, come i callout. Seguendo la guida dettagliata e utilizzando il codice sorgente C# fornito, gli sviluppatori possono facilmente implementare annotazioni callout nei loro documenti PDF, migliorando l'usabilità e la chiarezza dei loro documenti. Aspose.PDF per .NET è una libreria versatile e affidabile per le operazioni PDF nelle applicazioni .NET, che offre potenti strumenti per gestire in modo efficiente varie attività relative ai PDF.

### Domande frequenti per impostare la proprietà callout nel file PDF

#### D: Cos'è un'annotazione di callout in un documento PDF?

R: Un'annotazione di callout in un documento PDF è un tipo di annotazione che consente di creare una casella di testo con una linea guida che punta a un'area specifica nel documento. Viene comunemente utilizzato per fornire informazioni aggiuntive o commenti relativi a una particolare sezione o elemento del documento.

#### D: Posso personalizzare l'aspetto dell'annotazione del callout utilizzando Aspose.PDF per .NET?

R: Sì, puoi personalizzare varie proprietà dell'annotazione del richiamo, come il colore, la dimensione del carattere, l'allineamento del testo, lo stile della linea, lo stile della freccia e altro.

#### D: Come si aggiunge del testo all'annotazione del callout?

 R: Per aggiungere testo all'annotazione del callout, puoi impostare il file`RichText` proprietà del`FreeTextAnnotation` oggetto. IL`RichText` La proprietà accetta una stringa di XML formattato che rappresenta il testo da visualizzare nell'annotazione del callout.

#### D: Posso aggiungere più annotazioni callout a un documento PDF utilizzando Aspose.PDF per .NET?

 R: Sì, puoi creare più annotazioni callout in un documento PDF creando più istanze del file`FreeTextAnnotation`oggetto e aggiungendoli a diverse pagine o posizioni nel documento.