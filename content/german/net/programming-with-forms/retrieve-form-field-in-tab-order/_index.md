---
title: Formularfeld in Tab-Reihenfolge abrufen
linktitle: Formularfeld in Tab-Reihenfolge abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Formularfelder in Tab-Reihenfolge abrufen.
type: docs
weight: 240
url: /de/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Beim Arbeiten mit PDF-Dokumenten in C# unter Verwendung von Aspose.PDF für .NET stoßen Sie möglicherweise auf ein Szenario, in dem Sie Formularfelder in einer bestimmten Tab-Reihenfolge abrufen müssen. Dies kann nützlich sein, wenn Sie Operationen an Formularfeldern basierend auf ihrer Tabulatorreihenfolge ausführen möchten. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Abrufen von Formularfeldern in Tab-Reihenfolge mit Aspose.PDF für .NET.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Visual Studio ist auf Ihrem System installiert
- Aspose.PDF für .NET-Bibliothek installiert

Lassen Sie uns nun in die Schritte zum Abrufen von Formularfeldern in Tab-Reihenfolge eintauchen.

## Schritt 1: Festlegen des Dokumentenverzeichnisses

 Zunächst müssen Sie das Dokumentverzeichnis festlegen, in dem sich Ihr PDF-Dokument befindet. Sie können dies tun, indem Sie den Pfad zum Verzeichnis im angeben`dataDir` Variable.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Laden des PDF-Dokuments

 In diesem Schritt laden wir das PDF-Dokument mit Aspose.PDF für .NET. Der`Document` Die Klasse bietet die Möglichkeit, PDF-Dokumente zu laden und zu bearbeiten.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Hier,`"Test2.pdf"`ist der Name des PDF-Dokuments, das Sie laden möchten. Stellen Sie sicher, dass das Dokument im angegebenen Dokumentverzeichnis vorhanden ist.

## Schritt 3: Formularfelder in Tab-Reihenfolge abrufen

 Um Formularfelder in Tab-Reihenfolge abzurufen, müssen wir auf zugreifen`FieldsInTabOrder` Eigentum der`Page` Klasse. Diese Eigenschaft gibt eine Liste von Formularfeldern zurück, sortiert nach ihrer Tabulatorreihenfolge.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Im obigen Codeausschnitt rufen wir die Formularfelder von der zweiten Seite ab (`doc.Pages[1]` ) und durchlaufen Sie jedes Feld, um deren Teilnamen zu verketten`s` Variable. Sie können dieses Code-Snippet entsprechend Ihren spezifischen Anforderungen ändern.

## Schritt 4: Ändern der Tab-Reihenfolge

 Wenn Sie die Tab-Reihenfolge von Formularfeldern ändern möchten, können Sie dies tun, indem Sie auf zugreifen`TabOrder` Eigenschaft jedes Felds und Zuweisen eines neuen Tab-Reihenfolgewerts. Hier ist ein Beispiel:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Im obigen Codeausschnitt weisen wir drei Formularfeldern neue Tab-Reihenfolgewerte zu (`doc.Form[3]`, `doc.Form[1]` , Und`doc.Form[2]`). Passen Sie die Feldindizes und Tab-Reihenfolgewerte entsprechend Ihren spezifischen Anforderungen an.

## Schritt 5: Speichern des geänderten Dokuments

 Nachdem Sie die Tab-Reihenfolge der Formularfelder geändert haben, müssen Sie das geänderte Dokument speichern. Sie können dies mit dem tun`Save` Methode der`Document` Klasse.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Hier,`"39522_out.pdf"` ist der Name der Ausgabedatei, in der das geänderte Dokument gespeichert wird. Geben Sie den gewünschten Namen und Speicherort für die Ausgabedatei an.

### Beispielquellcode für „Formularfeld in Tab-Reihenfolge abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Formularfelder in Tab-Reihenfolge abruft. Wir haben die Schritte zum Laden eines PDF-Dokuments, zum Abrufen von Formularfeldern in der Tab-Reihenfolge, zum Ändern der Tab-Reihenfolge und zum Speichern des geänderten Dokuments behandelt. Wenn Sie diese Schritte befolgen, können Sie effizient mit Formularfeldern arbeiten und deren Tabulatorreihenfolge an Ihre Anforderungen anpassen.


### FAQs

#### F: Wie kann ich die abgerufenen Formularfelder in meinem C#-Code zur weiteren Verarbeitung verwenden?

 A: Sie können die abgerufenen Formularfelder in Ihrem C#-Code verwenden, indem Sie auf deren Eigenschaften zugreifen, z`Value`, `Name`, `Rect`usw. Mit diesen Eigenschaften können Sie die Formularfelddaten nach Bedarf lesen und ändern.

#### F: Kann ich Formularfelder von allen Seiten des PDF-Dokuments in Tab-Reihenfolge abrufen?

 A: Ja, Sie können Formularfelder von allen Seiten des PDF-Dokuments abrufen, indem Sie jede Seite durchlaufen und auf die zugreifen`FieldsInTabOrder` Eigenschaft wie im Tutorial gezeigt. Dadurch erhalten Sie Formularfelder sortiert nach ihrer Tabulatorreihenfolge auf allen Seiten.

#### F: Ist es möglich, nur bestimmte Arten von Formularfeldern, z. B. Textfelder oder Kontrollkästchen, in Tab-Reihenfolge abzurufen?

A: Ja, Sie können Formularfelder nach ihrem Typ filtern, z. B. Textfelder oder Kontrollkästchen, nachdem Sie sie in Tab-Reihenfolge abgerufen haben. Sie können bedingte Anweisungen verwenden, um den Typ jedes Formularfelds zu überprüfen und es entsprechend zu verarbeiten.

#### F: Kann ich Formularfelder anhand ihrer Namen statt anhand der Tab-Reihenfolge abrufen?

 A: Ja, Sie können Formularfelder anhand ihrer Namen abrufen, indem Sie die verwenden`doc.Form` Sammlung und Angabe des Feldnamens als Index. Zum Beispiel,`doc.Form["fieldName"]`ruft das Formularfeld mit dem angegebenen Namen ab.

#### F: Unterstützt Aspose.PDF für .NET die Arbeit mit verschlüsselten PDF-Dokumenten?

A: Ja, Aspose.PDF für .NET bietet Unterstützung für die Arbeit mit verschlüsselten PDF-Dokumenten. Sie können verschlüsselte PDF-Dateien mit geeigneten Passwortparametern laden und bearbeiten.