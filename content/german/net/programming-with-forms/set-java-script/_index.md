---
title: Stellen Sie Java Script ein
linktitle: Stellen Sie Java Script ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Aspose.PDF für .NET verwenden, um JavaScript in Formularfeldern in PDF-Dateien festzulegen.
type: docs
weight: 270
url: /de/net/programming-with-forms/set-java-script/
---
In dieser Anleitung erklären wir Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET JavaScript in einem Formularfeld eines PDF-Dokuments definieren. Wir zeigen Ihnen, wie Sie JavaScript-Aktionen konfigurieren, um bestimmte Vorgänge im Textfeld auszuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine auf Ihrem System installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Konfigurieren des Dokumentenverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich die PDF-Datei befindet, an der Sie arbeiten möchten. Du kannst den ... benutzen`dataDir` Variable, um den Verzeichnispfad anzugeben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 2: Laden der Eingabe-PDF-Datei

In diesem Schritt laden wir die Eingabe-PDF-Datei mit`Document` Klasse von Aspose.PDF.

```csharp
// Laden Sie die Eingabe-PDF-Datei
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Stellen Sie sicher, dass die Eingabe-PDF-Datei im angegebenen Dokumentenverzeichnis vorhanden ist.

## Schritt 3: Zugriff auf das TextBox-Feld

 Um JavaScript auf ein bestimmtes Textfeld anzuwenden, müssen wir zunächst auf dieses Feld zugreifen. In diesem Beispiel gehen wir davon aus, dass das Textfeld „textbox1“ heißt. Benutzen Sie die`doc.Form["textbox1"]` Methode, um das entsprechende zu erhalten`TextBoxField` Objekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Stellen Sie sicher, dass das angegebene Textfeld in der Eingabe-PDF-Datei vorhanden ist.

## Schritt 4: Konfigurieren Sie JavaScript-Aktionen

 Nachdem wir nun auf das Textfeld zugegriffen haben, können wir die mit diesem Feld verbundenen JavaScript-Aktionen konfigurieren. In diesem Beispiel verwenden wir zwei Aktionen:`OnModifyCharacter` Und`OnFormat` . Diese Aktionen werden mit definiert`JavascriptAction` Objekte.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Passen Sie die JavaScript-Aktionen unbedingt an Ihre Bedürfnisse an.

## Schritt 5: Festlegen des anfänglichen Feldwerts

Bevor wir das resultierende PDF speichern, können wir einen Anfangswert für das Textfeld festlegen. In diesem Beispiel legen wir für das Feld den Wert „123“ fest.

```csharp
field.Value = "123";
```

Passen Sie diesen Wert an Ihre Bedürfnisse an.

## Schritt 6: Speichern des resultierenden PDF

 Nachdem wir nun mit dem Einrichten des Textfelds und der JavaScript-Aktionen fertig sind, können wir die resultierende PDF-Datei mit speichern`Save` Methode der`Document` Klasse.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Speichern Sie das resultierende PDF
doc.Save(dataDir);
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für die resultierende PDF-Datei an.


### Beispielquellcode für Set Java Script mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die Eingabe-PDF-Datei
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 Ziffern nach dem Punkt
// Kein Trennzeichen
// Neg-Stil = Minus
// Keine Währung
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Legen Sie den anfänglichen Feldwert fest
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Speichern Sie das resultierende PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Abschluss

In dieser Anleitung haben wir gelernt, wie man die Aspose.PDF-Bibliothek für .NET verwendet, um JavaScript in einem Formularfeld eines PDF-Dokuments festzulegen. Indem Sie die beschriebenen Schritte befolgen, können Sie JavaScript-Aktionen anpassen, um verschiedene Vorgänge in Textfeldern auszuführen. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten der Bearbeitung von PDF-Dateien zu erweitern.


### FAQs

#### F: Kann ich Aspose.PDF für .NET verwenden, um JavaScript zu anderen Formularelementen wie Kontrollkästchen und Optionsfeldern hinzuzufügen?

 A: Ja, mit Aspose.PDF für .NET können Sie JavaScript zu verschiedenen Formularelementen hinzufügen, einschließlich Kontrollkästchen, Optionsfeldern und Dropdown-Listen. Du kannst den ... benutzen`JavascriptAction` Klasse zum Definieren von JavaScript-Aktionen für verschiedene Formularelemente.

#### F: Ist es möglich, Benutzereingaben mithilfe von JavaScript in Formularfeldern zu validieren?

 A: Ja, Sie können JavaScript verwenden, um Benutzereingaben in Formularfeldern zu validieren. Durch die Definition von JavaScript-Aktionen wie`OnBlur` oder`OnKeystroke` Für ein Formularfeld können Sie die eingegebenen Daten validieren und bei Bedarf Fehlermeldungen anzeigen.

#### F: Kann ich komplexe JavaScript-Funktionen mit Aspose.PDF für .NET ausführen?

 A: Ja, Sie können komplexe JavaScript-Funktionen mit Aspose.PDF für .NET ausführen. Sie haben die Flexibilität, benutzerdefinierte JavaScript-Funktionen zu definieren und diese innerhalb der aufzurufen`JavascriptAction`.

#### F: Unterstützt Aspose.PDF für .NET andere JavaScript-Ereignisse als die in diesem Tutorial erwähnten?

 A: Ja, Aspose.PDF für .NET unterstützt eine Vielzahl von JavaScript-Ereignissen, darunter`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Und`OnMouseUp`, unter anderen. Mithilfe dieser Ereignisse können Sie JavaScript-Aktionen basierend auf Benutzerinteraktionen auslösen.

#### F: Kann ich Aspose.PDF für .NET verwenden, um JavaScript-Code aus vorhandenen PDF-Dokumenten zu extrahieren?

 A: Aspose.PDF für .NET bietet die Möglichkeit, JavaScript-Code aus vorhandenen PDF-Dokumenten zu extrahieren. Du kannst den ... benutzen`JavascriptAction` Klasse und andere relevante Methoden, um auf JavaScript-Aktionen in einem PDF-Formular zuzugreifen und diese zu analysieren.