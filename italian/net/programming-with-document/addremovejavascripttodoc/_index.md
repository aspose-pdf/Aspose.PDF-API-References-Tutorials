---
title: Aggiungi Rimuovi Javascript a Doc
linktitle: Aggiungi Rimuovi Javascript a Doc
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere e rimuovere JavaScript dai documenti PDF utilizzando Aspose.PDF per .NET. Guida dettagliata con esercitazioni sul codice per lo scripting a livello di documento.
type: docs
weight: 30
url: /it/net/programming-with-document/addremovejavascripttodoc/
---

Per aggiungere e rimuovere JavaScript dai documenti PDF, utilizzeremo la libreria Aspose.PDF per .NET. Questa potente libreria ci consente di manipolare i file PDF nelle applicazioni .NET. Segui le istruzioni dettagliate di seguito per aggiungere e rimuovere JavaScript utilizzando Aspose.PDF per .NET.

## Passaggio 1: crea un nuovo documento PDF

 Inizia creando una nuova istanza di`Document` classe fornita da Aspose.PDF per .NET. Questo servirà come documento PDF in cui aggiungeremo il JavaScript.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Passaggio 2: aggiungi JavaScript a livello di documento

 Per aggiungere JavaScript a livello di documento, utilizzare il file`JavaScript` proprietà del`Document` classe. Assegna funzioni JavaScript alle chiavi nel dizionario JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 In questo tutorial, abbiamo aggiunto due funzioni JavaScript,`func1` E`func2`, al documento PDF.

## Passaggio 3: rimuovere JavaScript a livello di documento

 Per rimuovere JavaScript a livello di documento, caricare il documento PDF e accedere al file`JavaScript` dizionario. Scorri le chiavi e rimuovi la funzione JavaScript desiderata.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 In questo tutorial, rimuoviamo il`func1` Funzione JavaScript dal documento PDF.

## Passaggio 4: salvare e verificare le modifiche

Salva il documento PDF modificato e verifica le modifiche.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Questo codice salverà il documento PDF modificato e visualizzerà il messaggio di successo.

### Esempio di codice sorgente per Aggiungi Rimuovi Javascript dai documenti PDF utilizzando Aspose.PDF per .NET

```csharp

            
            // Il percorso della directory dei documenti.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Document doc = new Document();
            doc.Pages.Add();
            doc.JavaScript["func1"] = "function func1() { hello(); }";
            doc.JavaScript["func2"] = "function func2() { hello(); }";
            doc.Save(dataDir + "AddJavascript.pdf");

            // Rimuovi JavaScript a livello di documento
            Document doc1 = new Document(dataDir + "AddJavascript.pdf");
            IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
            Console.WriteLine("=============================== ");
            foreach (string key in keys)
            {
                Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
            }

            doc1.JavaScript.Remove("func1");
            Console.WriteLine("Key 'func1' removed ");
            Console.WriteLine("=============================== ");
            
            Console.WriteLine("\nJavascript added/removed successfully to a document.");
        
```

## Conclusione

In questo articolo, abbiamo fornito una guida passo passo per aggiungere e rimuovere JavaScript dai documenti PDF utilizzando Aspose.PDF per .NET. Seguendo le istruzioni e utilizzando i tutorial sul codice forniti, puoi facilmente incorporare JavaScript nei tuoi documenti PDF e rimuoverlo quando necessario. JavaScript abilita la funzionalità dinamica e l'interattività nei tuoi file PDF, migliorando l'esperienza dell'utente.