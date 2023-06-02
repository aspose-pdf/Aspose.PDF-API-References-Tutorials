---
title: Aggiungi annotazione
linktitle: Aggiungi annotazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere annotazioni di testo con Aspose.PDF per .NET utilizzando questo codice sorgente C#. Personalizza le tue annotazioni con dettagli e icone specifici.
type: docs
weight: 10
url: /it/net/annotations/addannotation/
---

L'aggiunta di annotazioni ai documenti PDF è una potente funzionalità che può migliorare i processi di collaborazione e revisione. Aspose.PDF per .NET semplifica l'aggiunta di annotazioni a livello di codice ai documenti PDF utilizzando C#. In questa guida, spiegheremo passo dopo passo come utilizzare Aspose.PDF per .NET per aggiungere annotazioni a un documento PDF.

## Passaggio 1: creare un nuovo progetto e installare Aspose.PDF per .NET

Prima di iniziare a scrivere il codice per l'aggiunta di annotazioni, è necessario creare un nuovo progetto e installare Aspose.PDF per .NET. Per installare Aspose.PDF per .NET, attenersi alla seguente procedura:

1. Apri Visual Studio e crea un nuovo progetto C#.
2. Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e selezionare "Gestisci pacchetti NuGet".
3. Cerca "Aspose.PDF" e seleziona "Installa".

Una volta completata l'installazione, possiamo iniziare a scrivere il codice.

## Passaggio 2: apri il documento PDF

Il primo passo per aggiungere annotazioni è aprire il documento PDF. Possiamo usare il seguente codice per aprire il documento:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

In questo codice specifichiamo il percorso del documento PDF che vogliamo aprire. Assicurati di sostituire "LA TUA DIRECTORY DEI DATI" con il percorso effettivo della tua directory dei dati.

## Passaggio 3: creare l'annotazione

 Per aggiungere un'annotazione, dobbiamo creare una nuova istanza del file`TextAnnotation` classe. Possiamo utilizzare il seguente codice per creare una nuova annotazione di testo:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

In questo codice creiamo una nuova annotazione di testo nella seconda pagina del documento PDF. Impostiamo anche le proprietà titolo, oggetto, stato, contenuto, apertura e icona dell'annotazione.

## Passaggio 4: personalizzare l'annotazione

 Possiamo personalizzare l'aspetto dell'annotazione utilizzando il file`Border` classe. Possiamo utilizzare il seguente codice per personalizzare il bordo dell'annotazione:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 In questo codice, creiamo un nuovo`Border` oggetto e impostarne le proprietà di larghezza e trattino. Impostiamo quindi il`Border` proprietà dell'annotazione al nuovo`Border`oggetto. Infine, impostiamo il`Rect` proprietà dell'annotazione per specificarne la posizione e le dimensioni.

## Passaggio 5: aggiungere l'annotazione al documento PDF

Dopo aver creato e personalizzato l'annotazione, dobbiamo aggiungerla al documento PDF. Possiamo utilizzare il seguente codice per aggiungere l'annotazione al documento PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

In questo codice, aggiungiamo l'annotazione alla raccolta di annotazioni della seconda pagina del documento PDF.

## Passaggio 6: salvare il file di output

Infine, dobbiamo salvare il documento PDF con l'annotazione aggiunta. Possiamo usare il seguente codice per salvare il file di output:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Codice sorgente di esempio per l'aggiunta di annotazioni utilizzando Aspose.PDF per .NET


```csharp   
 // Il percorso della directory dei documenti.
string dataDir = "YOUR DATA DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Crea annotazione
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Aggiungi annotazione nella raccolta di annotazioni della pagina
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Salva il file di output
pdfDocument.Save(dataDir);
```
Questo codice mostra come aggiungere un'annotazione di testo con titolo, oggetto, stato, contenuto e icona specifici a una pagina PDF utilizzando Aspose.PDF per .NET. È possibile modificare questo codice in base alle proprie esigenze per l'aggiunta di annotazioni ai documenti PDF. Ricorda solo di sostituire LA TUA DIRECTORY DEI DATI con il percorso effettivo della directory in cui si trova il tuo file PDF e dove vuoi salvare il file di output.