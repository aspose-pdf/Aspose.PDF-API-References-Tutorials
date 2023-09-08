---
title: Annotazione invisibile nel file PDF
linktitle: Annotazione invisibile nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come annotare invisibili nel file PDF utilizzando il codice sorgente C# con Aspose.PDF per .NET. Guida passo passo.
type: docs
weight: 100
url: /it/net/annotations/invisibleannotation/
---
Le annotazioni nel file PDF sono una potente funzionalità che ti consente di aggiungere informazioni o note aggiuntive a un documento senza modificarne il contenuto effettivo. Possono essere utilizzati per evidenziare testo, attirare l'attenzione su aree specifiche di un documento o aggiungere commenti o feedback.

Esistono molti tipi diversi di annotazioni che è possibile utilizzare nei documenti PDF, tra cui:

- Annotazioni di testo
- Collega annotazioni
- Annotazioni sui timbri
- Annotazioni sonore
- Annotazioni sugli allegati di file
- e molti altri

## Passaggio 1: creazione di un'annotazione invisibile in un documento PDF utilizzando Aspose.PDF per .NET

 Per creare un'annotazione invisibile in un documento PDF utilizzando Aspose.PDF per .NET, dobbiamo prima creare un file`FreeTextAnnotation` oggetto e specificare la posizione e la dimensione dell'annotazione.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Nel codice sopra, creiamo a`FreeTextAnnotation`oggetto e specificare la posizione dell'annotazione nella pagina 2 del documento PDF. Specifichiamo inoltre il tipo di carattere, la dimensione e il colore per il testo che verrà visualizzato nell'annotazione.

## Passaggio 2: aggiunta di caratteristiche all'annotazione invisibile

Successivamente, possiamo aggiungere alcune caratteristiche all'annotazione, come il colore del bordo, il colore dello sfondo o l'opacità.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Nel codice sopra, impostiamo il colore del bordo dell'annotazione su rosso.

## Passaggio 3: impostazione dei flag di annotazione

Dopo aver creato l'annotazione e impostato le sue caratteristiche, possiamo specificare i flag di annotazione. In questo tutorial vogliamo che l'annotazione sia stampabile, ma non visualizzabile.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Passaggio 4: salvataggio del documento PDF modificato

Infine, possiamo salvare il documento PDF modificato con la nuova annotazione invisibile.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Esempio di codice sorgente per come annotare l'annotazione invisibile utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Salva il file di output
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come creare un'annotazione invisibile in un documento PDF utilizzando Aspose.PDF per .NET. Le annotazioni invisibili sono una funzionalità utile quando desideri aggiungere informazioni o note aggiuntive a un documento senza mostrarle al lettore. Seguendo la guida passo passo e utilizzando il codice sorgente C# fornito, gli sviluppatori possono creare e personalizzare facilmente annotazioni invisibili nei propri documenti PDF. Aspose.PDF per .NET fornisce un set completo di strumenti per lavorare con le annotazioni, consentendoti di migliorare l'interattività e l'usabilità dei tuoi file PDF.

### Domande frequenti

#### D: Cos'è un'annotazione invisibile in un documento PDF?

R: Un'annotazione invisibile in un documento PDF è un'annotazione che non è visibile sulla pagina ma contiene informazioni o note aggiuntive. Ti consente di aggiungere commenti o feedback senza mostrarli al lettore.

#### D: Quali tipi di caratteristiche possono essere aggiunte a un'annotazione invisibile?

R: È possibile aggiungere varie caratteristiche a un'annotazione invisibile, come il colore del bordo, il colore dello sfondo, l'opacità, il tipo di carattere, la dimensione e il colore del testo che verrà visualizzato.

#### D: Posso impostare flag di annotazione diversi per un'annotazione invisibile?

R: Sì, puoi impostare diversi flag di annotazione per un'annotazione invisibile, a seconda delle tue esigenze. Ad esempio, puoi rendere l'annotazione stampabile ma non visualizzabile.

#### D: Come posso aggiungere un'annotazione invisibile a una pagina specifica del documento PDF?

 R: Per aggiungere un'annotazione invisibile a una pagina specifica del documento PDF, è necessario creare un file`FreeTextAnnotation` oggetto e specificare la posizione e la dimensione dell'annotazione su quella pagina.

#### D: Posso modificare le caratteristiche di un'annotazione invisibile esistente in un file PDF?

R: Sì, puoi modificare le caratteristiche di un'annotazione invisibile esistente in un file PDF utilizzando Aspose.PDF per .NET. Puoi modificare il tipo di carattere, la dimensione, il colore, il colore del bordo, il colore dello sfondo, l'opacità e altre proprietà dell'annotazione.