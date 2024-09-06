---
title: Felder aus Region in PDF-Datei abrufen
linktitle: Felder aus Region in PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Holen Sie sich mit Aspose.PDF für .NET ganz einfach Felder aus einer bestimmten Region in eine PDF-Datei.
type: docs
weight: 130
url: /de/net/programming-with-forms/get-fields-from-region/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Felder einer bestimmten Region in einer PDF-Datei abrufen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Öffnen Sie die PDF-Datei

Öffnen Sie die PDF-Datei:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Schritt 3: Erstellen Sie ein rechteckiges Objekt, um die Region zu begrenzen

Erstellen Sie ein rechteckiges Objekt, um den Bereich abzugrenzen, in dem Sie die Felder erhalten möchten:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Schritt 4: PDF-Formular erhalten

Holen Sie sich das PDF-Dokument:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Schritt 5: Holen Sie sich die Felder im rechteckigen Bereich

Holen Sie sich die Felder, die sich im angegebenen rechteckigen Bereich befinden:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Schritt 6: Feldnamen und Werte anzeigen

Iterieren Sie durch die resultierenden Felder und zeigen Sie ihre Namen und Werte an:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Beispielquellcode für „Get Fields From Region“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Datei öffnen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Erstellen Sie ein rechteckiges Objekt, um Felder in diesem Bereich zu erhalten
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// PDF-Formular herunterladen
Aspose.Pdf.Forms.Form form = doc.Form;
// Holen Sie sich Felder im rechteckigen Bereich
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Anzeigefeldnamen und -werte
foreach (Field field in fields)
{
	// Bildplatzierungseigenschaften für alle Platzierungen anzeigen
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Felder eines bestimmten Bereichs in einem PDF-Dokument abruft. Indem Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach die Felder extrahieren, die sich in einem bestimmten rechteckigen Bereich Ihres PDF-Dokuments befinden.

### Häufig gestellte Fragen

#### F: Kann ich diese Methode verwenden, um Felder aus einem nicht rechteckigen Bereich in einem PDF-Dokument abzurufen?

 A: Nein, die bereitgestellte Methode`GetFieldsInRect` ist speziell dafür konzipiert, Felder abzurufen, die sich in einem rechteckigen Bereich in einem PDF-Dokument befinden. Wenn Sie Felder aus einem nicht rechteckigen Bereich extrahieren müssen, müssen Sie eine benutzerdefinierte Logik implementieren, um die Felder anhand anderer Kriterien, wie z. B. Feldkoordinaten oder -namen, zu identifizieren und zu extrahieren.

#### F: Wie kann ich die Größe oder Position des Rechtecks ändern, um Felder aus einer anderen Region zu erhalten?

 A: Um Felder aus einer anderen Region zu erhalten, können Sie die`Aspose.Pdf.Rectangle` Parameter des Objekts, die zur Definition des Begrenzungsrechtecks verwendet werden.`Rectangle` Der Konstruktor verwendet vier Parameter:`x`, `y`, `width` , Und`height`die die Koordinaten der oberen linken Ecke und die Abmessungen des Rechtecks darstellen. Durch Anpassen dieser Parameter wird der Bereich geändert, aus dem Felder extrahiert werden.

#### F: Was passiert, wenn sich innerhalb des angegebenen rechteckigen Bereichs keine Felder befinden?

 A: Wenn sich innerhalb des angegebenen rechteckigen Bereichs keine Felder befinden,`GetFieldsInRect` Methode gibt ein leeres Array zurück. Sie können die Länge des Arrays überprüfen, um festzustellen, ob sich innerhalb der Region Felder befinden.

#### F: Kann ich Felder aus überlappenden Bereichen in einem PDF-Dokument abrufen?

 A: Ja, Sie können Felder aus überlappenden Bereichen in einem PDF-Dokument abrufen, indem Sie mehrere`Aspose.Pdf.Rectangle` Objekte und Aufruf der`GetFieldsInRect` Methode für jeden von ihnen. Überlappende Regionen werden unabhängig behandelt und Sie erhalten separate Feldarrays für jede Region.

#### F: Ist es möglich, Felder von einer bestimmten Seite oder mehreren Seiten im PDF-Dokument abzurufen?

A: Ja, Sie können Felder von einer bestimmten Seite oder mehreren Seiten in einem PDF-Dokument abrufen. Dazu können Sie das PDF-Dokument laden, die gewünschten Seiten über den`doc.Pages` Sammlung, und wenden Sie dann die`GetFieldsInRect` Methode für die spezifische Region jeder Seite.