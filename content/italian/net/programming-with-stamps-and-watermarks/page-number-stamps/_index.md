---
title: Timbri numerici di pagina nel file PDF
linktitle: Timbri numerici di pagina nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere timbri con i numeri di pagina nei file PDF con Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere timbri di numeri di pagina in un file PDF usando Aspose.PDF per .NET. Utilizzeremo il codice sorgente C# fornito per aprire un documento PDF esistente, creare un timbro di numeri di pagina, impostarne le proprietà e aggiungerlo a una pagina specifica nel file PDF.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: caricamento del documento PDF esistente

Il primo passo è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Aprire il documento PDF esistente
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Assicurati di sostituire "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Fase 3: Creazione e configurazione del timbro di numerazione delle pagine

Ora che il documento PDF è caricato, possiamo creare un buffer di numerazione delle pagine e configurarlo in base alle nostre esigenze. Ecco come:

```csharp
// Crea un buffer per i numeri di pagina
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definisci se il buffer è in background o meno
pageNumberStamp.Background = false;

// Formato del buffer di numerazione delle pagine
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margine inferiore del buffer di numerazione delle pagine
pageNumberStamp.BottomMargin = 10;

// Allineamento orizzontale del buffer di numerazione delle pagine
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Numero di inizio della numerazione delle pagine
pageNumberStamp.StartingNumber = 1;

// Imposta le proprietà del testo del buffer del numero di pagina
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Il codice soprastante crea un timbro con il numero di pagina con proprietà quali formato del numero di pagina, margine inferiore, allineamento orizzontale, numero iniziale e proprietà del testo.

## Fase 4: Aggiunta del timbro del numero di pagina a una pagina specifica

Una volta configurato il timbro del numero di pagina, possiamo aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungere il buffer del numero di pagina a una pagina specifica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Il codice sopra aggiunge il timbro del numero di pagina alla prima pagina del documento PDF. Puoi modificare il numero di pagina come necessario.

## Passaggio 5: salvataggio del documento PDF modificato

Una volta aggiunto il timbro del numero di pagina al documento PDF, possiamo salvare il documento PDF modificato. Ecco come:

```csharp
// Salvare il documento PDF modificato
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della directory in cui desideri salvare il documento PDF modificato.

### Esempio di codice sorgente per timbri numerici di pagina utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Crea timbro numero pagina
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Se il timbro è di sfondo
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

// Aggiungi timbro a una pagina specifica
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Salva il documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere timbri di numeri di pagina a un documento PDF usando Aspose.PDF per .NET. Ora puoi personalizzare i tuoi documenti PDF aggiungendo numeri di pagina chiari e informativi.

### FAQ sui timbri dei numeri di pagina nei file PDF

#### D: Cos'è un timbro con numero di pagina e come si usa per aggiungere i numeri di pagina a un file PDF?

A: Un Page Number Stamp è una funzionalità di Aspose.PDF che consente di aggiungere numeri di pagina dinamici a pagine specifiche di un documento PDF. In questo tutorial, si ottiene creando un oggetto PageNumberStamp, configurandone le proprietà e aggiungendolo a una pagina designata.

#### D: In che modo il codice sorgente C# fornito riesce ad aggiungere timbri con i numeri di pagina a un file PDF?

R: Il codice dimostra come caricare un documento PDF esistente, creare un PageNumberStamp, impostare varie proprietà (come formato, font, allineamento, ecc.) e quindi aggiungere il timbro a una pagina specifica. Il timbro calcola automaticamente il conteggio totale delle pagine e inserisce i numeri di pagina corretti.

#### D: Posso personalizzare l'aspetto del numero di pagina, ad esempio lo stile, il colore e la dimensione del carattere?

R: Certamente, puoi personalizzare l'aspetto del timbro del numero di pagina modificando proprietà come il carattere, la dimensione del carattere, lo stile del carattere (grassetto, corsivo, ecc.) e il colore del testo.

#### D: È possibile aggiungere timbri con i numeri di pagina a più pagine di un documento PDF?

R: Sì, è possibile aggiungere timbri con i numeri di pagina a più pagine creando più oggetti PageNumberStamp e aggiungendo ciascuno di essi alle pagine desiderate.

#### D: Posso scegliere se il timbro del numero di pagina debba apparire come parte del contenuto della pagina o come elemento di sfondo?

 A: Sì, puoi controllare se il timbro del numero di pagina appare come parte del contenuto della pagina o come elemento di sfondo impostando`Background` proprietà del PageNumberStamp.

#### D: Come faccio a specificare il formato del numero di pagina, incluso il conteggio totale delle pagine?

 A: Il codice utilizza il`Format`proprietà di PageNumberStamp per specificare il formato del numero di pagina. La macro "# of" è usata per rappresentare il conteggio totale delle pagine.

#### D: Cosa succede se aggiungo lo stesso timbro con il numero di pagina a più pagine?

A: Aggiungendo la stessa istanza di PageNumberStamp a più pagine verranno visualizzati i numeri di pagina corretti per ogni pagina. Il timbro regola automaticamente il numero di pagina e il conteggio totale delle pagine.

#### D: Posso aggiungere timbri con i numeri di pagina alle sezioni intestazione o piè di pagina di un documento PDF?

R: Sebbene i PageNumberStamp vengano solitamente aggiunti direttamente al contenuto della pagina, è possibile utilizzare FloatingBox o altre tecniche per posizionarli nelle sezioni dell'intestazione o del piè di pagina.

#### D: Come faccio a specificare la posizione del timbro del numero di pagina sulla pagina?

 A: Il`BottomMargin` E`HorizontalAlignment` Le proprietà di PageNumberStamp consentono di controllare la posizione del timbro all'interno della pagina.

#### D: Cosa succede se voglio iniziare la numerazione delle pagine da un numero diverso da 1?

 A: Puoi impostare il`StartingNumber`proprietà di PageNumberStamp per specificare il numero di pagina iniziale.