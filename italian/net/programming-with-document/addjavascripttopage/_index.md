---
title: Aggiungi Java Script alla pagina
linktitle: Aggiungi Java Script alla pagina
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere JavaScript ai file PDF utilizzando Aspose.PDF per .NET. Guida dettagliata con esercitazioni sul codice per lo scripting a livello di documento e pagina.
type: docs
weight: 10
url: /it/net/programming-with-document/addjavascripttopage/
---

Per aggiungere JavaScript a un file PDF, useremo Aspose.PDF per .NET. Questa libreria fornisce un modo semplice ed efficiente per lavorare con i file PDF nelle applicazioni .NET. I seguenti passaggi ti guideranno attraverso il processo di aggiunta di JavaScript a un file PDF utilizzando Aspose.PDF per .NET.

## Passaggio 1: carica il file PDF

 Il primo passo è caricare il file PDF a cui vuoi aggiungere JavaScript. Puoi farlo usando il`Document` classe fornita da Aspose.PDF per .NET. IL`Document` class fornisce metodi per caricare, salvare e manipolare i file PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 2: aggiungi JavaScript a livello di documento

 Per aggiungere JavaScript a livello di documento, useremo il file`JavascriptAction` classe fornita da Aspose.PDF per .NET. Questa classe consente di specificare l'istruzione JavaScript che si desidera aggiungere al file PDF.

```csharp
// Aggiunta di JavaScript a livello di documento
// Crea un'istanza JavascriptAction con l'istruzione JavaScript desiderata
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assegna l'oggetto JavascriptAction all'azione desiderata di Document
doc.OpenAction = javaScript;
```

In questo tutorial, stiamo aggiungendo un'istruzione JavaScript che stamperà il file PDF con le opzioni specificate quando il documento viene aperto.

## Passaggio 3: aggiungi JavaScript a livello di pagina

 Per aggiungere JavaScript a livello di pagina, utilizzeremo il file`JavascriptAction` classe e il`Actions`proprietà fornita da Aspose.PDF per .NET. Questa proprietà consente di specificare istruzioni JavaScript che verranno eseguite all'apertura o alla chiusura della pagina.

```csharp
// Aggiunta di JavaScript a livello di pagina
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

In questo tutorial, stiamo aggiungendo istruzioni JavaScript che visualizzeranno un messaggio di avviso quando la pagina viene aperta o chiusa.

## Passaggio 4: salvare il file PDF

 Dopo aver aggiunto il codice JavaScript al file PDF, è necessario salvare il file modificato. Puoi farlo usando il`Save` metodo fornito dal`Document` classe.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Salva documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Questo codice salverà il file PDF modificato nella directory specificata.

### Codice sorgente di esempio per Aggiungi script Java alla pagina utilizzando Aspose.PDF per .NET

```csharp
            
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");

// Aggiunta di JavaScript a livello di documento
// Crea un'istanza di JavascriptAction con l'istruzione JavaScript desiderata
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assegna l'oggetto JavascriptAction all'azione desiderata di Document
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

In questo articolo, abbiamo spiegato come aggiungere JavaScript a un file PDF sia a livello di documento che a livello di pagina utilizzando Aspose.PDF per .NET. Abbiamo fornito istruzioni dettagliate e incluso il codice sorgente completo per ogni esempio. Con questa conoscenza, puoi aggiungere JavaScript ai tuoi file PDF e personalizzarne il comportamento in base alle tue esigenze.


