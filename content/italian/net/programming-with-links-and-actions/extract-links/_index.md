---
title: Estrai i link nel file PDF
linktitle: Estrai i link nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Estrai facilmente i link nei file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 50
url: /it/net/programming-with-links-and-actions/extract-links/
---
L'estrazione di link in un file PDF consente di recuperare tutti i link ipertestuali presenti nel documento. Con Aspose.PDF per .NET, puoi estrarre facilmente questi link seguendo il seguente codice sorgente:

## Passaggio 1: importare le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco la direttiva di importazione necessaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Passaggio 2: imposta il percorso per la cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF da cui vuoi estrarre i link. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel codice seguente con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 3: aprire il documento PDF

 Apriremo il documento PDF utilizzando il`Document` classe. Ecco il codice corrispondente:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Passaggio 4: estrai i link

 In questa fase estrarremo i link presenti nel documento PDF utilizzando il`AnnotationSelector` classe. Ecco il codice corrispondente:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Passaggio 5: salvare il documento aggiornato

Ora salviamo il file PDF aggiornato utilizzando il`Save` metodo del`document` oggetto. Ecco il codice corrispondente:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Esempio di codice sorgente per Estrai collegamenti utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Apri documento
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Azioni di estrazione
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Salva il documento aggiornato
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Conclusione

Congratulazioni! Ora hai una guida passo-passo per estrarre i link da un documento PDF usando Aspose.PDF per .NET. Puoi usare questo codice per recuperare tutti gli hyperlink presenti nel documento.

Per maggiori informazioni sulle funzionalità avanzate di estrazione dei link, consultate la documentazione ufficiale di Aspose.PDF.

### FAQ per estrarre i link nel file PDF

#### D: Che cosa si intende per estrazione di link in un file PDF?

A: L'estrazione di link in un file PDF si riferisce al processo di recupero di tutti i link ipertestuali presenti nel documento. Ciò consente di recuperare URL, link interni al documento e altri elementi interattivi.

#### D: In che modo l'estrazione dei link può essere utile per l'analisi dei miei documenti PDF?

A: L'estrazione dei link è utile per vari scopi, come la convalida dei contenuti, il data mining e l'analisi. Consente di identificare e catalogare tutti i link all'interno di un documento PDF per un'ulteriore esplorazione.

#### D: In che modo Aspose.PDF per .NET supporta l'estrazione dei link?

A: Aspose.PDF per .NET fornisce potenti API per estrarre facilmente link da documenti PDF. Il tutorial passo dopo passo descritto in questa guida dimostra come estrarre link usando C#.

#### D: Posso estrarre tipi specifici di link, come collegamenti ipertestuali o link a documenti interni?

 A: Sì, puoi estrarre selettivamente tipi specifici di link utilizzando`AnnotationSelector`classe. Ciò consente di filtrare e recuperare i link desiderati in base alle proprie esigenze.

#### D: È possibile estrarre i link da pagine specifiche di un documento PDF?

 A: Assolutamente! Puoi estrarre i link da pagine specifiche di un documento PDF specificando la pagina di destinazione utilizzando`Document.Pages` raccolta. Ciò ti consente di concentrarti su sezioni specifiche.

#### D: In quale formato vengono restituiti i link estratti?

 A: I link estratti vengono restituiti come istanze di`Annotation` classe. Puoi elaborare e analizzare queste annotazioni per recuperare i dettagli del collegamento, inclusi gli URL di destinazione e i tipi di collegamento.

#### D: Come posso verificare che l'estrazione dei link sia accurata?

A: Seguendo il tutorial e il codice di esempio forniti, puoi garantire un'estrazione di link accurata. Puoi analizzare le annotazioni estratte e convalidare gli URL e gli attributi dei link.

#### D: Ci sono delle limitazioni quando si estraggono i link?

R: Sebbene l'estrazione dei link sia una funzionalità potente, è importante considerare la struttura del documento PDF. I link incorporati in immagini, tabelle o contenuti multimediali potrebbero richiedere una gestione aggiuntiva.

#### D: Posso estrarre i link dai documenti PDF protetti da password?

R: Aspose.PDF per .NET può estrarre collegamenti da documenti PDF protetti da password, a condizione che vengano fornite le credenziali di autenticazione necessarie quando si apre il documento.