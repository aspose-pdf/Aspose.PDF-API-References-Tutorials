---
title: Incorpora caratteri nel file PDF con la strategia dei sottoinsiemi
linktitle: Incorpora caratteri con la strategia dei sottoinsiemi
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come incorporare i caratteri in un file PDF con la strategia dei sottoinsiemi utilizzando Aspose.PDF per .NET. Ottimizza le dimensioni del tuo PDF incorporando solo i caratteri necessari.
type: docs
weight: 130
url: /it/net/programming-with-document/embedfontsusingsubsetstrategy/
---
In questo tutorial, discuteremo come incorporare i caratteri in un file PDF con una strategia di sottoinsieme utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare documenti PDF a livello di codice. Incorporare i caratteri in un file PDF è un passaggio importante per garantire che il documento venga visualizzato correttamente su dispositivi diversi, indipendentemente dal fatto che i caratteri richiesti siano installati o meno su tali dispositivi.

## Passaggio 1: creare una nuova applicazione console C#
Per iniziare, crea una nuova applicazione console C# in Visual Studio. Puoi chiamarlo come preferisci. Una volta creato il progetto, è necessario aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa lo spazio dei nomi Aspose.PDF
Aggiungi la seguente riga di codice nella parte superiore del file C# per importare lo spazio dei nomi Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Passaggio 3: carica un file PDF esistente
Per incorporare i caratteri in un file PDF esistente, è necessario caricare quel file utilizzando la classe Document. Il codice seguente mostra come caricare un file PDF esistente:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 4: incorpora i caratteri con la strategia del sottoinsieme
Aspose.PDF per .NET fornisce due strategie per l'incorporamento dei caratteri: SubsetAllFonts e SubsetEmbeddedFontsOnly.

La strategia SubsetAllFonts incorporerà tutti i caratteri nel documento come sottoinsieme. Un sottoinsieme è una parte del carattere che contiene solo i caratteri utilizzati nel documento. Questa strategia è utile per ridurre le dimensioni del file del documento PDF.

La strategia SubsetEmbeddedFontsOnly incorporerà solo il sottoinsieme di caratteri già incorporati nel documento. Se un carattere non è incorporato, non sarà interessato da questa strategia.

Il codice seguente mostra come incorporare i caratteri in un file PDF con una strategia di sottoinsieme:

```csharp
// Tutti i caratteri verranno incorporati come sottoinsieme nel documento in caso di SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Il sottoinsieme di caratteri verrà incorporato per i caratteri completamente incorporati, ma i caratteri che non sono incorporati nel documento non saranno interessati.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Passaggio 5: salva il documento PDF
Dopo aver incorporato tutti i caratteri nel file PDF con una strategia di sottoinsieme, è necessario salvare il documento. Il codice seguente mostra come salvare il file PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Codice sorgente di esempio per incorporare caratteri con strategia di sottoinsieme utilizzando Aspose.PDF per .NET. 

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Tutti i caratteri verranno incorporati come sottoinsieme nel documento in caso di SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Il sottoinsieme di caratteri verrà incorporato per i caratteri completamente incorporati, ma i caratteri che non sono incorporati nel documento non saranno interessati.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusione
In questo articolo, abbiamo discusso come incorporare i caratteri in un file PDF con una strategia di sottoinsieme utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET fornisce un'API semplice e facile da usare per lavorare con documenti PDF, inclusa l'aggiunta e l'incorporamento di caratteri con diverse strategie. Incorporare i caratteri in un file PDF è un passaggio importante per garantire che il documento venga visualizzato correttamente su diversi dispositivi e la strategia del sottoinsieme è una funzionalità utile per ridurre le dimensioni del file del documento PDF.

### Domande frequenti per incorporare i caratteri nel file PDF con la strategia dei sottoinsiemi

#### D: Qual è una strategia di sottoinsieme per l'incorporamento dei caratteri in un file PDF?

R: Una strategia di sottoinsieme per l'incorporamento dei caratteri in un file PDF implica che verrà incorporata solo una parte del carattere contenente i caratteri utilizzati nel documento. Ciò aiuta a ridurre le dimensioni del file del documento PDF eliminando i dati dei caratteri non necessari.

#### D: Qual è la differenza tra le strategie SubsetAllFonts e SubsetEmbeddedFontsOnly?

 R: Il`SubsetAllFonts`la strategia incorporerà tutti i caratteri nel documento come sottoinsieme, mentre il file`SubsetEmbeddedFontsOnly` La strategia incorporerà solo il sottoinsieme di caratteri già incorporati nel documento. Quest'ultima strategia non influenzerà i caratteri che non sono già incorporati.

#### D: Perché è importante l'incorporamento dei caratteri con una strategia di sottoinsieme?

R: L'incorporamento dei caratteri con una strategia di sottoinsieme è importante per garantire che il file PDF contenga i dati dei caratteri necessari per visualizzare correttamente il testo, mantenendo allo stesso tempo le dimensioni del file più piccole includendo solo i caratteri utilizzati nel documento.

#### D: Posso utilizzare Aspose.PDF per .NET per incorporare caratteri con strategie diverse?

 R: Sì, Aspose.PDF per .NET fornisce varie strategie per l'incorporamento dei caratteri, inclusi`SubsetAllFonts` E`SubsetEmbeddedFontsOnly`. Puoi scegliere la strategia appropriata in base alle tue esigenze.

#### D: Aspose.PDF per .NET è una libreria affidabile per lavorare con documenti PDF?

R: Sì, Aspose.PDF per .NET è una libreria affidabile e potente per lavorare con documenti PDF. Fornisce funzionalità estese per la creazione, la modifica e la manipolazione di file PDF nelle applicazioni .NET.