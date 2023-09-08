---
title: Appiattire i moduli nel documento PDF
linktitle: Appiattire i moduli nel documento PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Appiattisci facilmente i moduli nel documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-forms/flatten-forms/
---
In questo tutorial, ti mostreremo come appiattire i moduli utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# passo dopo passo per guidarti attraverso questo processo.

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

## Passaggio 3: appiattire i moduli

Per prima cosa controlla se ci sono campi modulo nel documento. In tal caso, scorrere ciascun campo e applicare l'appiattimento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Passaggio 4: salva il documento aggiornato

Salvare il documento PDF aggiornato:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Codice sorgente di esempio per Flatten Forms utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il modulo PDF di origine
Document doc = new Document(dataDir + "input.pdf");
// Forme appiattite
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

In questo tutorial, abbiamo imparato come appiattire i moduli utilizzando Aspose.PDF per .NET. Seguendo questi passaggi, puoi facilmente unire i moduli nei tuoi documenti PDF, rendendo i campi non modificabili e unendo le annotazioni al contenuto del documento.

### Domande frequenti

#### D: Cosa significa "appiattimento di moduli" in Aspose.PDF per .NET?

R: L'appiattimento dei moduli in Aspose.PDF per .NET si riferisce al processo di rendere non modificabili i campi modulo in un documento PDF e di unire annotazioni (come campi modulo, annotazioni e firme digitali) con il contenuto del documento. Una volta appiattiti i moduli, gli utenti non possono modificare i campi modulo e l'aspetto visivo dei campi modulo diventa parte del contenuto statico del documento PDF.

#### D: Posso invertire il processo di appiattimento e rendere nuovamente modificabili i campi del modulo?

R: No, una volta appiattiti i campi del modulo, il processo è irreversibile utilizzando Aspose.PDF per .NET. L'appiattimento unisce in modo permanente l'aspetto dei campi modulo con il contenuto del PDF e i singoli elementi dei campi modulo non sono più accessibili o modificabili.

#### D: Quando devo unire i moduli in un documento PDF?

R: L'appiattimento dei moduli è utile quando si desidera preservare l'aspetto visivo dei campi modulo e delle annotazioni in un documento PDF impedendo al tempo stesso agli utenti di modificare i dati. Questo viene comunemente fatto quando si desidera condividere un documento PDF con dati di moduli precompilati o annotazioni che non devono essere modificate dai destinatari.

#### D: L'appiattimento dei moduli avrà effetto su altre annotazioni, come le firme digitali?

R: Sì, la conversione dei moduli unirà tutte le annotazioni, comprese le firme digitali, al contenuto del PDF. Una volta appiattiti i moduli, eventuali firme digitali esistenti diventeranno parte permanente del documento e gli utenti non potranno modificarle o rimuoverle.

#### D: Posso appiattire selettivamente campi modulo specifici e lasciare gli altri modificabili?

R: Sì, puoi unire selettivamente campi modulo specifici in un documento PDF lasciandone altri modificabili. Invece di utilizzare il codice per unire tutti i campi del modulo, puoi scegliere di unire solo i campi del modulo desiderati in base ai loro nomi o ad altri criteri.