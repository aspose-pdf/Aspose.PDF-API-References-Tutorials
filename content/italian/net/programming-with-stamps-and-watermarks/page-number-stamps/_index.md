---
title: Timbri del numero di pagina nel file PDF
linktitle: Timbri del numero di pagina nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere timbri del numero di pagina nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere timbri del numero di pagina nel file PDF utilizzando Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per aprire un documento PDF esistente, creare un timbro del numero di pagina, impostarne le proprietà e aggiungerlo a una pagina specifica nel file PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: caricamento del documento PDF esistente

Il primo passo è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF esistente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione e configurazione del timbro di numerazione delle pagine

Ora che il documento PDF è caricato, possiamo creare un buffer di numerazione delle pagine e configurarlo in base alle nostre esigenze. Ecco come:

```csharp
// Crea un buffer del numero di pagina
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definisce se il buffer è in background o meno
pageNumberStamp.Background = false;

// Formato del buffer di numerazione delle pagine
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margine inferiore del buffer di numerazione delle pagine
pageNumberStamp.BottomMargin = 10;

// Allineamento orizzontale del buffer di numerazione delle pagine
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Numero iniziale della numerazione delle pagine
pageNumberStamp.StartingNumber = 1;

// Imposta le proprietà del testo del buffer del numero di pagina
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Il codice precedente crea un timbro del numero di pagina con proprietà come formato del numero di pagina, margine inferiore, allineamento orizzontale, numero iniziale e proprietà del testo.

## Passaggio 4: aggiunta del timbro del numero di pagina a una pagina specifica

Una volta configurato il timbro del numero di pagina, possiamo aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi il buffer del numero di pagina a una pagina specifica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Il codice sopra aggiunge il timbro del numero di pagina alla prima pagina del documento PDF. È possibile modificare il numero di pagina secondo necessità.

## Passaggio 5: salvataggio del documento PDF modificato

Una volta aggiunto il timbro del numero di pagina al documento PDF, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento PDF modificato
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF modificato.

### Codice sorgente di esempio per i timbri dei numeri di pagina utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Crea timbro del numero di pagina
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Se il timbro è lo sfondo
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Imposta le proprietà del testo
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Aggiungi timbro a una pagina particolare
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere timbri del numero di pagina a un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi personalizzare i tuoi documenti PDF aggiungendo numeri di pagina chiari e informativi.

### Domande frequenti sui timbri dei numeri di pagina nel file PDF

#### D: Cos'è il timbro del numero di pagina e come viene utilizzato per aggiungere i numeri di pagina a un file PDF?

R: Un timbro del numero di pagina è una funzionalità di Aspose.PDF che consente di aggiungere numeri di pagina dinamici a pagine specifiche di un documento PDF. In questo tutorial, si ottiene creando un oggetto PageNumberStamp, configurandone le proprietà e aggiungendolo a una pagina designata.

#### D: In che modo il codice sorgente C# fornito consente di aggiungere timbri del numero di pagina a un file PDF?

R: Il codice mostra come caricare un documento PDF esistente, creare un PageNumberStamp, impostare varie proprietà (come formato, carattere, allineamento, ecc.) e quindi aggiungere il timbro a una pagina specifica. Il timbro calcola automaticamente il conteggio totale delle pagine e inserisce i numeri di pagina corretti.

#### D: Posso personalizzare l'aspetto del numero di pagina, ad esempio stile, colore e dimensione del carattere?

R: Assolutamente, puoi personalizzare l'aspetto del timbro del numero di pagina regolando proprietà come carattere, dimensione del carattere, stile del carattere (grassetto, corsivo, ecc.) e colore del testo.

#### D: È possibile aggiungere timbri del numero di pagina a più pagine all'interno di un documento PDF?

R: Sì, puoi aggiungere timbri dei numeri di pagina a più pagine creando più oggetti PageNumberStamp e aggiungendo ciascuno di essi alle pagine desiderate.

#### D: Posso scegliere se il timbro del numero di pagina viene visualizzato come parte del contenuto della pagina o come elemento di sfondo?

 R: Sì, puoi controllare se il timbro del numero di pagina appare come parte del contenuto della pagina o come elemento di sfondo impostando l'opzione`Background` proprietà di PageNumberStamp.

#### D: Come posso specificare il formato del numero di pagina, incluso il conteggio totale delle pagine?

 R: Il codice utilizza il file`Format`proprietà di PageNumberStamp per specificare il formato del numero di pagina. La macro "# di" viene utilizzata per rappresentare il conteggio totale delle pagine.

#### D: Cosa succede se aggiungo lo stesso timbro con il numero di pagina a più pagine?

R: Aggiungendo la stessa istanza PageNumberStamp a più pagine verranno visualizzati i numeri di pagina corretti per ciascuna pagina. Il timbro regola automaticamente il numero di pagina e il conteggio totale delle pagine.

#### D: Posso aggiungere timbri del numero di pagina alle sezioni di intestazione o piè di pagina di un documento PDF?

R: Sebbene i PageNumberStamps vengano generalmente aggiunti direttamente al contenuto della pagina, puoi utilizzare FloatingBox o altre tecniche per posizionarli nelle sezioni di intestazione o piè di pagina.

#### D: Come posso specificare la posizione del timbro del numero di pagina sulla pagina?

 R: Il`BottomMargin` E`HorizontalAlignment` le proprietà di PageNumberStamp consentono di controllare la posizione del timbro all'interno della pagina.

#### D: Cosa succede se voglio iniziare la numerazione delle pagine da un numero diverso da 1?

 R: Puoi impostare il`StartingNumber`proprietà di PageNumberStamp per specificare il numero di pagina iniziale.