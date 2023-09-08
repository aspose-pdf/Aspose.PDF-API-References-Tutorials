---
title: Aggiungi HTML utilizzando DOM
linktitle: Aggiungi HTML utilizzando DOM
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere contenuto HTML utilizzando DOM in Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-text/add-html-using-dom/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di contenuto HTML utilizzando DOM (Document Object Model) in Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere il contenuto HTML, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: crea un nuovo oggetto Documento
 Istanziarne uno nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: aggiungi una pagina al documento
 Aggiungi una nuova pagina al documento utilizzando il file`Add` metodo del`Pages`collezione. Nel codice fornito, la nuova pagina viene assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 6: crea un HtmlFragment con il contenuto HTML
 Istanziare un`HtmlFragment` oggetto e fornire il contenuto HTML desiderato. Nel codice fornito, il contenuto HTML viene assegnato alla variabile`titel`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Passaggio 7: impostare le informazioni sul margine
Se necessario, regola il margine inferiore e superiore del frammento HTML. Nel codice fornito, il margine inferiore è impostato su 10 e il margine superiore è impostato su 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Passaggio 8: aggiungi HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla raccolta di paragrafi della pagina.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Passaggio 9: salva il documento PDF
 Salvare il documento PDF utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato al passaggio 3.

```csharp
doc.Save(dataDir);
```

## Passaggio 10: visualizzare il messaggio di successo
Visualizza un messaggio di successo insieme al percorso in cui è stato salvato il file PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Codice sorgente di esempio per Aggiungi HTMLUtilizzando DOM utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Istanziare l'oggetto Documento
Document doc = new Document();
// Aggiungi una raccolta di pagine a pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di HtmlFragment con reti HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Imposta le informazioni sul margine inferiore
titel.Margin.Bottom = 10;
// Imposta le informazioni sul margine superiore
titel.Margin.Top = 200;
// Aggiungi un frammento HTML alla raccolta di paragrafi della pagina
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusione
Hai aggiunto con successo contenuto HTML utilizzando DOM in Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

R: Questo tutorial mira a fornire una guida passo passo su come aggiungere contenuto HTML a un documento PDF utilizzando il Document Object Model (DOM) in Aspose.PDF per .NET. Include frammenti di codice sorgente C# per aiutarti a comprendere e implementare il processo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui prevedi di aggiungere contenuto HTML, importa il seguente spazio dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
```

#### D: Come posso specificare la directory del documento e il percorso del file di output?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso creare un oggetto Document?

 R: Nel passaggio 4, istanziare un nuovo file`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

#### D: Come faccio ad aggiungere una pagina al documento?

 R: Nel passaggio 5, aggiungerai una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione:

```csharp
Page page = doc.Pages.Add();
```

#### D: Come posso impostare il contenuto HTML utilizzando il DOM?

 R: Nel passaggio 6 creerai un file`HtmlFragment` oggetto e assegnargli il contenuto HTML desiderato. Il contenuto HTML viene assegnato alla variabile`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### D: Posso regolare il margine del contenuto HTML?

R: Sì, al passaggio 7 puoi regolare i margini inferiore e superiore del frammento HTML secondo necessità:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### D: Come posso aggiungere il frammento HTML al documento PDF?

 R: Nel passaggio 8 aggiungerai il file`HtmlFragment` oggetto (`titel`) alla raccolta paragrafi della pagina:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### D: Come posso salvare il documento PDF risultante?

 R: Dopo aver aggiunto il contenuto HTML e regolato i margini, utilizza il file`Save` metodo del`Document` oggetto per salvare il documento PDF:

```csharp
doc.Save(dataDir);
```

#### D: Esiste un modo per verificare se il processo ha avuto successo?

R: Sicuramente, nel passaggio 10, verrà visualizzato un messaggio di successo insieme al percorso in cui è stato salvato il file PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come utilizzare il Document Object Model (DOM) in Aspose.PDF per .NET per aggiungere contenuto HTML a un documento PDF. Questa conoscenza ti consente di migliorare le tue capacità di generazione di PDF.