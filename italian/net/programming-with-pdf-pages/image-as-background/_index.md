---
title: Imposta l'immagine come sfondo
linktitle: Imposta l'immagine come sfondo
second_title: Aspose.PDF per riferimento API .NET
description: Guida dettagliata per impostare un'immagine come sfondo della pagina in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-pdf-pages/image-as-background/
---
In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare un'immagine come sfondo della pagina utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come aggiungere un'immagine come sfondo della pagina in un documento PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento PDF modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un nuovo documento
 Quindi puoi creare un nuovo oggetto Documento usando il file`Document` classe.

```csharp
Document doc = new Document();
```

## Passaggio 3: aggiungi una nuova pagina al documento
 Ora puoi aggiungere una nuova pagina all'oggetto Document usando il file`Add()` metodo del`Pages` classe.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 4: creare un oggetto Background Artifact
Quindi puoi creare un nuovo oggetto BackgroundArtifact per impostare l'immagine di sfondo.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Passaggio 5: aggiungi lo sfondo alla pagina
 Quindi puoi aggiungere l'oggetto BackgroundArtifact alla raccolta di artefatti della pagina utilizzando il`Artifacts` proprietà del`Page` classe.

```csharp
page. Artifacts. Add(background);
```

## Passaggio 6: salvare il documento PDF
 Infine, puoi salvare il documento PDF in un file utilizzando l'estensione`Save()` metodo del`Document` classe. Assicurarsi di specificare il percorso e il nome file corretti.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Esempio di codice sorgente per Immagine come sfondo utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un nuovo oggetto Documento
Document doc = new Document();
// Aggiungi una nuova pagina all'oggetto documento
Page page = doc.Pages.Add();
// Crea un oggetto artefatto di sfondo
BackgroundArtifact background = new BackgroundArtifact();
// Specificare l'immagine per l'oggetto backgroundartifact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Aggiungi backgroundartifact alla raccolta di artefatti della pagina
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Salva il documento
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Conclusione
In questo tutorial, abbiamo imparato come impostare un'immagine come sfondo della pagina in un documento PDF utilizzando Aspose.PDF per .NET. Seguendo questa guida dettagliata, puoi facilmente aggiungere un'immagine di sfondo ai tuoi documenti PDF. Aspose.PDF offre un'API potente e flessibile per lavorare con i file PDF, inclusa la personalizzazione dello sfondo della pagina. Ora puoi applicare questa funzione nei tuoi progetti per creare documenti PDF con immagini di sfondo personalizzate
