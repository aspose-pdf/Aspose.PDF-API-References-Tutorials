---
title: Crea collegamento ipertestuale locale nel file PDF
linktitle: Crea collegamento ipertestuale locale nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Crea facilmente collegamenti ipertestuali locali in file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-links-and-actions/create-local-hyperlink/
---
La creazione di collegamenti ipertestuali locali in un file PDF consente di creare collegamenti cliccabili che portano gli utenti ad altre pagine nello stesso documento PDF. Con Aspose.PDF per .NET, è possibile creare facilmente tali collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso per la cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella in cui vuoi salvare il file PDF risultante. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: creare un'istanza del documento

 Creeremo un'istanza di`Document` classe per rappresentare il nostro documento PDF. Ecco il codice corrispondente:

```csharp
Document doc = new Document();
```

## Passaggio 4: aggiungere pagina e testo con collegamenti ipertestuali

In questo passaggio, aggiungeremo una pagina al nostro documento PDF e aggiungeremo del testo contenente collegamenti ipertestuali locali. Definiremo le pagine di destinazione per ogni collegamento. Ecco il codice corrispondente:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Passaggio 5: salvare il documento aggiornato

Ora salviamo il file PDF aggiornato utilizzando il`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per creare un collegamento ipertestuale locale utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea istanza del documento
Document doc = new Document();
// Aggiungi pagina alla raccolta di pagine del file PDF
Page page = doc.Pages.Add();
// Crea istanza di frammento di testo
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Crea un'istanza di collegamento ipertestuale locale
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Imposta la pagina di destinazione per l'istanza del collegamento
link.TargetPageNumber = 7;
// Imposta collegamento ipertestuale TextFragment
text.Hyperlink = link;
// Aggiungi testo alla raccolta di paragrafi della pagina
page.Paragraphs.Add(text);
// Crea una nuova istanza di TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment dovrebbe essere aggiunto sulla nuova pagina
text.IsInNewPage = true;
// Crea un'altra istanza di collegamento ipertestuale locale
link = new LocalHyperlink();
// Imposta la pagina di destinazione per il secondo collegamento ipertestuale
link.TargetPageNumber = 1;
// Imposta collegamento per il secondo TextFragment
text.Hyperlink = link;
// Aggiungi testo alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per creare collegamenti ipertestuali locali in un PDF usando Aspose.PDF per .NET. Puoi usare questo codice per creare collegamenti cliccabili che portano gli utenti ad altre pagine nello stesso documento.

Per maggiori informazioni sulle funzionalità avanzate di collegamento ipertestuale, consultate la documentazione ufficiale di Aspose.PDF.

### FAQ per creare un collegamento ipertestuale locale nel file PDF

#### D: Cosa sono i collegamenti ipertestuali locali in un file PDF?

R: Gli hyperlink locali in un file PDF sono link cliccabili che indirizzano gli utenti a pagine diverse all'interno dello stesso documento. Questi link migliorano la navigazione e consentono ai lettori di accedere rapidamente alle sezioni pertinenti.

#### D: In che modo i collegamenti ipertestuali locali possono essere utili al mio documento PDF?

A: Gli hyperlink locali forniscono un modo efficiente per collegare contenuti correlati all'interno dello stesso documento PDF. Migliorano l'esperienza utente consentendo ai lettori di passare rapidamente a sezioni specifiche senza scorrere l'intero documento.

#### D: In che modo Aspose.PDF per .NET supporta la creazione di collegamenti ipertestuali locali?
R: Aspose.PDF per .NET offre un supporto completo per la creazione di collegamenti ipertestuali locali. Il tutorial passo-passo fornito in questa guida dimostra come aggiungere collegamenti ipertestuali locali al documento PDF utilizzando C#.

#### D: Posso personalizzare l'aspetto dei collegamenti ipertestuali locali?

R: Sì, puoi personalizzare l'aspetto dei collegamenti ipertestuali locali, inclusi il colore e lo stile del testo, per garantire che corrispondano al design del tuo documento e forniscano un'esperienza visiva coerente.

#### D: È possibile creare più collegamenti ipertestuali locali all'interno di una singola pagina PDF?

R: Assolutamente! Puoi creare più collegamenti ipertestuali locali all'interno di una singola pagina PDF, consentendo ai lettori di passare a varie sezioni o pagine a seconda delle necessità. Ogni collegamento ipertestuale locale può essere adattato al rispettivo target.

#### D: Posso collegarmi a sezioni specifiche di una pagina utilizzando collegamenti ipertestuali locali?

R: Mentre gli hyperlink locali in genere navigano verso pagine intere, puoi creare ancore o segnalibri all'interno del tuo documento PDF per ottenere un collegamento mirato. Aspose.PDF per .NET supporta varie opzioni di hyperlinking.

#### D: Come posso verificare che i miei collegamenti ipertestuali locali funzionino correttamente?

R: Seguendo il tutorial e il codice di esempio forniti, puoi creare con sicurezza hyperlink locali funzionali. Puoi testare i link aprendo il documento PDF generato e cliccando sul testo dell'hyperlink.

#### D: Ci sono delle limitazioni quando si utilizzano i collegamenti ipertestuali locali?

R: Gli hyperlink locali sono un modo efficace per migliorare la navigazione del documento, ma è importante assicurarsi che la struttura del documento rimanga chiara e intuitiva. Gli hyperlink e gli anchor correttamente etichettati contribuiscono a un'esperienza utente positiva.

#### D: Posso creare collegamenti ipertestuali locali all'interno di tabelle o immagini?

R: Sì, puoi creare collegamenti ipertestuali locali all'interno di vari elementi del tuo documento PDF, tra cui tabelle, immagini e testo. Aspose.PDF per .NET offre flessibilità nell'aggiunta di collegamenti ipertestuali a diversi tipi di contenuto.