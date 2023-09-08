---
title: Aggiungi script Java al file PDF
linktitle: Aggiungi file PDF Java Script
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere JavaScript al file PDF utilizzando Aspose.PDF per .NET. Guida passo passo con tutorial sul codice per lo scripting a livello di documento e pagina.
type: docs
weight: 10
url: /it/net/programming-with-document/addjavascripttopage/
---
Per aggiungere JavaScript a un file PDF, utilizzeremo Aspose.PDF per .NET. Questa libreria fornisce un modo semplice ed efficiente per lavorare con file PDF nelle applicazioni .NET. I seguenti passaggi ti guideranno attraverso il processo di aggiunta di JavaScript a un file PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: caricare il file PDF

 Il primo passo è caricare il file PDF a cui desideri aggiungere JavaScript. Puoi farlo usando il file`Document` classe fornita da Aspose.PDF per .NET. IL`Document` fornisce metodi per caricare, salvare e manipolare file PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 2: aggiungi JavaScript a livello di documento

Per aggiungere JavaScript a livello di documento, utilizzeremo il file`JavascriptAction` classe fornita da Aspose.PDF per .NET. Questa classe ti consente di specificare l'istruzione JavaScript che desideri aggiungere al file PDF.

```csharp
// Aggiunta di JavaScript a livello di documento
// Crea un'istanza di JavascriptAction con l'istruzione JavaScript desiderata
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assegna l'oggetto JavascriptAction all'azione desiderata del documento
doc.OpenAction = javaScript;
```

In questo tutorial, aggiungeremo un'istruzione JavaScript che stamperà il file PDF con le opzioni specificate all'apertura del documento.

## Passaggio 3: aggiungi JavaScript a livello di pagina

 Per aggiungere JavaScript a livello di pagina, utilizzeremo il file`JavascriptAction` classe e il`Actions` proprietà fornita da Aspose.PDF per .NET. Questa proprietà consente di specificare le istruzioni JavaScript che verranno eseguite quando la pagina viene aperta o chiusa.

```csharp
// Aggiunta di JavaScript a livello di pagina
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

In questo tutorial aggiungeremo istruzioni JavaScript che visualizzeranno un messaggio di avviso quando la pagina viene aperta o chiusa.

## Passaggio 4: salva il file PDF

Dopo aver aggiunto JavaScript al file PDF, è necessario salvare il file modificato. Puoi farlo usando il file`Save` metodo previsto dal`Document` classe.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Salva documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Questo codice salverà il file PDF modificato nella directory specificata.

### Codice sorgente di esempio per Aggiungi Java Script alla pagina utilizzando Aspose.PDF per .NET

```csharp
            
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");

// Aggiunta di JavaScript a livello di documento
// Crea un'istanza di JavascriptAction con l'istruzione JavaScript desiderata
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assegna l'oggetto JavascriptAction all'azione desiderata del documento
doc.OpenAction = javaScript;

// Aggiunta di JavaScript a livello di pagina
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Salva documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusione

In questo articolo, abbiamo spiegato come aggiungere JavaScript a un file PDF sia a livello di documento che a livello di pagina utilizzando Aspose.PDF per .NET. Abbiamo fornito istruzioni dettagliate e incluso il codice sorgente completo per ogni esempio. Con questa conoscenza, puoi aggiungere JavaScript ai tuoi file PDF e personalizzare il loro comportamento in base alle tue esigenze.


### Domande frequenti per aggiungere script Java al file PDF

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di lavorare con file PDF nelle applicazioni .NET. Fornisce un'ampia gamma di funzionalità per creare, modificare e manipolare documenti PDF.

#### D: Posso aggiungere JavaScript a un documento PDF utilizzando Aspose.PDF per .NET?

R: Sì, Aspose.PDF per .NET ti consente di aggiungere JavaScript sia a livello di documento che a livello di pagina di un file PDF, consentendoti di creare documenti PDF dinamici e interattivi.

#### D: Come posso caricare un file PDF esistente utilizzando Aspose.PDF per .NET?

 R: Puoi caricare un file PDF esistente utilizzando il file`Document` classe e i suoi metodi, come mostrato nella guida passo passo.

#### D: Quali tipi di azioni JavaScript posso aggiungere a un documento PDF?

R: Con Aspose.PDF per .NET, puoi aggiungere un'ampia varietà di azioni JavaScript, come stampa, messaggi di avviso, manipolazione dei campi del modulo e altro ancora.

#### D: Aspose.PDF per .NET è adatto a progetti commerciali?

R: Sì, Aspose.PDF per .NET è una libreria affidabile e robusta che viene comunemente utilizzata in progetti commerciali per attività di manipolazione e generazione di PDF.

