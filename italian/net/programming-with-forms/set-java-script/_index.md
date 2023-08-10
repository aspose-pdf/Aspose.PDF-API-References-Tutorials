---
title: Imposta script Java
linktitle: Imposta script Java
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare JavaScript nei campi modulo nei file PDF.
type: docs
weight: 270
url: /it/net/programming-with-forms/set-java-script/
---
In questa guida, spiegheremo passo dopo passo come utilizzare la libreria Aspose.PDF per .NET per definire JavaScript in un campo modulo di un documento PDF. Ti mostreremo come configurare le azioni JavaScript per eseguire operazioni specifiche sul campo di testo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato nel sistema.
- La libreria Aspose.PDF per .NET. Puoi scaricarlo dal sito ufficiale di Aspose.

## Passaggio 1: configurazione della directory dei documenti

 Il primo passaggio consiste nel configurare la directory dei documenti in cui si trova il file PDF su cui si desidera lavorare. Puoi usare il`dataDir` variabile per specificare il percorso della directory.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del file PDF di input

 In questo passaggio, caricheremo il file PDF di input utilizzando l'estensione`Document` classe di Aspose.PDF.

```csharp
// Carica il file PDF di input
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Assicurarsi che il file PDF di input sia presente nella directory dei documenti specificata.

## Passaggio 3: accesso al campo TextBox

 Per applicare JavaScript a un campo di testo specifico, dobbiamo prima accedere a quel campo. In questo esempio, assumiamo che il campo di testo si chiami "textbox1". Usa il`doc.Form["textbox1"]` metodo per ottenere il corrispondente`TextBoxField` oggetto.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Assicurarsi che il campo di testo specificato esista nel file PDF di input.

## Passaggio 4: configurare le azioni JavaScript

Ora che abbiamo effettuato l'accesso al campo di testo, possiamo configurare le azioni JavaScript associate a questo campo. In questo esempio, utilizzeremo due azioni:`OnModifyCharacter` E`OnFormat` . Queste azioni saranno definite utilizzando`JavascriptAction` oggetti.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Assicurati di personalizzare le azioni JavaScript in base alle tue esigenze.

## Passaggio 5: impostazione del valore del campo iniziale

Prima di salvare il PDF risultante, possiamo impostare un valore iniziale per il campo di testo. In questo esempio, imposteremo il valore "123" per il campo.

```csharp
field.Value = "123";
```

Personalizza questo valore in base alle tue esigenze.

## Passaggio 6: salvare il PDF risultante

 Ora che abbiamo finito di configurare il campo di testo e le azioni JavaScript, possiamo salvare il PDF risultante utilizzando il file`Save` metodo del`Document` classe.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Salva il PDF risultante
doc.Save(dataDir);
```

Assicurati di specificare il percorso completo e il nome del file per il PDF risultante.


### Esempio di codice sorgente per Set Java Script utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il file PDF di input
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 cifre dopo il punto
// Nessun separatore
// Stile negativo = meno
// Nessuna valuta
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Imposta il valore del campo iniziale
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Salva il PDF risultante
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questa guida, abbiamo imparato come utilizzare la libreria Aspose.PDF per .NET per impostare JavaScript in un campo modulo di un documento PDF. Seguendo i passaggi descritti, puoi personalizzare le azioni JavaScript per eseguire varie operazioni sui campi di testo. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.PDF per .NET per espandere le possibilità di manipolazione dei file PDF.


### FAQ

#### D: Posso utilizzare Aspose.PDF per .NET per aggiungere JavaScript ad altri elementi del modulo, come caselle di controllo e pulsanti di opzione?

 A: Sì, Aspose.PDF per .NET ti consente di aggiungere JavaScript a vari elementi del modulo, tra cui caselle di controllo, pulsanti di opzione ed elenchi a discesa. Puoi usare il`JavascriptAction` class per definire azioni JavaScript per diversi elementi del modulo.

#### D: È possibile convalidare l'input dell'utente utilizzando JavaScript nei campi del modulo?

 R: Sì, puoi utilizzare JavaScript per convalidare l'input dell'utente nei campi del modulo. Definendo azioni JavaScript come`OnBlur` O`OnKeystroke` per un campo modulo, è possibile convalidare i dati immessi e visualizzare i messaggi di errore, se necessario.

#### D: Posso eseguire complesse funzioni JavaScript utilizzando Aspose.PDF per .NET?

 R: Sì, puoi eseguire funzioni JavaScript complesse utilizzando Aspose.PDF per .NET. Hai la flessibilità di definire funzioni JavaScript personalizzate e chiamarle all'interno del file`JavascriptAction`.

#### D: Aspose.PDF per .NET supporta eventi JavaScript diversi da quelli menzionati in questo tutorial?

 R: Sì, Aspose.PDF per .NET supporta un'ampia gamma di eventi JavaScript, inclusi`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , E`OnMouseUp`, tra gli altri. Puoi utilizzare questi eventi per attivare azioni JavaScript in base alle interazioni dell'utente.

#### D: Posso utilizzare Aspose.PDF per .NET per estrarre il codice JavaScript da documenti PDF esistenti?

 R: Aspose.PDF per .NET offre la possibilità di estrarre codice JavaScript da documenti PDF esistenti. Puoi usare il`JavascriptAction` class e altri metodi pertinenti per accedere e analizzare le azioni JavaScript in un modulo PDF.