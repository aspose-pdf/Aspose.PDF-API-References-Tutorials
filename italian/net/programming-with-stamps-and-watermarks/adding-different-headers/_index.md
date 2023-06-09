---
title: Aggiunta di intestazioni diverse
linktitle: Aggiunta di intestazioni diverse
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere facilmente diverse intestazioni a ciascuna pagina dei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
In questo tutorial, ti guideremo passo dopo passo su come aggiungere diverse intestazioni a un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere intestazioni personalizzate a ogni pagina del documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento di origine
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione di buffer di intestazione

Ora che hai caricato il documento PDF, puoi creare i timbri di intestazione da aggiungere. Ecco come:

```csharp
// Crea tre buffer di intestazione
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Il codice precedente crea tre nuovi buffer di intestazione contenenti il testo specificato.

## Passaggio 4: configurazione delle proprietà del buffer di intestazione

Prima di aggiungere i timbri di intestazione al documento PDF, puoi configurare diverse proprietà per ogni timbro, come allineamento, dimensione, colore, ecc. Ecco come:

```csharp
// Configura il primo buffer di intestazione
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Configurazione del secondo buffer di intestazione
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Configura il terzo buffer di intestazione
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

È possibile regolare queste proprietà secondo necessità per ciascun buffer di intestazione.

## Passaggio 5: aggiungi i timbri di intestazione al PDF

Ora che i timbri di intestazione sono pronti, puoi aggiungerli a ciascuna pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi buffer di intestazione a pagine specifiche
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Il codice sopra aggiunge ogni timbro di intestazione alla pagina corrispondente del documento PDF.

## Passaggio 6: salvare il documento di output

Una volta aggiunti i timbri di intestazione, è possibile salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento aggiornato
doc.Save(dataDir);
```

Il codice precedente salva il documento PDF modificato nella directory specificata.

### Codice sorgente di esempio per l'aggiunta di intestazioni diverse utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Documento open source
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Crea tre francobolli
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Imposta l'allineamento del timbro (posiziona il timbro in cima alla pagina, centrato orizzontalmente)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Specificare lo stile del carattere come Grassetto
stamp1.TextState.FontStyle = FontStyles.Bold;

// Impostare le informazioni sul colore di sfondo del testo come rosso
stamp1.TextState.ForegroundColor = Color.Red;

// Specificare la dimensione del carattere come 14
stamp1.TextState.FontSize = 14;

// Ora dobbiamo impostare l'allineamento verticale del secondo oggetto timbro come Alto
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Imposta le informazioni di allineamento orizzontale per il timbro come Allineato al centro
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Imposta il fattore di zoom per l'oggetto timbro
stamp2.Zoom = 10;

// Imposta la formattazione del terzo oggetto timbro
// Specificare le informazioni sull'allineamento verticale per l'oggetto timbro come TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Imposta le informazioni sull'allineamento orizzontale per l'oggetto timbro come Allineato al centro
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Imposta l'angolo di rotazione per l'oggetto timbro
stamp3.RotateAngle = 35;

// Imposta il rosa come colore di sfondo per il timbro
stamp3.TextState.BackgroundColor = Color.Pink;

// Modificare le informazioni sul carattere del timbro in Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Il primo timbro è aggiunto sulla prima pagina;
doc.Pages[1].AddStamp(stamp1);

// Il secondo timbro è aggiunto sulla seconda pagina;
doc.Pages[2].AddStamp(stamp2);

// Il terzo timbro è aggiunto alla terza pagina.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Conclusione

Congratulazioni! Hai imparato come aggiungere intestazioni diverse a ciascuna pagina di un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per personalizzare le intestazioni dei tuoi documenti PDF.
