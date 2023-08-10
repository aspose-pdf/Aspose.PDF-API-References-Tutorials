---
title: Crea collegamento ipertestuale locale nel file PDF
linktitle: Crea collegamento ipertestuale locale nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Crea facilmente collegamenti ipertestuali locali nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 40
url: /it/net/programming-with-links-and-actions/create-local-hyperlink/
---
La creazione di collegamenti ipertestuali locali nel file PDF consente di creare collegamenti selezionabili che portano gli utenti ad altre pagine nello stesso documento PDF. Con Aspose.PDF per .NET, puoi facilmente creare tali collegamenti seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, è necessario specificare il percorso della cartella in cui si desidera salvare il file PDF risultante. Sostituire`"YOUR DOCUMENT DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: creare un'istanza di Document

 Creeremo un'istanza di`Document` class per rappresentare il nostro documento PDF. Ecco il codice corrispondente:

```csharp
Document doc = new Document();
```

## Passaggio 4: aggiungi pagina e testo con collegamenti ipertestuali

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

 Ora salviamo il file PDF aggiornato utilizzando l'estensione`Save` metodo del`doc` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Crea collegamento ipertestuale locale utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crea un'istanza di documento
Document doc = new Document();
// Aggiungi pagine alla raccolta di pagine di file PDF
Page page = doc.Pages.Add();
// Crea un'istanza di frammento di testo
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Crea un'istanza di collegamento ipertestuale locale
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Imposta la pagina di destinazione per l'istanza del collegamento
link.TargetPageNumber = 7;
// Imposta il collegamento ipertestuale TextFragment
text.Hyperlink = link;
//Aggiungi testo alla raccolta di paragrafi di Page
page.Paragraphs.Add(text);
// Crea una nuova istanza TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment dovrebbe essere aggiunto su una nuova pagina
text.IsInNewPage = true;
// Crea un'altra istanza di collegamento ipertestuale locale
link = new LocalHyperlink();
// Imposta la pagina di destinazione per il secondo collegamento ipertestuale
link.TargetPageNumber = 1;
// Imposta il collegamento per il secondo TextFragment
text.Hyperlink = link;
// Aggiungi testo alla raccolta di paragrafi dell'oggetto pagina
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Salva documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per creare collegamenti ipertestuali locali in un PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare questo codice per creare collegamenti selezionabili che indirizzano gli utenti ad altre pagine dello stesso documento.

Assicurati di controllare la documentazione ufficiale di Aspose.PDF per ulteriori informazioni sulle funzionalità avanzate di collegamento ipertestuale.

### Domande frequenti per creare collegamenti ipertestuali locali nel file PDF

#### D: Cosa sono i collegamenti ipertestuali locali in un file PDF?

R: I collegamenti ipertestuali locali in un file PDF sono collegamenti selezionabili che conducono gli utenti a pagine diverse all'interno dello stesso documento. Questi collegamenti migliorano la navigazione e consentono ai lettori di accedere rapidamente alle sezioni pertinenti.

#### D: In che modo i collegamenti ipertestuali locali possono avvantaggiare il mio documento PDF?

R: I collegamenti ipertestuali locali forniscono un modo efficiente per collegare i contenuti correlati all'interno dello stesso documento PDF. Migliorano l'esperienza dell'utente consentendo ai lettori di passare rapidamente a sezioni specifiche senza scorrere l'intero documento.

#### D: In che modo Aspose.PDF per .NET supporta la creazione di collegamenti ipertestuali locali?
R: Aspose.PDF per .NET offre un supporto completo per la creazione di collegamenti ipertestuali locali. L'esercitazione dettagliata fornita in questa guida mostra come aggiungere collegamenti ipertestuali locali al documento PDF utilizzando C#.

#### D: Posso personalizzare l'aspetto dei collegamenti ipertestuali locali?

R: Sì, puoi personalizzare l'aspetto dei collegamenti ipertestuali locali, inclusi il colore e lo stile del testo, per assicurarti che corrispondano al design del tuo documento e forniscano un'esperienza visiva coerente.

#### D: È possibile creare più collegamenti ipertestuali locali all'interno di una singola pagina PDF?

R: Assolutamente! È possibile creare più collegamenti ipertestuali locali all'interno di una singola pagina PDF, consentendo ai lettori di passare a varie sezioni o pagine secondo necessità. Ogni collegamento ipertestuale locale può essere adattato al rispettivo target.

#### D: Posso collegarmi a sezioni specifiche di una pagina utilizzando collegamenti ipertestuali locali?

R: Mentre i collegamenti ipertestuali locali in genere consentono di accedere a intere pagine, è possibile creare ancore o segnalibri all'interno del documento PDF per ottenere collegamenti mirati. Aspose.PDF per .NET supporta varie opzioni di collegamento ipertestuale.

#### D: Come posso verificare che i miei collegamenti ipertestuali locali funzionino correttamente?

R: Seguendo il tutorial e il codice di esempio fornito, puoi creare con sicurezza collegamenti ipertestuali locali funzionali. Puoi testare i collegamenti aprendo il documento PDF generato e facendo clic sul testo del collegamento ipertestuale.

#### D: Ci sono limitazioni quando si utilizzano i collegamenti ipertestuali locali?

R: I collegamenti ipertestuali locali sono un modo efficace per migliorare la navigazione del documento, ma è importante garantire che la struttura del documento rimanga chiara e intuitiva. I collegamenti ipertestuali e gli ancoraggi adeguatamente etichettati contribuiscono a un'esperienza utente positiva.

#### D: Posso creare collegamenti ipertestuali locali all'interno di tabelle o immagini?

R: Sì, puoi creare collegamenti ipertestuali locali all'interno di vari elementi del tuo documento PDF, incluse tabelle, immagini e testo. Aspose.PDF per .NET offre flessibilità nell'aggiunta di collegamenti ipertestuali a diversi tipi di contenuto.