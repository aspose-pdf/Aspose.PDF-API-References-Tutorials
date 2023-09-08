---
title: Aggiungi annotazione PDF
linktitle: Aggiungi annotazione
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere annotazioni PDF di testo con Aspose.PDF per .NET utilizzando questo codice sorgente C#. Personalizza le tue annotazioni con dettagli e icone specifici.
type: docs
weight: 10
url: /it/net/annotations/addannotation/
---
L'aggiunta di annotazioni ai documenti PDF è una funzionalità potente che può migliorare i processi di collaborazione e revisione. Aspose.PDF per .NET semplifica l'aggiunta di annotazioni a livello di codice ai documenti PDF utilizzando C#. In questa guida spiegheremo passo dopo passo come utilizzare Aspose.PDF per .NET per aggiungere annotazioni a un documento PDF.

## Passaggio 1: crea un nuovo progetto e installa Aspose.PDF per .NET

Prima di iniziare a scrivere il codice per aggiungere annotazioni, dobbiamo creare un nuovo progetto e installare Aspose.PDF per .NET. Per installare Aspose.PDF per .NET, attenersi alla seguente procedura:

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

In questo codice specifichiamo il percorso del documento PDF che vogliamo aprire. Assicurati di sostituire "LA TUA DIRECTORY DATI" con il percorso effettivo della directory dei dati.

## Passaggio 3: crea l'annotazione

 Per aggiungere un'annotazione, dobbiamo creare una nuova istanza del file`TextAnnotation` classe. Possiamo usare il seguente codice per creare una nuova annotazione di testo:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

In questo codice creiamo una nuova annotazione di testo sulla seconda pagina del documento PDF. Impostiamo anche le proprietà titolo, oggetto, stato, contenuto, apertura e icona dell'annotazione.

## Passaggio 4: personalizzare l'annotazione

 Possiamo personalizzare l'aspetto dell'annotazione utilizzando il comando`Border` classe. Possiamo utilizzare il seguente codice per personalizzare il bordo dell'annotazione:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 In questo codice creiamo un nuovo file`Border`oggetto e impostarne le proprietà larghezza e trattino. Impostiamo quindi il`Border` proprietà dell'annotazione al nuovo`Border` oggetto. Infine impostiamo il`Rect` proprietà dell'annotazione per specificarne la posizione e la dimensione.

## Passaggio 5: aggiungi l'annotazione al documento PDF

Una volta creata e personalizzata l'annotazione, dobbiamo aggiungerla al documento PDF. Possiamo utilizzare il seguente codice per aggiungere l'annotazione al documento PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

In questo codice aggiungiamo l'annotazione alla raccolta di annotazioni della seconda pagina del documento PDF.

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
Questo codice dimostra come aggiungere un'annotazione di testo con titolo, oggetto, stato, contenuto e icona specifici a una pagina PDF utilizzando Aspose.PDF per .NET. Puoi modificare questo codice in base alle tue esigenze per aggiungere annotazioni ai tuoi documenti PDF. Ricorda solo di sostituire la TUA DIRECTORY DATI con il percorso effettivo della directory in cui si trova il tuo file PDF e dove desideri salvare il file di output.

## Conclusione

L'aggiunta di annotazioni ai documenti PDF utilizzando Aspose.PDF per .NET offre uno strumento prezioso per migliorare la collaborazione dei documenti e i processi di revisione. Seguendo la guida dettagliata fornita in questo articolo, gli sviluppatori possono integrare perfettamente le funzionalità di annotazione nelle proprie applicazioni C#.

### Domande frequenti

#### D: Quali tipi di annotazioni possono essere aggiunti utilizzando Aspose.PDF per .NET?

R: Aspose.PDF per .NET supporta vari tipi di annotazioni, incluse annotazioni di testo, timbri, collegamenti, forme e altro. Gli sviluppatori possono personalizzare l'aspetto e le proprietà di queste annotazioni in base alle proprie esigenze specifiche.

#### D: Posso aggiungere annotazioni a pagine specifiche in un documento PDF multipagina?

R: Sì, Aspose.PDF per .NET ti consente di specificare la pagina in cui desideri aggiungere l'annotazione. Puoi scegliere una pagina specifica o aggiungere annotazioni a più pagine secondo necessità.

#### D: Come posso personalizzare l'aspetto delle annotazioni?

R: Le annotazioni possono essere personalizzate utilizzando proprietà come larghezza del bordo, colore, stile del trattino, stile del testo e altro. Aspose.PDF per .NET fornisce un ricco set di opzioni per personalizzare l'aspetto delle annotazioni.

#### D: È possibile aggiungere collegamenti ipertestuali come annotazioni utilizzando Aspose.PDF per .NET?

R: Sì, puoi aggiungere collegamenti ipertestuali come annotazioni ai documenti PDF utilizzando Aspose.PDF per .NET. Le annotazioni dei collegamenti ipertestuali possono essere utilizzate per collegarsi a URL esterni o posizioni specifiche all'interno dello stesso documento.

#### D: È possibile aggiungere annotazioni ai documenti PDF esistenti senza alterare il contenuto originale?

R: Sì, Aspose.PDF per .NET aggiunge annotazioni come elementi aggiuntivi senza alterare il contenuto originale del documento PDF. Il contenuto PDF originale rimane intatto.