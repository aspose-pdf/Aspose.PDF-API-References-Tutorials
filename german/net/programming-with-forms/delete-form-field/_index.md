---
title: Formularfeld im PDF-Dokument löschen
linktitle: Formularfeld im PDF-Dokument löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Entfernen Sie mit Aspose.PDF für .NET ganz einfach unerwünschte Formularfelder in PDF-Dokumenten.
type: docs
weight: 50
url: /de/net/programming-with-forms/delete-form-field/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie ein Formularfeld mit Aspose.PDF für .NET löschen. Wir erklären Ihnen Schritt für Schritt den C#-Quellcode, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben und legen Sie den Pfad zum Dokumentenverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Schritt 3: Löschen Sie ein bestimmtes Feld

Löschen Sie ein bestimmtes Formularfeld anhand seines Namens:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Schritt 4: Speichern Sie das bearbeitete Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für „Formularfeld löschen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Löschen Sie ein bestimmtes Feld nach Namen
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Geändertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man ein Formularfeld mit Aspose.PDF für .NET löscht. Wenn Sie diese Schritte befolgen, können Sie mithilfe von Aspose.PDF problemlos unerwünschte Formularfelder aus Ihren PDF-Dokumenten entfernen.

### FAQs

#### F: Kann ich mit Aspose.PDF für .NET mehrere Formularfelder gleichzeitig löschen?

 A: Ja, Sie können mit Aspose.PDF für .NET mehrere Formularfelder gleichzeitig löschen. Rufen Sie einfach an`Delete` Methode für jedes Formularfeld, das Sie entfernen möchten.

#### F: Wie kann ich prüfen, ob ein Formularfeld vorhanden ist, bevor ich versuche, es zu löschen?

 A: Sie können überprüfen, ob ein Formularfeld vorhanden ist, bevor Sie versuchen, es zu löschen, indem Sie verwenden`Contains` Methode der`Form` Eigentum. Zum Beispiel:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### F: Was passiert, wenn ich versuche, ein Formularfeld zu löschen, das im PDF-Dokument nicht vorhanden ist?

 A: Wenn Sie versuchen, ein Formularfeld zu löschen, das im PDF-Dokument nicht vorhanden ist, wird das`Delete` Die Methode löst keinen Fehler oder keine Ausnahme aus. Es wird einfach nichts passieren, da kein Feld zum Löschen vorhanden ist.

#### F: Kann ich Formularfelder unterschiedlichen Typs löschen, z. B. Textfelder, Kontrollkästchen und Optionsfelder?

 A: Ja, Sie können damit Formularfelder unterschiedlicher Art, z. B. Textfelder, Kontrollkästchen und Optionsfelder, löschen`Delete` Methode in Aspose.PDF für .NET. Übergeben Sie einfach den Namen des Feldes, das Sie löschen möchten, als Parameter an die Methode.

#### F: Ist es möglich, das Löschen eines Formularfelds im PDF-Dokument rückgängig zu machen?

A: Nein, sobald ein Formularfeld mit Aspose.PDF für .NET gelöscht wurde, kann dies nicht programmgesteuert rückgängig gemacht werden. Es wird empfohlen, eine Sicherungskopie des PDF-Dokuments zu erstellen, bevor Sie Änderungen daran vornehmen, damit Sie bei Bedarf zum Originaldokument zurückkehren können.