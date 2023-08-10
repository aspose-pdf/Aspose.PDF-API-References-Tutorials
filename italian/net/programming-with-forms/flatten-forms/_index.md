---
title: Appiattire i moduli nel documento PDF
linktitle: Appiattire i moduli nel documento PDF
second_title: Aspose.PDF per riferimento API .NET
description: Appiattisci facilmente i moduli nel documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-forms/flatten-forms/
---
In questo tutorial, ti mostreremo come appiattire i moduli usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

## Passaggio 1: preparazione

Innanzitutto, assicurati di aver importato le librerie necessarie e di impostare il percorso della directory dei documenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il modulo PDF di origine

Carica il modulo PDF di origine:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 3: appiattisci le forme

Innanzitutto controlla se ci sono campi modulo nel documento. In tal caso, scorrere ogni campo e applicare l'appiattimento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Passaggio 4: salvare il documento aggiornato

Salva il documento PDF aggiornato:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per Flatten Forms utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il modulo PDF di origine
Document doc = new Document(dataDir + "input.pdf");
// Appiattire le forme
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Salva il documento aggiornato
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusione

In questo tutorial, abbiamo imparato come appiattire i moduli utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente appiattire i moduli nei tuoi documenti PDF, rendendo i campi non modificabili e unendo le annotazioni con il contenuto del documento.

### FAQ

#### D: Cosa significa "formi appiattiti" in Aspose.PDF per .NET?

R: L'appiattimento dei moduli in Aspose.PDF per .NET si riferisce al processo di rendere i campi modulo in un documento PDF non modificabili e unire le annotazioni (come campi modulo, annotazioni e firme digitali) con il contenuto del documento. Una volta appiattiti i moduli, gli utenti non possono modificare i campi del modulo e l'aspetto visivo dei campi del modulo diventa parte del contenuto statico del documento PDF.

#### D: Posso invertire il processo di appiattimento e rendere nuovamente modificabili i campi del modulo?

R: No, una volta appiattiti i campi del modulo, il processo è irreversibile utilizzando Aspose.PDF per .NET. L'appiattimento unisce in modo permanente l'aspetto dei campi modulo con il contenuto del PDF e i singoli elementi del campo modulo non sono più accessibili o modificabili.

#### D: Quando devo appiattire i moduli in un documento PDF?

R: L'appiattimento dei moduli è utile quando si desidera preservare l'aspetto visivo dei campi modulo e delle annotazioni in un documento PDF, impedendo agli utenti di modificare i dati. Questa operazione viene comunemente eseguita quando si desidera condividere un documento PDF con dati di moduli precompilati o annotazioni che non devono essere modificate dai destinatari.

#### D: L'appiattimento dei moduli influirà su altre annotazioni, come le firme digitali?

R: Sì, l'appiattimento dei moduli unirà tutte le annotazioni, incluse le firme digitali, con il contenuto del PDF. Una volta appiattiti i moduli, eventuali firme digitali esistenti diventeranno parte permanente del documento e gli utenti non potranno modificarle o rimuoverle.

#### D: Posso appiattire in modo selettivo campi modulo specifici e lasciare gli altri modificabili?

R: Sì, puoi appiattire in modo selettivo campi modulo specifici in un documento PDF lasciandone altri modificabili. Invece di utilizzare il codice per appiattire tutti i campi del modulo, puoi scegliere di appiattire solo i campi del modulo desiderati in base ai loro nomi o ad altri criteri.