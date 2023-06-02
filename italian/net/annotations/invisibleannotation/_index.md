---
title: Annotazione invisibile
linktitle: Annotazione invisibile
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come annotare in modo invisibile i PDF utilizzando il codice sorgente C# con Aspose.PDF per .NET. Guida passo dopo passo.
type: docs
weight: 100
url: /it/net/annotations/invisibleannotation/
---

Le annotazioni nei documenti PDF sono una potente funzionalità che consente di aggiungere ulteriori informazioni o note a un documento senza modificare il contenuto effettivo. Possono essere utilizzati per evidenziare il testo, attirare l'attenzione su aree specifiche di un documento o aggiungere commenti o feedback.

Esistono molti tipi diversi di annotazioni che è possibile utilizzare nei documenti PDF, tra cui:

- Annotazioni di testo
- Collega annotazioni
- Annotazioni di francobolli
- Annotazioni sonore
- Annotazioni di file allegati
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

 Nel codice sopra, creiamo a`FreeTextAnnotation`oggetto e specificare la posizione dell'annotazione a pagina 2 del documento PDF. Specifichiamo anche il tipo di carattere, la dimensione e il colore per il testo che verrà visualizzato nell'annotazione.

## Passaggio 2: aggiunta di caratteristiche all'annotazione invisibile

Successivamente, possiamo aggiungere alcune caratteristiche all'annotazione, come un colore del bordo, un colore di sfondo o un'opacità.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Nel codice sopra, impostiamo il colore del bordo dell'annotazione su rosso.

## Passaggio 3: impostazione dei flag di annotazione

Dopo aver creato l'annotazione e impostato le sue caratteristiche, possiamo specificare i flag di annotazione. In questo tutorial, vogliamo che l'annotazione sia stampabile, ma non visualizzabile.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Passaggio 4: salvare il documento PDF modificato

Infine, possiamo salvare il documento PDF modificato con la nuova annotazione invisibile.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Codice sorgente di esempio per come annotare invisibile utilizzando Aspose.PDF per .NET

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