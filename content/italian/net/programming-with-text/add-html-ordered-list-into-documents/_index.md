---
title: Aggiungere un elenco ordinato HTML nei documenti
linktitle: Aggiungere un elenco ordinato HTML nei documenti
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un elenco ordinato HTML a un documento utilizzando Aspose.PDF per .NET.
type: docs
weight: 30
url: /it/net/programming-with-text/add-html-ordered-list-into-documents/
---
In questo tutorial, imparerai come usare la libreria Aspose.PDF per .NET per aggiungere un elenco ordinato HTML in un documento. Il codice fornito illustra i passaggi necessari per portare a termine questa attività.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere l'elenco ordinato HTML, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare la directory del documento e il percorso del file di output
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

 Quindi, individua la riga che dice`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e sostituire`"AddHTMLOrderedListIntoDocuments_out.pdf"` con il nome desiderato per il file PDF di output.

## Passaggio 4: creare un nuovo oggetto Documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: creare un oggetto HtmlFragment con il contenuto HTML
 Crea un'istanza`HtmlFragment` oggetto con il contenuto HTML che vuoi aggiungere al documento. Nel codice fornito, il contenuto HTML è assegnato alla variabile`t`È possibile modificare il contenuto HTML in base alle proprie esigenze.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Passaggio 6: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando il`Add` metodo del`Pages` raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 7: aggiungere HtmlFragment alla pagina
 Aggiungere il`HtmlFragment` oggetto alla pagina utilizzando il`Add` metodo del`Paragraphs` collezione.

```csharp
page.Paragraphs.Add(t);
```

## Passaggio 8: Salvare il documento PDF
 Salvare il file PDF risultante utilizzando`Save` metodo del`Document` oggetto. Specifica il percorso del file di output impostato nel passaggio 3.

```csharp
doc.Save(outFile);
```

### Esempio di codice sorgente per aggiungere un elenco HTMLordinato nei documenti utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Percorso verso il documento di output.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Crea un'istanza dell'oggetto Documento
Document doc = new Document();
// Crea un'istanza dell'oggetto HtmlFragment con il frammento HTML corrispondente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Aggiungi pagina nella raccolta Pagine
Page page = doc.Pages.Add();
// Aggiungi HtmlFragment all'interno della pagina
page.Paragraphs.Add(t);
//Salva il file PDF risultante
doc.Save(outFile);
```

## Conclusione
Hai aggiunto con successo un elenco ordinato HTML in un documento utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

Ricordatevi di personalizzare il contenuto HTML e di adattare il codice in base alle vostre esigenze specifiche.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di aggiunta di un elenco ordinato HTML in un documento utilizzando la libreria Aspose.PDF per .NET. Fornisce istruzioni dettagliate e frammenti di codice per aiutarti a raggiungere questo obiettivo.

#### D: Quali namespace devo importare per questo tutorial?

A: Devi importare i seguenti namespace all'inizio del tuo file di codice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### D: Come faccio a specificare la directory del documento e il percorso del file di output?

 A: Nel codice, individua la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del tuo documento. Inoltre, trova la riga`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` e sostituire`"AddHTMLOrderedListIntoDocuments_out.pdf"` con il nome del file PDF di output desiderato.

#### D: Posso personalizzare il contenuto HTML aggiunto al documento?

 A: Assolutamente! Nel passaggio 5, creerai un`HtmlFragment` oggetto denominato`t` che contiene il contenuto HTML. Puoi modificare il contenuto HTML all'interno dei backtick per adattarlo alle tue esigenze.

#### D: Come posso aggiungere l'elenco ordinato HTML a una pagina del documento?

 A: Nel passaggio 7, aggiungerai il`HtmlFragment` oggetto (`t` ) alla pagina utilizzando il`Add` metodo del`Paragraphs` raccolta. Ciò integrerà perfettamente l'elenco ordinato HTML nel documento.

#### D: Come posso salvare il documento PDF risultante?

 A: Dopo aver aggiunto il contenuto HTML e averlo disposto su una pagina, puoi salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto. Assicurati di fornire il percorso corretto del file di output impostato in precedenza.

#### D: Puoi fornire un riepilogo del codice sorgente di esempio come riferimento?

A: Certamente! Ecco una versione riassunta del codice sorgente di esempio fornito in questo tutorial:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come sfruttare la libreria Aspose.PDF per .NET per incorporare un elenco ordinato HTML in un documento. Questa nuova conoscenza può essere applicata per migliorare i tuoi processi di creazione e manipolazione dei documenti.