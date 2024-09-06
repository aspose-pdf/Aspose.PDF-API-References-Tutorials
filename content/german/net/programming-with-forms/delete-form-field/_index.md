---
title: Formularfeld im PDF-Dokument löschen
linktitle: Formularfeld im PDF-Dokument löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Entfernen Sie mit Aspose.PDF für .NET ganz einfach unerwünschte Formularfelder aus PDF-Dokumenten.
type: docs
weight: 50
url: /de/net/programming-with-forms/delete-form-field/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Formularfeld löschen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Vorgang zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Schritt 3: Ein bestimmtes Feld löschen

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

### Beispielquellcode zum Löschen von Formularfeldern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Löschen eines bestimmten Felds anhand des Namens
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Geändertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Formularfeld löscht. Indem Sie diese Schritte befolgen, können Sie mit Aspose.PDF problemlos unerwünschte Formularfelder aus Ihren PDF-Dokumenten entfernen.

### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET mehrere Formularfelder gleichzeitig löschen?

 A: Ja, Sie können mehrere Formularfelder auf einmal löschen, indem Sie Aspose.PDF für .NET verwenden. Rufen Sie einfach die`Delete` Methode für jedes Formularfeld, das Sie entfernen möchten.

#### F: Wie kann ich überprüfen, ob ein Formularfeld vorhanden ist, bevor ich versuche, es zu löschen?

 A: Sie können überprüfen, ob ein Formularfeld vorhanden ist, bevor Sie versuchen, es zu löschen. Dazu verwenden Sie den`Contains` Methode der`Form` Eigenschaft. Beispiel:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### F: Was passiert, wenn ich versuche, ein Formularfeld zu löschen, das im PDF-Dokument nicht vorhanden ist?

 A: Wenn Sie versuchen, ein Formularfeld zu löschen, das im PDF-Dokument nicht vorhanden ist,`Delete` -Methode wird keinen Fehler oder keine Ausnahme auslösen. Sie wird einfach nichts tun, da kein zu löschendes Feld vorhanden ist.

#### F: Kann ich Formularfelder unterschiedlichen Typs löschen, beispielsweise Textfelder, Kontrollkästchen und Optionsfelder?

 A: Ja, Sie können Formularfelder unterschiedlichen Typs, wie Textfelder, Kontrollkästchen und Optionsfelder, mit demselben`Delete` Methode in Aspose.PDF für .NET. Übergeben Sie einfach den Namen des Felds, das Sie löschen möchten, als Parameter an die Methode.

#### F: Ist es möglich, das Löschen eines Formularfelds im PDF-Dokument rückgängig zu machen?

A: Nein, wenn ein Formularfeld einmal mit Aspose.PDF für .NET gelöscht wurde, kann dies nicht programmgesteuert rückgängig gemacht werden. Es wird empfohlen, vor dem Vornehmen von Änderungen eine Sicherungskopie des PDF-Dokuments zu erstellen, damit Sie bei Bedarf zum Originaldokument zurückkehren können.