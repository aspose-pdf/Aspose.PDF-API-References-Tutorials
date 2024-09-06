---
title: Aggiungi data e ora nel file PDF
linktitle: Aggiungi data e ora nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere facilmente data e ora in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 10
url: /it/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In questo articolo, ti guideremo passo dopo passo su come aggiungere un timbro di data e ora in un file PDF usando Aspose.PDF per .NET. Ti mostreremo come usare il codice sorgente C# fornito per aggiungere un timbro di data e ora a un file PDF esistente.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Fase 1: Impostazione dell'ambiente

Prima di poter aggiungere un timbro data e ora a un documento PDF, devi impostare il tuo ambiente di sviluppo. Ecco i passaggi da seguire:

1. Apri il tuo IDE (Integrated Development Environment) preferito.
2. Crea un nuovo progetto C#.
3. Assicurati di aver aggiunto un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: aggiunta della libreria Aspose.PDF

Per lavorare con i documenti PDF nel tuo progetto è necessaria la libreria Aspose.PDF per .NET.

## Passaggio 3: caricamento del documento PDF

Il primo passo per aggiungere un timbro data e ora è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assicurati di sostituire "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Fase 4: Creazione del timbro data e ora

Ora che hai caricato il documento

  PDF, puoi creare il timbro data e ora da aggiungere. Ecco come fare:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Crea un buffer di testo
TextStamp textStamp = new TextStamp(annotationText);
```

Il codice sopra crea un nuovo buffer di testo contenente la data e l'ora correnti.

## Passaggio 5: Configurazione delle proprietà del timbro

Prima di aggiungere il timbro al documento PDF, è possibile configurare varie proprietà del timbro, come margine, allineamento orizzontale e verticale, ecc. Ecco come fare:

```csharp
// Imposta le proprietà del buffer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

È possibile adattare queste proprietà in base alle proprie esigenze.

## Passaggio 6: Aggiungi timbro al PDF

Ora che la data e l'ora sono pronte, puoi aggiungerle a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi il timbro alla collezione di timbri della pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

Il codice sopra aggiunge il timbro alla prima pagina del documento PDF. Puoi specificare un'altra pagina se necessario.

## Passaggio 7: Salvare il documento di output

Una volta aggiunti la data e l'ora, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento di output
pdfDocument.Save(dataDir);
```

Il codice soprastante salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per aggiungere data e ora utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
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

// Aggiungere un francobollo alla collezione di francobolli
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

Congratulazioni! Hai imparato come aggiungere un timbro di data e ora usando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per aggiungere timbri di data e ora ai documenti PDF.

### Domande frequenti per aggiungere data e ora nel file PDF

#### D: Qual è lo scopo di aggiungere un timbro di data e ora a un documento PDF utilizzando Aspose.PDF per .NET?

R: Aggiungere un timbro data e ora a un documento PDF ne aumenta il valore informativo indicando quando il documento è stato modificato o creato. Questa funzionalità è utile per tenere traccia delle modifiche al documento e fornire un punto di riferimento per la cronologia del documento.

#### D: Posso personalizzare il formato della data e dell'ora per soddisfare esigenze specifiche?

 A: Sì, puoi personalizzare il formato della data e dell'ora in base alle tue preferenze. Il codice sorgente C# fornito utilizza il`DateTime.Now.ToString()` metodo per generare il timestamp in un formato specifico. Puoi modificare questo codice per formattare il timestamp come necessario.

#### D: È possibile aggiungere la data e l'ora in una posizione specifica su una pagina PDF?

 A: Assolutamente, puoi modificare la posizione della data e dell'ora sulla pagina PDF modificando le proprietà del`TextStamp` oggetto. Il codice fornito nel tutorial dimostra come impostare proprietà quali margine, allineamento e posizionamento verticale.

#### D: Posso aggiungere più timbri di data e ora a pagine diverse dello stesso documento PDF?

 R: Sì, puoi aggiungere più timbri data e ora a pagine diverse dello stesso documento PDF. Ripeti semplicemente il processo di creazione di un`TextStamp` oggetto e configurandone le proprietà per ogni pagina desiderata.

#### D: Come posso modificare il carattere, la dimensione o il colore del testo della data e dell'ora?

 A: Per modificare il carattere, la dimensione o il colore del testo del timbro data e ora, è possibile personalizzare le proprietà del`DefaultAppearance` oggetto utilizzato per creare il`TextStamp`Regola il nome del font, la dimensione e i valori del colore per ottenere l'aspetto desiderato.

#### D: È possibile aggiungere altri tipi di annotazioni o timbri a un documento PDF utilizzando Aspose.PDF per .NET?

R: Sì, Aspose.PDF per .NET fornisce un'ampia gamma di tipi di annotazione che puoi aggiungere ai documenti PDF, tra cui annotazioni di testo, timbri, linee, forme e altro. Puoi esplorare la documentazione di Aspose.PDF per ulteriori dettagli su come lavorare con le annotazioni.

#### D: Ci sono limitazioni o considerazioni da fare quando si aggiunge un timbro di data e ora a un documento PDF?

R: Sebbene aggiungere un timbro data e ora sia semplice, considera fattori come il layout del documento e il contenuto esistente. Assicurati che il posizionamento del timbro non nasconda informazioni importanti o non influisca sulla leggibilità del documento.

#### D: Come posso integrare questo metodo nei miei progetti per aggiungere data e ora ai documenti PDF?

R: Per integrare questo metodo, segui i passaggi forniti e adatta il codice per adattarlo alla struttura del tuo progetto. Puoi aggiungere data e ora ai documenti PDF esistenti per migliorarne l'utilità e fornire una cronologia chiara delle modifiche.

#### D: Posso automatizzare il processo di aggiunta di data e ora a più documenti PDF?

R: Sì, è possibile automatizzare il processo di aggiunta di data e ora a più documenti PDF creando uno script o un programma che scorre un elenco di documenti e applica lo stesso processo di timbratura a ciascuno di essi.