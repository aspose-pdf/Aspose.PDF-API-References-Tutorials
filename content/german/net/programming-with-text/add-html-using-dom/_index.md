---
title: HTML mit DOM hinzufügen
linktitle: HTML mit DOM hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit DOM in Aspose.PDF für .NET HTML-Inhalte hinzufügen.
type: docs
weight: 40
url: /de/net/programming-with-text/add-html-using-dom/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von HTML-Inhalten mithilfe von DOM (Document Object Model) in Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

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
```

## Schritt 3: Dokumentverzeichnis und Ausgabedateipfad festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Neues Dokumentobjekt erstellen
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document doc = new Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen Sie ein HtmlFragment mit dem HTML-Inhalt
 Instanziieren Sie einen`HtmlFragment` Objekt und geben Sie den gewünschten HTML-Inhalt an. Im bereitgestellten Code wird der HTML-Inhalt der Variablen zugewiesen`titel`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Schritt 7: Margeninformationen festlegen
Passen Sie bei Bedarf den unteren und oberen Rand des HTML-Fragments an. Im bereitgestellten Code ist der untere Rand auf 10 und der obere Rand auf 200 eingestellt.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Schritt 8: Fügen Sie das HtmlFragment zur Seite hinzu
 Fügen Sie den`HtmlFragment` Objekt zur Absatzsammlung der Seite.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Schritt 9: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
doc.Save(dataDir);
```

## Schritt 10: Erfolgsmeldung anzeigen
Zeigen Sie eine Erfolgsmeldung zusammen mit dem Pfad an, unter dem die PDF-Datei gespeichert wurde.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Hinzufügen von HTML unter Verwendung von DOM mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document-Objekt instanziieren
Document doc = new Document();
// Fügen Sie der Seitensammlung einer PDF-Datei eine Seite hinzu
Page page = doc.Pages.Add();
// Instanziieren Sie HtmlFragment mit HTML-Inhalten
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Informationen zum unteren Rand festlegen
titel.Margin.Bottom = 10;
// Obere Randinformationen festlegen
titel.Margin.Top = 200;
// HTML-Fragment zur Absatzsammlung der Seite hinzufügen
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben erfolgreich HTML-Inhalte mit DOM in Aspose.PDF für .NET hinzugefügt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

### Häufig gestellte Fragen

#### F: Was ist das Ziel dieses Tutorials?

A: Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung zum Hinzufügen von HTML-Inhalten zu einem PDF-Dokument mithilfe des Document Object Model (DOM) in Aspose.PDF für .NET. Es enthält C#-Quellcodeausschnitte, die Ihnen beim Verständnis und der Implementierung des Prozesses helfen.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in die Sie HTML-Inhalte hinzufügen möchten, am Anfang der Datei den folgenden Namespace:

```csharp
using Aspose.Pdf;
```

#### F: Wie gebe ich das Dokumentverzeichnis und den Ausgabedateipfad an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Dokumentobjekt?

 A: Instanziieren Sie in Schritt 4 ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document doc = new Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu, indem Sie`Add` Methode der`Pages` Sammlung:

```csharp
Page page = doc.Pages.Add();
```

#### F: Wie kann ich mithilfe des DOM HTML-Inhalte festlegen?

 A: In Schritt 6 erstellen Sie ein`HtmlFragment` Objekt und weisen Sie ihm Ihren gewünschten HTML-Inhalt zu. Der HTML-Inhalt wird der Variable`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### F: Kann ich den Rand des HTML-Inhalts anpassen?

A: Ja, in Schritt 7 können Sie die unteren und oberen Ränder des HTML-Fragments nach Bedarf anpassen:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### F: Wie füge ich das HTML-Fragment zum PDF-Dokument hinzu?

 A: In Schritt 8 fügen Sie die`HtmlFragment` Objekt (`titel`) zur Absatzsammlung der Seite:

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

A: In diesem Tutorial haben Sie erfolgreich gelernt, wie Sie das Document Object Model (DOM) in Aspose.PDF für .NET nutzen, um HTML-Inhalte zu einem PDF-Dokument hinzuzufügen. Mit diesem Wissen können Sie Ihre PDF-Generierungsfunktionen verbessern.