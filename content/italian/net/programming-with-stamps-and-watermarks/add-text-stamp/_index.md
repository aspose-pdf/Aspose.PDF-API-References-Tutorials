---
title: Aggiungi timbro di testo nel file PDF
linktitle: Aggiungi timbro di testo nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere facilmente un timbro di testo in un file PDF con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un timbro di testo in un file PDF usando Aspose.PDF per .NET. Ti mostreremo come usare il codice sorgente C# fornito per aggiungere un timbro di testo personalizzato a una pagina specifica del file PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passo è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assicurati di sostituire "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Fase 3: Creazione del buffer di testo

Ora che hai caricato il documento PDF, puoi creare il timbro di testo da aggiungere. Ecco come fare:

```csharp
// Crea il buffer di testo
TextStamp textStamp = new TextStamp("Example Stamp");
```

Il codice sopra crea un nuovo buffer di testo contenente il testo specificato.

## Passaggio 4: Configurazione delle proprietà del timbro di testo

Prima di aggiungere il timbro di testo al documento PDF, è possibile configurare varie proprietà del timbro, come sfondo, posizione, rotazione, carattere, dimensione, ecc. Ecco come fare:

```csharp
// Configurare le proprietà del buffer di testo
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

È possibile adattare queste proprietà in base alle proprie esigenze.

## Passaggio 5: aggiungere il timbro di testo al PDF

Ora che il timbro di testo è pronto, puoi aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
//Aggiungi buffer di testo a una pagina specifica
pdfDocument.Pages[1].AddStamp(textStamp);
```

Il codice sopra aggiunge il timbro di testo alla prima pagina del documento PDF. Puoi specificare un'altra pagina se necessario.

## Passaggio 6: Salvare il documento di output

Una volta aggiunto il timbro di testo, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento di output
pdfDocument.Save(dataDir);
```

Il codice soprastante salva il documento PDF modificato nella directory specificata.

### Esempio di codice sorgente per Add Text Stamp utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crea timbro di testo
TextStamp textStamp = new TextStamp("Sample Stamp");

// Imposta se il timbro è uno sfondo
textStamp.Background = true;

// Imposta origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Ruota timbro
textStamp.Rotate = Rotation.on90;

// Imposta le proprietà del testo
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Aggiungi timbro a una pagina specifica
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un timbro di testo usando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per aggiungere timbri di testo personalizzati ai documenti PDF.

### Domande frequenti per aggiungere un timbro di testo nel file PDF

#### D: Qual è lo scopo di aggiungere un timbro di testo in un file PDF utilizzando Aspose.PDF per .NET?

R: Aggiungere un timbro di testo consente di posizionare testo personalizzato su una pagina specifica di un documento PDF. Questa funzionalità è utile per aggiungere etichette, commenti, filigrane o qualsiasi altra informazione testuale per migliorare il contenuto del documento e fornire contesto aggiuntivo.

#### D: Posso personalizzare l'aspetto del timbro di testo, ad esempio il carattere, la dimensione, il colore e la rotazione?

 A: Sì, puoi personalizzare completamente l'aspetto del timbro di testo. Il codice sorgente C# fornito dimostra come impostare varie proprietà del`TextStamp` oggetto, inclusi carattere, dimensione del carattere, stile del carattere, colore del testo, colore di sfondo e rotazione.

#### D: È possibile aggiungere più timbri di testo a pagine diverse dello stesso documento PDF?

R: Assolutamente, puoi aggiungere più timbri di testo a pagine diverse dello stesso documento PDF. Il codice fornito dal tutorial ti consente di specificare la pagina di destinazione per l'aggiunta del timbro di testo, rendendolo versatile per pagine diverse all'interno del documento.

#### D: Come faccio a specificare la posizione del timbro di testo all'interno del documento PDF?

 A: È possibile personalizzare la posizione del timbro di testo modificando il`XIndent` E`YIndent` proprietà del`TextStamp` oggetto. Queste proprietà definiscono le coordinate dell'angolo superiore sinistro del timbro rispetto all'origine della pagina.

#### D: Posso applicare questo metodo ai documenti PDF esistenti per aggiungere timbri di testo?

R: Sì, puoi applicare questo metodo ai documenti PDF esistenti per aggiungere timbri di testo. Il codice fornito dal tutorial dimostra come caricare un documento PDF esistente e aggiungere un timbro di testo a una pagina specifica.

#### D: Posso aggiungere sia colori di sfondo che di primo piano al timbro di testo?

 R: Sì, puoi aggiungere sia i colori di sfondo che quelli di primo piano al timbro di testo. Impostando`Background` proprietà a`true` , puoi fornire uno sfondo colorato per il timbro di testo. Inoltre, puoi impostare il`TextState.ForegroundColor` proprietà per specificare il colore del testo stesso.

#### D: Come posso assicurarmi che il timbro di testo non nasconda il contenuto sottostante del documento PDF?

R: Quando aggiungi un timbro di testo, fai attenzione al suo posizionamento per assicurarti che non ostruisca informazioni critiche o influisca negativamente sulla leggibilità del documento. Puoi regolare il`XIndent` E`YIndent` proprietà per posizionare opportunamente il timbro di testo.

#### D: Posso usare questo metodo per aggiungere timbri diversi dal testo, come immagini o loghi?

R: Questo tutorial specifico si concentra sull'aggiunta di timbri di testo, ma puoi aggiungere in modo simile altri tipi di timbri, come immagini o loghi, utilizzando Aspose.PDF per .NET. Il processo prevede la creazione dell'oggetto timbro appropriato e la configurazione delle sue proprietà.

#### D: Come posso automatizzare il processo di aggiunta di timbri di testo a più documenti PDF?

R: È possibile automatizzare il processo di aggiunta di timbri di testo a più documenti PDF creando uno script o un programma che scorre un elenco di documenti e applica lo stesso processo di timbratura di testo a ciascuno di essi.