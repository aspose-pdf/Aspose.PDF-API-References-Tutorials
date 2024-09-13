---
title: Fügen Sie HTML-geordnete Listen zu Dokumenten hinzu
linktitle: Fügen Sie eine HTML-geordnete Liste zu Dokumenten hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einem Dokument eine geordnete HTML-Liste hinzufügen.
type: docs
weight: 30
url: /de/net/programming-with-text/add-html-ordered-list-into-documents/
---
In diesem Tutorial erfahren Sie, wie Sie mit der Bibliothek Aspose.PDF für .NET eine geordnete HTML-Liste in ein Dokument einfügen. Der bereitgestellte Code zeigt die notwendigen Schritte zum Ausführen dieser Aufgabe.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie die sortierte HTML-Liste einfügen möchten, am Anfang der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Dokumentverzeichnis und Ausgabedateipfad festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

 Suchen Sie als nächstes die Zeile mit dem Inhalt`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` und ersetzen`"AddHTMLOrderedListIntoDocuments_out.pdf"` durch den gewünschten Namen für Ihre Ausgabe-PDF-Datei.

## Schritt 4: Neues Dokumentobjekt erstellen
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document doc = new Document();
```

## Schritt 5: Erstellen Sie ein HtmlFragment-Objekt mit dem HTML-Inhalt
 Instanziieren Sie einen`HtmlFragment` Objekt mit dem HTML-Inhalt, den Sie dem Dokument hinzufügen möchten. Im bereitgestellten Code wird der HTML-Inhalt der Variablen zugewiesen`t`. Sie können den HTML-Inhalt nach Bedarf ändern.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Schritt 6: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 7: Fügen Sie das HtmlFragment zur Seite hinzu
 Fügen Sie den`HtmlFragment` Einspruch gegen die Seite erheben, indem Sie das`Add` Methode der`Paragraphs` Sammlung.

```csharp
page.Paragraphs.Add(t);
```

## Schritt 8: Speichern Sie das PDF-Dokument
 Speichern Sie die resultierende PDF-Datei mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
doc.Save(outFile);
```

### Beispielquellcode zum Hinzufügen einer HTML-geordneten Liste zu Dokumenten mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Der Pfad zum Ausgabedokument.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Document-Objekt instanziieren
Document doc = new Document();
// Instanziieren Sie das HtmlFragment-Objekt mit dem entsprechenden HTML-Fragment
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Seite zur Seitensammlung hinzufügen
Page page = doc.Pages.Add();
// HtmlFragment innerhalb der Seite hinzufügen
page.Paragraphs.Add(t);
//Speichern Sie die resultierende PDF-Datei
doc.Save(outFile);
```

## Abschluss
Sie haben erfolgreich eine geordnete HTML-Liste mit Aspose.PDF für .NET in ein Dokument eingefügt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

Denken Sie daran, den HTML-Inhalt anzupassen und den Code entsprechend Ihren spezifischen Anforderungen anzupassen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Einfügens einer geordneten HTML-Liste in ein Dokument mithilfe der Aspose.PDF-Bibliothek für .NET. Es enthält schrittweise Anleitungen und Codeausschnitte, die Ihnen bei dieser Aufgabe helfen.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Sie müssen die folgenden Namespaces oben in Ihre Codedatei importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis und den Ausgabedateipfad an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Suchen Sie außerdem die Zeile`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` und ersetzen`"AddHTMLOrderedListIntoDocuments_out.pdf"` durch den gewünschten Namen Ihrer PDF-Ausgabedatei.

#### F: Kann ich den HTML-Inhalt anpassen, der dem Dokument hinzugefügt wird?

 A: Auf jeden Fall! In Schritt 5 erstellen Sie eine`HtmlFragment` Objekt mit dem Namen`t` das den HTML-Inhalt enthält. Sie können den HTML-Inhalt innerhalb der Backticks Ihren Anforderungen entsprechend ändern.

#### F: Wie füge ich die sortierte HTML-Liste zu einer Seite im Dokument hinzu?

 A: In Schritt 7 fügen Sie die`HtmlFragment` Objekt (`t` ) zur Seite mit dem`Add` Methode der`Paragraphs` Sammlung. Dadurch wird die HTML-geordnete Liste nahtlos in das Dokument integriert.

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den HTML-Inhalt hinzugefügt und auf einer Seite angeordnet haben, können Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Stellen Sie sicher, dass Sie den korrekten Ausgabedateipfad angeben, den Sie zuvor festgelegt haben.

#### F: Können Sie eine Zusammenfassung des Beispielquellcodes als Referenz bereitstellen?

A: Natürlich! Hier ist eine zusammengefasste Version des Beispielquellcodes aus diesem Tutorial:

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

A: Durch das Durcharbeiten dieses Tutorials haben Sie erfolgreich gelernt, wie Sie die Aspose.PDF-Bibliothek für .NET nutzen können, um eine HTML-geordnete Liste in ein Dokument einzubinden. Dieses neu gewonnene Wissen können Sie anwenden, um Ihre Prozesse zur Dokumenterstellung und -bearbeitung zu verbessern.