---
title: Rimuovi i collegamenti ipertestuali dopo la conversione da HTML
linktitle: Rimuovi i collegamenti ipertestuali dopo la conversione da HTML
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per rimuovere i collegamenti ipertestuali dopo aver convertito HTML in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 250
url: /it/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
In questo tutorial ti guideremo attraverso il processo di rimozione dei collegamenti ipertestuali da un file PDF generato da un file HTML utilizzando Aspose.PDF per .NET. I collegamenti ipertestuali sono collegamenti cliccabili che possono reindirizzare ad altre pagine o siti Web. Seguendo i passaggi seguenti, sarai in grado di rimuovere i collegamenti ipertestuali dal file PDF risultante.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del file HTML e rimozione dei collegamenti ipertestuali
questo punto, caricheremo il file HTML e rimuoveremo i collegamenti ipertestuali dal documento PDF risultante. Utilizza il seguente codice:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il file HTML utilizzando le opzioni di caricamento HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Sfoglia le annotazioni della prima pagina del documento
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Controlla se l'annotazione è un collegamento
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Controlla se l'azione è di tipo GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Utilizzare un assorbitore di frammenti di testo per trovare frammenti di testo corrispondenti
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Passa in rassegna i frammenti di testo corrispondenti e rimuovi gli attributi dai collegamenti ipertestuali
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Rimuovi l'annotazione dalla pagina
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file HTML.

## Passaggio 2: salvataggio del file PDF risultante
Infine, salveremo il file PDF risultante senza i collegamenti ipertestuali. Utilizza il seguente codice:

```csharp
// Salva il file PDF risultante
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Il codice sopra salva il file PDF risultante con il nome file`"RemoveHyperlinksFromText_out.pdf"`.

### Codice sorgente di esempio per rimuovere i collegamenti ipertestuali dopo la conversione da Html utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo trattato il processo passo passo di rimozione dei collegamenti ipertestuali da un file PDF generato da un file HTML utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, sarai in grado di rimuovere con successo i collegamenti ipertestuali dal file PDF risultante.

### Domande frequenti

#### D: Cos'è Aspose.PDF per .NET?

R: Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di lavorare con documenti PDF in applicazioni C#. Offre un'ampia gamma di funzionalità, inclusa la possibilità di convertire file HTML in PDF e manipolare il contenuto PDF.

#### D: Perché dovrei rimuovere i collegamenti ipertestuali da un file PDF?

R: Esistono vari motivi per rimuovere i collegamenti ipertestuali da un file PDF. Ad esempio, potresti voler eliminare i collegamenti esterni per scopi di stampa o archiviazione o garantire che il contenuto del PDF non sia navigabile tramite collegamenti ipertestuali.

#### D: Come posso caricare un file HTML e rimuovere i collegamenti ipertestuali utilizzando Aspose.PDF per .NET?

 R: Per caricare un file HTML e rimuovere i collegamenti ipertestuali, è possibile utilizzare Aspose.PDF per .NET`HtmlLoadOptions` classe. Scorri le annotazioni delle pagine PDF per trovare le annotazioni dei collegamenti e modificarne gli attributi.

#### D: Posso personalizzare il nome del file di output per il PDF risultante?

R: Sì, puoi personalizzare il nome del file di output per il file PDF risultante modificando il codice che salva il documento PDF. Basta cambiare il nome del file desiderato nel file`doc.Save()` metodo.

#### D: È possibile rimuovere selettivamente i collegamenti ipertestuali in base a determinati criteri?

R: Sì, puoi rimuovere selettivamente i collegamenti ipertestuali in base a criteri specifici. Ad esempio, puoi scegliere di rimuovere solo i collegamenti esterni o i collegamenti che puntano a URL specifici.