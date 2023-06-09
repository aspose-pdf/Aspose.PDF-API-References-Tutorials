---
title: Aggiungi timbro pagina PDF
linktitle: Aggiungi timbro pagina PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere facilmente un timbro di pagina PDF ai tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

In questo tutorial, ti guideremo passo dopo passo su come aggiungere un timbro di pagina PDF a un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per aggiungere un timbro personalizzato a una pagina specifica del documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: creazione del buffer della pagina

Ora che hai caricato il documento PDF, puoi creare il timbro pagina da aggiungere. Ecco come farlo:

```csharp
// Crea il buffer della pagina
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Il codice sopra crea un nuovo buffer di pagina utilizzando la prima pagina del documento PDF.

## Passaggio 4: configurazione delle proprietà del buffer di pagina

Prima di aggiungere il timbro di pagina al documento PDF, puoi configurare varie proprietà del timbro, come sfondo, posizione, rotazione, ecc. Ecco come:

```csharp
// Configurare le proprietà del buffer della pagina
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

È possibile regolare queste proprietà in base alle proprie esigenze.

## Passaggio 5: aggiunta del timbro di pagina al PDF

Ora che il timbro pagina è pronto, puoi aggiungerlo a una pagina specifica del documento PDF. Ecco come:

```csharp
// Aggiungi il buffer della pagina a una pagina specifica
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Il codice precedente aggiunge il timbro di pagina alla prima pagina del documento PDF. È possibile specificare un'altra pagina, se necessario.

## Passaggio 6: salvare il documento di output

Dopo aver aggiunto il timbro pagina, puoi salvare il documento PDF modificato. Ecco come:

```csharp
// Salva il documento di output
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Aggiungi PDFPage Stamp utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Crea timbro pagina
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Aggiungi timbro a una pagina particolare
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Salva documento di output
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

Il codice precedente salva il documento PDF modificato nella directory specificata.

## Conclusione

Congratulazioni! Hai imparato come aggiungere un timbro di pagina PDF utilizzando Aspose.PDF per .NET. Ora puoi applicare questa conoscenza ai tuoi progetti per aggiungere timbri personalizzati a pagine specifiche dei tuoi documenti PDF.
