---
title: Aggiungi elenco ordinato HTML nei documenti
linktitle: Aggiungi elenco ordinato HTML nei documenti
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere un elenco ordinato HTML a un documento utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-text/add-html-ordered-list-into-documents/
---

In questo tutorial imparerai come utilizzare la libreria Aspose.PDF per .NET per aggiungere un elenco ordinato HTML in un documento. Il codice fornito illustra i passaggi necessari per eseguire questa attività.

## Requisiti
Prima di iniziare, assicurati di disporre di quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato nel tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere l'elenco ordinato HTML, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individuare la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i documenti.

 Quindi, individua la riga che dice`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e sostituire`"AddHTMLOrderedListIntoDocuments_out.pdf"` con il nome desiderato per il file PDF di output.

## Passaggio 4: creare un nuovo oggetto documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: creare un oggetto HtmlFragment con il contenuto HTML
Istanziare un`HtmlFragment` oggetto con il contenuto HTML che desideri aggiungere al documento. Nel codice fornito, il contenuto HTML è assegnato alla variabile`t`. È possibile modificare il contenuto HTML secondo necessità.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Passaggio 6: aggiungi una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il file`Add` metodo del`Pages` collezione. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 7: aggiungere HtmlFragment alla pagina
 Aggiungi il`HtmlFragment` opporsi alla pagina utilizzando il`Add` metodo del`Paragraphs` collezione.

```csharp
page.Paragraphs.Add(t);
```

## Passaggio 8: salvare il documento PDF
 Salvare il file PDF risultante utilizzando il file`Save` metodo del`Document` oggetto. Specificare il percorso del file di output impostato nel passaggio 3.

```csharp
doc.Save(outFile);
```

### Esempio di codice sorgente per Aggiungi elenco ordinato HTML nei documenti utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Il percorso del documento di output.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Crea un'istanza dell'oggetto Document
Document doc = new Document();
// Crea un'istanza dell'oggetto HtmlFragment con il frammento HTML corrispondente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Aggiungi pagina nella raccolta di pagine
Page page = doc.Pages.Add();
// Aggiungi HtmlFragment all'interno della pagina
page.Paragraphs.Add(t);
// Salva il file PDF risultante
doc.Save(outFile);
```

## Conclusione
Hai aggiunto correttamente un elenco ordinato HTML in un documento utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

Ricorda di personalizzare il contenuto HTML e adattare il codice in base alle tue esigenze specifiche.