---
title: Fügen Sie eine geordnete HTML-Liste in Dokumente ein
linktitle: Fügen Sie eine HTML-geordnete Liste zu Dokumenten hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine geordnete HTML-Liste zu einem Dokument hinzufügen.
type: docs
weight: 30
url: /de/net/programming-with-text/add-html-ordered-list-into-documents/
---
In diesem Tutorial erfahren Sie, wie Sie mit der Aspose.PDF for .NET-Bibliothek eine geordnete HTML-Liste in ein Dokument einfügen. Der bereitgestellte Code demonstriert die notwendigen Schritte, um diese Aufgabe auszuführen.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie die geordnete HTML-Liste hinzufügen möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis und den Ausgabedateipfad fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

 Suchen Sie als Nächstes die Zeile mit der Aufschrift`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` und ersetzen`"AddHTMLOrderedListIntoDocuments_out.pdf"` mit dem gewünschten Namen für Ihre Ausgabe-PDF-Datei.

## Schritt 4: Erstellen Sie ein neues Dokumentobjekt
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

## Schritt 5: Erstellen Sie ein HtmlFragment-Objekt mit dem HTML-Inhalt
 Instanziieren Sie eine`HtmlFragment` Objekt mit dem HTML-Inhalt, den Sie dem Dokument hinzufügen möchten. Im bereitgestellten Code wird der Variable der HTML-Inhalt zugewiesen`t`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Schritt 6: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 7: Fügen Sie das HtmlFragment zur Seite hinzu
 Ergänzen Sie die`HtmlFragment` Der Seite widersprechen, indem Sie die verwenden`Add` Methode der`Paragraphs` Sammlung.

```csharp
page.Paragraphs.Add(t);
```

## Schritt 8: Speichern Sie das PDF-Dokument
 Speichern Sie die resultierende PDF-Datei mit`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
doc.Save(outFile);
```

### Beispielquellcode für das Hinzufügen einer HTMLOrdered List in Dokumente mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Der Pfad zum Ausgabedokument.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Dokumentobjekt instanziieren
Document doc = new Document();
// Instanziieren Sie das HtmlFragment-Objekt mit dem entsprechenden HTML-Fragment
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Seite zur Pages-Sammlung hinzufügen
Page page = doc.Pages.Add();
// Fügen Sie HtmlFragment innerhalb der Seite hinzu
page.Paragraphs.Add(t);
// Speichern Sie die resultierende PDF-Datei
doc.Save(outFile);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich eine geordnete HTML-Liste in ein Dokument eingefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.

Denken Sie daran, den HTML-Inhalt anzupassen und den Code an Ihre spezifischen Anforderungen anzupassen.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess des Hinzufügens einer geordneten HTML-Liste zu einem Dokument mithilfe der Aspose.PDF für .NET-Bibliothek führen. Es enthält Schritt-für-Schritt-Anleitungen und Codeausschnitte, die Ihnen bei der Bewältigung dieser Aufgabe helfen.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Sie müssen die folgenden Namespaces oben in Ihre Codedatei importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie lege ich das Dokumentverzeichnis und den Ausgabedateipfad fest?

 A: Suchen Sie im Code nach der Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Finden Sie auch die Zeile`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` und ersetzen`"AddHTMLOrderedListIntoDocuments_out.pdf"` mit dem gewünschten Namen der Ausgabe-PDF-Datei.

#### F: Kann ich den HTML-Inhalt anpassen, der dem Dokument hinzugefügt wird?

 A: Auf jeden Fall! In Schritt 5 erstellen Sie eine`HtmlFragment` Objekt benannt`t` das den HTML-Inhalt enthält. Sie können den HTML-Inhalt innerhalb der Backticks an Ihre Anforderungen anpassen.

#### F: Wie füge ich die geordnete HTML-Liste einer Seite im Dokument hinzu?

 A: In Schritt 7 fügen Sie das hinzu`HtmlFragment` Objekt (`t` ) auf die Seite mit dem`Add` Methode der`Paragraphs`Sammlung. Dadurch wird die geordnete HTML-Liste nahtlos in das Dokument integriert.

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den HTML-Inhalt hinzugefügt und auf einer Seite angeordnet haben, können Sie das PDF-Dokument mit speichern`Save` Methode der`Document` Objekt. Stellen Sie sicher, dass Sie den korrekten Ausgabedateipfad angeben, den Sie zuvor festgelegt haben.

#### F: Können Sie eine Zusammenfassung des Beispielquellcodes als Referenz bereitstellen?

A: Auf jeden Fall! Hier ist eine zusammengefasste Version des in diesem Tutorial bereitgestellten Beispielquellcodes:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie erfolgreich gelernt, wie Sie die Bibliothek Aspose.PDF für .NET nutzen können, um eine geordnete HTML-Liste in ein Dokument zu integrieren. Dieses neu gewonnene Wissen kann zur Verbesserung Ihrer Dokumenterstellungs- und Bearbeitungsprozesse eingesetzt werden.