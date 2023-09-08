---
title: Imposta il nome del carattere predefinito
linktitle: Imposta il nome del carattere predefinito
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per impostare il nome del carattere predefinito nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 270
url: /it/net/document-conversion/set-default-font-name/
---
In questo tutorial, ti mostreremo come impostare il nome del carattere predefinito in un file PDF utilizzando Aspose.PDF per .NET. A volte, quando estrai immagini da un file PDF, potresti riscontrare problemi con i caratteri mancanti. Specificando un nome di carattere predefinito, puoi garantire che il testo estratto verrà visualizzato correttamente. Seguire i passaggi seguenti per impostare il nome del carattere predefinito in un file PDF.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PDF
 Il primo passo è caricare il documento PDF in un file`Document` oggetto. Utilizza il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Codice da aggiungere
}
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: imposta il nome del carattere predefinito
 Successivamente, imposteremo il nome del carattere predefinito utilizzando il file`DefaultFontName` opzione del`RenderingOptions` oggetto. Utilizza il seguente codice:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Codice da aggiungere
     }
}
```

 Assicurati di sostituire`"Arial"` con il nome del carattere desiderato.

## Passaggio 3: estrazione dell'immagine
Successivamente, estrarremo l'immagine dalla pagina specificata del documento PDF. Utilizza il seguente codice:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Assicurati di specificare il numero di pagina corretto in`pdfDocument.Pages[1]`.

### Codice sorgente di esempio per Imposta nome carattere predefinito utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare il nome del carattere predefinito in un file PDF utilizzando Aspose.PDF per .NET. Specificando un nome di carattere predefinito, puoi garantire che il testo estratto verrà visualizzato correttamente. Utilizza questo metodo per risolvere i problemi relativi ai caratteri mancanti durante l'estrazione di immagini da file PDF.

### Domande frequenti

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di lavorare con documenti PDF in applicazioni C#. Offre varie funzionalità, inclusa l'impostazione del nome del carattere predefinito in un file PDF.

#### D: Perché dovrei impostare il nome del carattere predefinito in un file PDF?

R: L'impostazione del nome del carattere predefinito è utile quando si estrae testo da un documento PDF. Se il PDF contiene testo con caratteri non disponibili sulla macchina di estrazione, la specifica di un nome di carattere predefinito garantisce la corretta visualizzazione del testo.

#### D: Come posso caricare un documento PDF e impostare il nome del carattere predefinito utilizzando Aspose.PDF per .NET?

 R: Per caricare un documento PDF e impostare il nome del carattere predefinito, è possibile utilizzare il file`Document`class per caricare il file PDF e il file`RenderingOptions.DefaultFontName` proprietà per specificare il nome del carattere predefinito desiderato.

#### D: Posso scegliere qualsiasi carattere come nome del carattere predefinito?

R: Sì, puoi scegliere qualsiasi carattere disponibile sulla macchina di estrazione come nome del carattere predefinito. Utilizza un carattere che corrisponda il più possibile ai caratteri mancanti nel PDF originale per garantire un rendering accurato del testo.

#### D: L'impostazione del nome del carattere predefinito rappresenta una modifica permanente al file PDF?

R: No, l'impostazione del nome del carattere predefinito utilizzando Aspose.PDF per .NET è una modifica temporanea apportata durante l'estrazione del testo. Non modifica il file PDF originale.