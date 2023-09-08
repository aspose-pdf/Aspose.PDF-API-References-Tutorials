---
title: Fügen Sie HTML mithilfe von DOM hinzu
linktitle: Fügen Sie HTML mithilfe von DOM hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie HTML-Inhalte mithilfe von DOM in Aspose.PDF für .NET hinzufügen.
type: docs
weight: 40
url: /de/net/programming-with-text/add-html-using-dom/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von HTML-Inhalten mithilfe von DOM (Document Object Model) in Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

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
```

## Schritt 3: Legen Sie das Dokumentverzeichnis und den Ausgabedateipfad fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie ein neues Dokumentobjekt
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen Sie ein HtmlFragment mit dem HTML-Inhalt
 Instanziieren Sie eine`HtmlFragment` Objekt und stellen den gewünschten HTML-Inhalt bereit. Im bereitgestellten Code wird der Variable der HTML-Inhalt zugewiesen`titel`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Schritt 7: Randinformationen festlegen
Passen Sie bei Bedarf den unteren und oberen Rand des HTML-Fragments an. Im bereitgestellten Code ist der untere Rand auf 10 und der obere Rand auf 200 festgelegt.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Schritt 8: Fügen Sie das HtmlFragment zur Seite hinzu
 Ergänzen Sie die`HtmlFragment` Einspruch gegen die Absätze-Sammlung der Seite einlegen.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Schritt 9: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
doc.Save(dataDir);
```

## Schritt 10: Erfolgsmeldung anzeigen
Zeigen Sie eine Erfolgsmeldung zusammen mit dem Pfad an, in dem die PDF-Datei gespeichert wurde.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für Add HTMLUsing DOM mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Document doc = new Document();
// Fügen Sie eine Seite zur Seitensammlung der PDF-Datei hinzu
Page page = doc.Pages.Add();
// Instanziieren Sie HtmlFragment mit HTML-Inhalten
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Legen Sie die Informationen zum unteren Rand fest
titel.Margin.Bottom = 10;
// Legen Sie die Informationen zum oberen Rand fest
titel.Margin.Top = 200;
// Fügen Sie ein HTML-Fragment zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben erfolgreich HTML-Inhalte mithilfe von DOM in Aspose.PDF für .NET hinzugefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.

### FAQs

#### F: Was ist das Ziel dieses Tutorials?

A: Dieses Tutorial soll eine Schritt-für-Schritt-Anleitung zum Hinzufügen von HTML-Inhalten zu einem PDF-Dokument mithilfe des Document Object Model (DOM) in Aspose.PDF für .NET bieten. Es enthält C#-Quellcodeausschnitte, die Ihnen helfen, den Prozess zu verstehen und zu implementieren.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie HTML-Inhalte hinzufügen möchten, den folgenden Namespace am Anfang der Datei:

```csharp
using Aspose.Pdf;
```

#### F: Wie lege ich das Dokumentverzeichnis und den Ausgabedateipfad fest?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Document-Objekt?

 A: Instanziieren Sie in Schritt 4 eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu`Add` Methode der`Pages` Sammlung:

```csharp
Page page = doc.Pages.Add();
```

#### F: Wie kann ich HTML-Inhalte mithilfe des DOM festlegen?

 A: In Schritt 6 erstellen Sie eine`HtmlFragment` Objekt und weisen Sie ihm Ihren gewünschten HTML-Inhalt zu. Der Variable wird der HTML-Inhalt zugewiesen`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### F: Kann ich den Rand des HTML-Inhalts anpassen?

A: Ja, in Schritt 7 können Sie den unteren und oberen Rand des HTML-Fragments nach Bedarf anpassen:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### F: Wie füge ich das HTMLFragment zum PDF-Dokument hinzu?

 A: In Schritt 8 fügen Sie das hinzu`HtmlFragment` Objekt (`titel`) zur Absatzsammlung der Seite:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den HTML-Inhalt hinzugefügt und die Ränder angepasst haben, verwenden Sie die`Save` Methode der`Document` Objekt zum Speichern des PDF-Dokuments:

```csharp
doc.Save(dataDir);
```

#### F: Gibt es eine Möglichkeit zu überprüfen, ob der Vorgang erfolgreich war?

A: Natürlich wird in Schritt 10 eine Erfolgsmeldung zusammen mit dem Pfad angezeigt, in dem die PDF-Datei gespeichert wurde:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie erfolgreich gelernt, wie Sie das Document Object Model (DOM) in Aspose.PDF für .NET verwenden, um HTML-Inhalte zu einem PDF-Dokument hinzuzufügen. Dieses Wissen versetzt Sie in die Lage, Ihre Möglichkeiten zur PDF-Generierung zu verbessern.