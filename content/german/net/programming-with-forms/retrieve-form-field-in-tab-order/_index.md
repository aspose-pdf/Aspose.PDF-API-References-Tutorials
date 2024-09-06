---
title: Formularfeld in Tabulatorreihenfolge abrufen
linktitle: Formularfeld in Tabulatorreihenfolge abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Formularfelder in der Tabulatorreihenfolge abrufen.
type: docs
weight: 240
url: /de/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Wenn Sie mit PDF-Dokumenten in C# unter Verwendung von Aspose.PDF für .NET arbeiten, stoßen Sie möglicherweise auf ein Szenario, in dem Sie Formularfelder in einer bestimmten Tabulatorreihenfolge abrufen müssen. Dies kann nützlich sein, wenn Sie Vorgänge an Formularfeldern basierend auf ihrer Tabulatorreihenfolge durchführen möchten. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Abrufen von Formularfeldern in der Tabulatorreihenfolge unter Verwendung von Aspose.PDF für .NET.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Visual Studio auf Ihrem System installiert
- Aspose.PDF für .NET-Bibliothek installiert

Sehen wir uns nun die Schritte zum Abrufen von Formularfeldern in der Tabulatorreihenfolge an.

## Schritt 1: Festlegen des Dokumentverzeichnisses

 Zunächst müssen Sie das Dokumentverzeichnis festlegen, in dem sich Ihr PDF-Dokument befindet. Sie können dies tun, indem Sie den Pfad zum Verzeichnis im`dataDir` Variable.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Laden des PDF-Dokuments

 In diesem Schritt laden wir das PDF-Dokument mit Aspose.PDF für .NET. Das`Document` Klasse bietet die Möglichkeit, PDF-Dokumente zu laden und zu bearbeiten.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Hier,`"Test2.pdf"`ist der Name des PDF-Dokuments, das Sie laden möchten. Stellen Sie sicher, dass das Dokument im angegebenen Dokumentverzeichnis vorhanden ist.

## Schritt 3: Abrufen von Formularfeldern in der Tabulatorreihenfolge

 Um Formularfelder in der Tabulatorreihenfolge abzurufen, müssen wir auf die`FieldsInTabOrder` Eigentum der`Page` Klasse. Diese Eigenschaft gibt eine Liste von Formularfeldern zurück, sortiert nach ihrer Tabulatorreihenfolge.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Im obigen Codeausschnitt rufen wir die Formularfelder von der zweiten Seite ab (`doc.Pages[1]` ) und durchlaufen Sie jedes Feld, um die Teilnamen zu verketten.`s` Variable. Sie können diesen Codeausschnitt Ihren spezifischen Anforderungen entsprechend ändern.

## Schritt 4: Ändern der Tabulatorreihenfolge

 Wenn Sie die Tabulatorreihenfolge von Formularfeldern ändern möchten, können Sie dies tun, indem Sie auf`TabOrder` -Eigenschaft jedes Felds und Zuweisen eines neuen Tabulatorreihenfolgewerts. Hier ist ein Beispiel:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Im obigen Codeausschnitt weisen wir drei Formularfeldern neue Tab-Reihenfolgewerte zu (`doc.Form[3]`, `doc.Form[1]` , Und`doc.Form[2]`). Passen Sie die Feldindizes und Tabulatorreihenfolgewerte Ihren spezifischen Anforderungen an.

## Schritt 5: Speichern des geänderten Dokuments

 Nachdem Sie die Tabulatorreihenfolge von Formularfeldern geändert haben, müssen Sie das geänderte Dokument speichern. Dies können Sie mit dem`Save` Methode der`Document` Klasse.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Hier,`"39522_out.pdf"` ist der Name der Ausgabedatei, in der das geänderte Dokument gespeichert wird. Geben Sie den gewünschten Namen und Speicherort für die Ausgabedatei an.

### Beispielquellcode zum Abrufen von Formularfeldern in der Tabulatorreihenfolge mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Formularfelder in Tabulatorreihenfolge mit Aspose.PDF für .NET abruft. Wir haben die Schritte zum Laden eines PDF-Dokuments, zum Abrufen von Formularfeldern in Tabulatorreihenfolge, zum Ändern der Tabulatorreihenfolge und zum Speichern des geänderten Dokuments behandelt. Wenn Sie diese Schritte befolgen, können Sie effizient mit Formularfeldern arbeiten und deren Tabulatorreihenfolge nach Ihren Anforderungen anpassen.


### Häufig gestellte Fragen

#### F: Wie kann ich die abgerufenen Formularfelder in meinem C#-Code zur weiteren Verarbeitung verwenden?

 A: Sie können die abgerufenen Formularfelder in Ihrem C#-Code verwenden, indem Sie auf deren Eigenschaften zugreifen, wie z. B.`Value`, `Name`, `Rect`usw. Diese Eigenschaften ermöglichen Ihnen, die Formularfelddaten nach Bedarf zu lesen und zu ändern.

#### F: Kann ich Formularfelder von allen Seiten des PDF-Dokuments in der Tabulatorreihenfolge abrufen?

 A: Ja, Sie können Formularfelder von allen Seiten des PDF-Dokuments abrufen, indem Sie jede Seite durchlaufen und auf die`FieldsInTabOrder` Eigenschaft, wie im Tutorial gezeigt. Dadurch erhalten Sie Formularfelder, die auf allen Seiten nach ihrer Tabulatorreihenfolge sortiert sind.

#### F: Ist es möglich, nur bestimmte Typen von Formularfeldern, wie etwa Textfelder oder Kontrollkästchen, in der Tabulatorreihenfolge abzurufen?

A: Ja, Sie können Formularfelder nach ihrem Typ filtern, z. B. nach Textfeldern oder Kontrollkästchen, nachdem Sie sie in der Tabulatorreihenfolge abgerufen haben. Sie können bedingte Anweisungen verwenden, um den Typ jedes Formularfelds zu überprüfen und sie entsprechend zu verarbeiten.

#### F: Kann ich Formularfelder anhand ihres Namens statt anhand der Tabulatorreihenfolge abrufen?

 A: Ja, Sie können Formularfelder anhand ihres Namens abrufen, indem Sie das`doc.Form` Sammlung und Angabe des Feldnamens als Index. Beispiel:`doc.Form["fieldName"]`ruft das Formularfeld mit dem angegebenen Namen ab.

#### F: Unterstützt Aspose.PDF für .NET die Arbeit mit verschlüsselten PDF-Dokumenten?

A: Ja, Aspose.PDF für .NET unterstützt die Arbeit mit verschlüsselten PDF-Dokumenten. Sie können verschlüsselte PDF-Dateien mit entsprechenden Kennwortparametern laden und bearbeiten.