---
title: Imposta lingua e titolo
linktitle: Imposta lingua e titolo
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo passo per configurare la lingua e il titolo di un documento PDF con Aspose.PDF per .NET. Crea documenti multilingue personalizzati.
type: docs
weight: 140
url: /it/net/programming-with-tagged-pdf/setup-language-and-title/
---
In questa guida, ti spiegheremo come configurare la lingua e il titolo di un documento PDF utilizzando la libreria Aspose.PDF per .NET. Aspose.PDF è una potente libreria che ti consente di creare, manipolare e convertire file PDF in modo programmatico.

Immergiamoci nel codice e impariamo come configurare la lingua e il titolo di un documento PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di iniziare, assicurati di aver installato Aspose.PDF per .NET e di configurare il tuo ambiente di sviluppo.

## Passaggio 1: creazione del documento

 Il primo passaggio consiste nel creare un nuovo documento PDF utilizzando il file`Document` classe.

```csharp
// Crea il documento PDF
Document document = new Document();
```

## Passaggio 2: accedi ai contenuti contrassegnati

 Successivamente, accediamo al contenuto con tag del documento utilizzando il file`ITaggedContent` oggetto.

```csharp
//Accedi ai contenuti contrassegnati
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Passaggio 3: imposta il titolo e la lingua

 Ora possiamo impostare il titolo e la lingua del documento utilizzando il file`SetTitle` E`SetLanguage` metodi del`ITaggedContent` oggetto.

```csharp
// Definire il titolo del documento
taggedContent.SetTitle("Example of tagged document");

// Imposta la lingua del documento
taggedContent.SetLanguage("fr-FR");
```

## Passaggio 4: aggiungi contenuto multilingue

Successivamente, aggiungiamo contenuto multilingue al documento utilizzando elementi di paragrafo per ciascuna lingua.

```csharp
// Aggiungi un paragrafo in inglese
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Aggiungi un paragrafo in tedesco
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Aggiungi un paragrafo in francese
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Aggiungi un paragrafo in spagnolo
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Passaggio 5: salvare il documento PDF con tag

Infine, salviamo il documento PDF con tag.

```csharp
// Salva il documento PDF con tag
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Esempio di codice sorgente per l'impostazione della lingua e del titolo utilizzando Aspose.PDF per .NET 
```csharp

Document document = new Document();

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ottieni contenuti contrassegnati
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Imposta titolo e lingua
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Intestazione (en-US, ereditata dal documento)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragrafo (inglese)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragrafo (tedesco)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragrafo (francese)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragrafo (spagnolo)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Salva documento PDF con tag
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Conclusione

Congratulazioni! Ora sai come configurare la lingua e il titolo di un documento PDF utilizzando Aspose.PDF per .NET. Puoi esplorare ulteriormente le funzionalità di Aspose.PDF per creare documenti PDF personalizzati e multilingue.
