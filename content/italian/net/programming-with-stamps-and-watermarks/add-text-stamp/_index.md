---
title: Aggiungi timbro di testo nel file PDF
linktitle: Aggiungi timbro di testo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere facilmente un timbro di testo nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere un timbro di testo nel file PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere un timbro di testo personalizzato a una pagina specifica del file PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passo è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione del buffer di testo

Ora che hai caricato il documento PDF, puoi creare il timbro di testo da aggiungere. Ecco come farlo:

```csharp
// Crea il buffer di testo
TextStamp textStamp = new TextStamp("Example Stamp");
```

Il codice sopra crea un nuovo buffer di testo contenente il testo specificato.

## Passaggio 4: configurazione delle proprietà del timbro di testo

Prima di aggiungere il timbro di testo al documento PDF, puoi configurare varie proprietà del timbro, come sfondo, posizione, rotazione, carattere, dimensione, ecc. Ecco come:

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

Puoi modificare queste proprietà in base alle tue esigenze.

## Passaggio 5: aggiungi il timbro testo al PDF

Ora che il timbro di testo è pronto, puoi aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
//Aggiungi buffer di testo a una pagina specifica
pdfDocument.Pages[1].AddStamp(textStamp);
```

Il codice sopra aggiunge il timbro di testo alla prima pagina del documento PDF. Se necessario, è possibile specificare un'altra pagina.

## Passaggio 6: salvare il documento di output

Dopo aver aggiunto il timbro di testo, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento di output
pdfDocument.Save(dataDir);
```

Il codice sopra salva il documento PDF modificato nella directory specificata.

### Codice sorgente di esempio per Aggiungi timbro testo utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Crea timbro di testo
TextStamp textStamp = new TextStamp("Sample Stamp");

// Imposta se il timbro deve essere utilizzato come sfondo
textStamp.Background = true;

// Imposta l'origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Ruota il timbro
textStamp.Rotate = Rotation.on90;

// Imposta le proprietà del testo
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Aggiungi timbro a una pagina particolare
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere un timbro di testo utilizzando Aspose.PDF per .NET. Ora puoi applicare queste conoscenze ai tuoi progetti per aggiungere timbri di testo personalizzati ai documenti PDF.

### Domande frequenti sull'aggiunta di un timbro di testo nel file PDF

#### D: Qual è lo scopo di aggiungere un timbro di testo in un file PDF utilizzando Aspose.PDF per .NET?

R: L'aggiunta di un timbro di testo consente di inserire testo personalizzato su una pagina specifica di un documento PDF. Questa funzionalità è utile per aggiungere etichette, commenti, filigrane o qualsiasi altra informazione testuale per migliorare il contenuto del documento e fornire contesto aggiuntivo.

#### D: Posso personalizzare l'aspetto del timbro di testo, ad esempio carattere, dimensione, colore e rotazione?

 R: Sì, puoi personalizzare completamente l'aspetto del timbro di testo. Il codice sorgente C# fornito dimostra come impostare varie proprietà di`TextStamp` oggetto, inclusi carattere, dimensione del carattere, stile del carattere, colore del testo, colore dello sfondo e rotazione.

#### D: È possibile aggiungere più timbri di testo a pagine diverse dello stesso documento PDF?

R: Assolutamente sì, puoi aggiungere più timbri di testo a pagine diverse dello stesso documento PDF. Il codice fornito nel tutorial consente di specificare la pagina di destinazione per l'aggiunta del timbro di testo, rendendolo versatile per le diverse pagine del documento.

#### D: Come posso specificare la posizione del timbro di testo all'interno del documento PDF?

 R: È possibile personalizzare la posizione del timbro testo modificando il`XIndent` E`YIndent` proprietà del`TextStamp` oggetto. Queste proprietà definiscono le coordinate dell'angolo superiore sinistro del timbro rispetto all'origine della pagina.

#### D: Posso applicare questo metodo ai documenti PDF esistenti per aggiungere timbri di testo?

R: Sì, puoi applicare questo metodo ai documenti PDF esistenti per aggiungere timbri di testo. Il codice fornito nel tutorial mostra come caricare un documento PDF esistente e aggiungere un timbro di testo a una pagina specifica.

#### D: Posso aggiungere sia i colori di sfondo che quelli di primo piano al timbro di testo?

 R: Sì, puoi aggiungere sia i colori di sfondo che quelli di primo piano al timbro di testo. Impostando il`Background` proprietà a`true` , è possibile fornire uno sfondo colorato per il timbro del testo. Inoltre, puoi impostare il file`TextState.ForegroundColor` proprietà per specificare il colore del testo stesso.

#### D: Come posso garantire che il timbro del testo non oscuri il contenuto sottostante del documento PDF?

 R: Quando aggiungi un timbro di testo, fai attenzione alla sua posizione per assicurarti che non ostruisca informazioni critiche o influenzi negativamente la leggibilità del documento. Puoi regolare il`XIndent` E`YIndent` proprietà per posizionare il timbro di testo in modo appropriato.

#### D: Posso utilizzare questo metodo per aggiungere timbri diversi dal testo, come immagini o loghi?

R: Questo tutorial specifico si concentra sull'aggiunta di timbri di testo, ma puoi allo stesso modo aggiungere altri tipi di timbri, come immagini o loghi, utilizzando Aspose.PDF per .NET. Il processo prevede la creazione dell'oggetto timbro appropriato e la configurazione delle sue proprietà.

#### D: Come posso automatizzare il processo di aggiunta di timbri di testo a più documenti PDF?

R: È possibile automatizzare il processo di aggiunta di timbri di testo a più documenti PDF creando uno script o un programma che scorre un elenco di documenti e applica lo stesso processo di timbratura di testo a ciascuno di essi.