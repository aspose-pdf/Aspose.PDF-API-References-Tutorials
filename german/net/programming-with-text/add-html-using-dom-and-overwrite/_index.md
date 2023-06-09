---
title: Fügen Sie HTML mithilfe von DOM hinzu und überschreiben Sie es
linktitle: Fügen Sie HTML mithilfe von DOM hinzu und überschreiben Sie es
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie HTML-Inhalte mithilfe von DOM in Aspose.PDF für .NET hinzufügen.
type: docs
weight: 50
url: /de/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von HTML-Inhalten mithilfe von DOM (Document Object Model) in Aspose.PDF für .NET. Darüber hinaus erfahren Sie, wie Sie Stile für den HTML-Inhalt überschreiben. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie den HTML-Inhalt hinzufügen möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis und den Ausgabedateipfad fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 4: Erstellen Sie ein neues Dokumentobjekt
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen Sie ein HtmlFragment mit dem HTML-Inhalt
 Instanziieren Sie eine`HtmlFragment` Objekt und stellen den gewünschten HTML-Inhalt bereit. Im bereitgestellten Code wird der Variable der HTML-Inhalt zugewiesen`title`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Schritt 7: Überschreiben Sie die Stile für den HTML-Inhalt
 Um die Stile des HTML-Inhalts zu überschreiben, können Sie die ändern`TextState` Eigenschaften der`HtmlFragment`Objekt. Im bereitgestellten Code wird die Schriftfamilie in „Arial“ geändert und die Schriftgröße auf 20 eingestellt.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Schritt 8: Randinformationen festlegen
Passen Sie bei Bedarf den unteren und oberen Rand des HTML-Fragments an. Im bereitgestellten Code ist der untere Rand auf 10 und der obere Rand auf 400 eingestellt.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Schritt 9: Fügen Sie das HtmlFragment zur Seite hinzu
 Ergänzen Sie die`HtmlFragment` Einspruch gegen die Absätze-Sammlung der Seite einlegen.

```csharp
page.Paragraphs.Add(title);
```

## Schritt 10: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für HTML hinzufügen mit DOM und Überschreiben mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Document doc = new Document();
// Fügen Sie eine Seite zur Seitensammlung der PDF-Datei hinzu
Page page = doc.Pages.Add();
// Instanziieren Sie HtmlFragment mit HTML-Inhalten
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Schriftfamilie von „Verdana“ wird auf „Arial“ zurückgesetzt
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Legen Sie die Informationen zum unteren Rand fest
title.Margin.Bottom = 10;
// Legen Sie die Informationen zum oberen Rand fest
title.Margin.Top = 400;
// Fügen Sie ein HTML-Fragment zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(title);
// PDF-Datei speichern
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
```

## Abschluss
Sie haben erfolgreich HTML-Inhalte mithilfe von DOM in Aspose.PDF für .NET hinzugefügt und die Stile für den HTML-Inhalt überschrieben. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.