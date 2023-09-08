---
title: Aggiungi data e ora nel file PDF
linktitle: Aggiungi data e ora nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere facilmente un timbro di data e ora nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In questo articolo, ti guideremo passo dopo passo su come aggiungere un timbro di data e ora nel file PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere una data e un'ora a un file PDF esistente.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e a cui si fa riferimento nel progetto.

## Passaggio 1: configurazione dell'ambiente

Prima di poter aggiungere data e ora a un documento PDF, è necessario configurare l'ambiente di sviluppo. Ecco i passaggi da seguire:

1. Apri il tuo IDE preferito (ambiente di sviluppo integrato).
2. Creare un nuovo progetto C#.
3. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: aggiunta della libreria Aspose.PDF

La libreria Aspose.PDF per .NET è necessaria per lavorare con i documenti PDF nel tuo progetto.

## Passaggio 3: caricamento del documento PDF

Il primo passo per aggiungere un timbro con data e ora è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 4: creazione del timbro di data e ora

Ora che hai caricato il documento

  PDF, è possibile creare la data e l'ora da aggiungere. Ecco come farlo:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Crea un buffer di testo
TextStamp textStamp = new TextStamp(annotationText);
```

Il codice sopra crea un nuovo buffer di testo contenente la data e l'ora correnti.

## Passaggio 5: configurazione delle proprietà del timbro

Prima di aggiungere il timbro al documento PDF, puoi configurare varie proprietà del timbro, come margine, allineamento orizzontale e verticale, ecc. Ecco come:

```csharp
// Imposta le proprietà del buffer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Puoi modificare queste proprietà in base alle tue esigenze.

## Passaggio 6: aggiungi timbro al PDF

Ora che la data e l'ora sono pronte, puoi aggiungerle a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi il francobollo alla collezione di francobolli della pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

Il codice sopra aggiunge il timbro alla prima pagina del documento PDF. Se necessario, è possibile specificare un'altra pagina.

## Passaggio 7: salvare il documento di output

Dopo aver aggiunto la data e l'ora, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento di output
pdfDocument.Save(dataDir);
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Codice sorgente di esempio per Aggiungi data e ora utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Crea timbro di testo
TextStamp textStamp = new TextStamp(annotationText);

// Imposta le proprietà del timbro
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Aggiunta di francobolli alla collezione di francobolli
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un timbro di data e ora utilizzando Aspose.PDF per .NET. Ora puoi applicare queste conoscenze ai tuoi progetti per aggiungere data e ora ai documenti PDF.

### Domande frequenti sull'aggiunta del timestamp della data nel file PDF

#### D: Qual è lo scopo di aggiungere un timbro di data e ora a un documento PDF utilizzando Aspose.PDF per .NET?

R: L'aggiunta di data e ora a un documento PDF ne aumenta il valore informativo indicando quando il documento è stato modificato o creato. Questa funzionalità è utile per tenere traccia delle modifiche al documento e fornire un punto di riferimento per la cronologia del documento.

#### D: Posso personalizzare il formato della data e dell'ora per soddisfare requisiti specifici?

 R: Sì, puoi personalizzare il formato della data e dell'ora in base alle tue preferenze. Il codice sorgente C# fornito utilizza il file`DateTime.Now.ToString()` metodo per generare il timestamp in un formato specifico. È possibile modificare questo codice per formattare il timestamp secondo necessità.

#### D: È possibile aggiungere la data e l'ora in una posizione specifica su una pagina PDF?

 R: Assolutamente sì, puoi regolare la posizione della data e dell'ora sulla pagina PDF modificando le proprietà del file`TextStamp` oggetto. Il codice fornito nell'esercitazione illustra come impostare proprietà quali margine, allineamento e posizionamento verticale.

#### D: Posso aggiungere più timbri di data e ora a pagine diverse dello stesso documento PDF?

 R: Sì, puoi aggiungere più timbri di data e ora a pagine diverse dello stesso documento PDF. Ripeti semplicemente il processo di creazione di un file`TextStamp` oggetto e configurandone le proprietà per ogni pagina desiderata.

#### D: Come posso modificare il carattere, la dimensione o il colore del testo della data e dell'ora?

 R: Per modificare il carattere, la dimensione o il colore del testo della data e dell'ora, è possibile personalizzare le proprietà del file`DefaultAppearance` oggetto utilizzato per creare il`TextStamp`. Regola il nome, la dimensione e i valori del colore del carattere per ottenere l'aspetto desiderato.

#### D: È possibile aggiungere altri tipi di annotazioni o timbri a un documento PDF utilizzando Aspose.PDF per .NET?

R: Sì, Aspose.PDF per .NET fornisce un'ampia gamma di tipi di annotazioni che puoi aggiungere ai documenti PDF, incluse annotazioni di testo, timbri, linee, forme e altro. È possibile esplorare la documentazione Aspose.PDF per ulteriori dettagli sull'utilizzo delle annotazioni.

#### D: Esistono limitazioni o considerazioni quando si aggiunge la data e l'ora a un documento PDF?

R: Anche se aggiungere data e ora è semplice, considera fattori come il layout del documento e il contenuto esistente. Assicurati che il posizionamento del timbro non oscuri informazioni importanti o influenzi la leggibilità del documento.

#### D: Come posso integrare questo metodo nei miei progetti per aggiungere data e ora ai documenti PDF?

R: Per integrare questo metodo, segui i passaggi forniti e modifica il codice per adattarlo alla struttura del tuo progetto. Puoi aggiungere data e ora ai documenti PDF esistenti per migliorarne l'utilità e fornire una chiara sequenza temporale delle modifiche.

#### D: Posso automatizzare il processo di aggiunta di data e ora a più documenti PDF?

R: Sì, puoi automatizzare il processo di aggiunta di data e ora a più documenti PDF creando uno script o un programma che scorre un elenco di documenti e applica lo stesso processo di timbratura a ciascuno di essi.