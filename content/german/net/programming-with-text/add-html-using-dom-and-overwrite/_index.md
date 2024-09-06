---
title: HTML mit DOM hinzufügen und PDF überschreiben
linktitle: HTML mit DOM hinzufügen und überschreiben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit DOM und PDF-Überschreiben in Aspose.PDF für .NET HTML-Inhalte hinzufügen.
type: docs
weight: 50
url: /de/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von HTML-Inhalten mithilfe von DOM (Document Object Model) in Aspose.PDF für .NET. Darüber hinaus erfahren Sie, wie Sie Stile für den HTML-Inhalt überschreiben. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie den HTML-Inhalt einfügen möchten, am Anfang der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Dokumentverzeichnis und Ausgabedateipfad festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 4: Neues Dokumentobjekt erstellen
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document doc = new Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen Sie ein HtmlFragment mit dem HTML-Inhalt
 Instanziieren Sie einen`HtmlFragment` Objekt und geben Sie den gewünschten HTML-Inhalt an. Im bereitgestellten Code wird der HTML-Inhalt der Variablen zugewiesen`title`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Schritt 7: Überschreiben Sie die Stile für den HTML-Inhalt
 Um die Stile des HTML-Inhalts zu überschreiben, können Sie die`TextState` Eigenschaften der`HtmlFragment` Objekt. Im bereitgestellten Code wird die Schriftfamilie in „Arial“ geändert und die Schriftgröße auf 20 festgelegt.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Schritt 8: Margeninformationen festlegen
Passen Sie bei Bedarf die unteren und oberen Ränder des HTML-Fragments an. Im bereitgestellten Code ist der untere Rand auf 10 und der obere Rand auf 400 eingestellt.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Schritt 9: Fügen Sie das HtmlFragment zur Seite hinzu
 Fügen Sie den`HtmlFragment` Objekt zur Absatzsammlung der Seite.

```csharp
page.Paragraphs.Add(title);
```

## Schritt 10: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode zum Hinzufügen von HTML unter Verwendung von DOM und zum Überschreiben unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document-Objekt instanziieren
Document doc = new Document();
// Fügen Sie der Seitensammlung einer PDF-Datei eine Seite hinzu
Page page = doc.Pages.Add();
// Instanziieren Sie HtmlFragment mit HTML-Inhalten
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Schriftfamilie von „Verdana“ wird auf „Arial“ zurückgesetzt
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Informationen zum unteren Rand festlegen
title.Margin.Bottom = 10;
// Obere Randinformationen festlegen
title.Margin.Top = 400;
// HTML-Fragment zur Absatzsammlung der Seite hinzufügen
page.Paragraphs.Add(title);
// PDF-Datei speichern
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
```

## Abschluss
Sie haben erfolgreich HTML-Inhalte mit DOM in Aspose.PDF für .NET hinzugefügt und die Stile für die HTML-Inhalte überschrieben. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

### Häufig gestellte Fragen

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von HTML-Inhalten zu einem PDF-Dokument mithilfe des Document Object Model (DOM) in Aspose.PDF für .NET. Darüber hinaus erfahren Sie, wie Sie Stile für den HTML-Inhalt überschreiben, sodass Sie dessen Erscheinungsbild anpassen können. Das Tutorial enthält C#-Quellcodeausschnitte, um die erforderlichen Schritte zu demonstrieren.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in die Sie HTML-Inhalte hinzufügen möchten, am Anfang der Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis und den Ausgabedateipfad an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Dokumentobjekt?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mit der folgenden Codezeile:

```csharp
Document doc = new Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu, indem Sie`Add` Methode der`Pages` Sammlung:

```csharp
Page page = doc.Pages.Add();
```

#### F: Wie kann ich mithilfe des DOM HTML-Inhalte festlegen?

 A: In Schritt 6 erstellen Sie ein`HtmlFragment` Objekt und weisen Sie ihm Ihren gewünschten HTML-Inhalt zu. Der HTML-Inhalt wird der Variable`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### F: Wie kann ich die Stile des HTML-Inhalts überschreiben?

 A: In Schritt 7 überschreiben Sie die Stile des HTML-Inhalts, indem Sie die`TextState` Eigenschaften der`HtmlFragment` Objekt. Sie können beispielsweise die Schriftfamilie in „Arial“ ändern und die Schriftgröße auf 20 festlegen:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### F: Kann ich den Rand des HTML-Inhalts anpassen?

A: Ja, in Schritt 8 können Sie die unteren und oberen Ränder des HTML-Fragments nach Bedarf anpassen:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### F: Wie füge ich das HTML-Fragment zum PDF-Dokument hinzu?

 A: In Schritt 9 fügen Sie die`HtmlFragment` Objekt (`title`) zur Absatzsammlung der Seite:

```csharp
page.Paragraphs.Add(title);
```

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den HTML-Inhalt hinzugefügt und seine Stile angepasst haben, verwenden Sie die`Save` Methode der`Document` Objekt zum Speichern des PDF-Dokuments:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie erfolgreich gelernt, wie Sie HTML-Inhalte mithilfe des Document Object Model (DOM) in Aspose.PDF für .NET integrieren. Darüber hinaus haben Sie die Möglichkeit erhalten, Stile zu überschreiben, um das Erscheinungsbild des HTML-Inhalts im resultierenden PDF-Dokument anzupassen.