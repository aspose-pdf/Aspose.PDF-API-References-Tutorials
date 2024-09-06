---
title: Java Script festlegen
linktitle: Java Script festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET JavaScript in Formularfeldern in PDF-Dateien festlegen.
type: docs
weight: 270
url: /de/net/programming-with-forms/set-java-script/
---
In dieser Anleitung erklären wir Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET JavaScript in einem Formularfeld eines PDF-Dokuments definieren. Wir zeigen Ihnen, wie Sie JavaScript-Aktionen konfigurieren, um bestimmte Vorgänge im Textfeld auszuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Auf Ihrem System ist eine .NET-Entwicklungsumgebung installiert.
- Die Aspose.PDF-Bibliothek für .NET. Sie können sie von der offiziellen Aspose-Website herunterladen.

## Schritt 1: Konfigurieren des Dokumentverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich die PDF-Datei befindet, die Sie bearbeiten möchten. Sie können das`dataDir` Variable zum Angeben des Verzeichnispfads.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Laden der Eingabe-PDF-Datei

 In diesem Schritt laden wir die Eingabe-PDF-Datei mit dem`Document` Klasse von Aspose.PDF.

```csharp
// PDF-Eingabedatei laden
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Stellen Sie sicher, dass die Eingabe-PDF-Datei im angegebenen Dokumentverzeichnis vorhanden ist.

## Schritt 3: Auf das TextBox-Feld zugreifen

 Um JavaScript auf ein bestimmtes Textfeld anzuwenden, müssen wir zunächst auf dieses Feld zugreifen. In diesem Beispiel gehen wir davon aus, dass das Textfeld „textbox1“ heißt. Verwenden Sie die`doc.Form["textbox1"]` Methode, um die entsprechende`TextBoxField` Objekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Stellen Sie sicher, dass das angegebene Textfeld in der PDF-Eingabedatei vorhanden ist.

## Schritt 4: JavaScript-Aktionen konfigurieren

 Nachdem wir nun auf das Textfeld zugegriffen haben, können wir die mit diesem Feld verknüpften JavaScript-Aktionen konfigurieren. In diesem Beispiel verwenden wir zwei Aktionen:`OnModifyCharacter` Und`OnFormat` Diese Aktionen werden definiert durch`JavascriptAction` Objekte.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Denken Sie daran, die JavaScript-Aktionen Ihren Anforderungen entsprechend anzupassen.

## Schritt 5: Festlegen des anfänglichen Feldwerts

Bevor wir das resultierende PDF speichern, können wir einen Anfangswert für das Textfeld festlegen. In diesem Beispiel legen wir für das Feld den Wert „123“ fest.

```csharp
field.Value = "123";
```

Passen Sie diesen Wert Ihren Bedürfnissen entsprechend an.

## Schritt 6: Speichern der resultierenden PDF-Datei

 Nachdem wir nun das Textfeld und die JavaScript-Aktionen eingerichtet haben, können wir das resultierende PDF mit dem`Save` Methode der`Document` Klasse.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Ergebnis-PDF speichern
doc.Save(dataDir);
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für die resultierende PDF-Datei an.


### Beispielquellcode für Set Java Script mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Eingabedatei laden
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 Ziffern nach dem Punkt
// Kein Trennzeichen
// Neg-Stil = Minus
// Keine Währung
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Festlegen des anfänglichen Feldwerts
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Ergebnis-PDF speichern
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Handbuch haben wir gelernt, wie man mit der Aspose.PDF-Bibliothek für .NET JavaScript in ein Formularfeld eines PDF-Dokuments einfügt. Indem Sie die beschriebenen Schritte befolgen, können Sie JavaScript-Aktionen anpassen, um verschiedene Vorgänge an Textfeldern auszuführen. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten zur Bearbeitung von PDF-Dateien zu erweitern.


### Häufig gestellte Fragen

#### F: Kann ich Aspose.PDF für .NET verwenden, um JavaScript zu anderen Formularelementen wie Kontrollkästchen und Optionsfeldern hinzuzufügen?

 A: Ja, Aspose.PDF für .NET ermöglicht es Ihnen, JavaScript zu verschiedenen Formularelementen hinzuzufügen, darunter Kontrollkästchen, Optionsfelder und Dropdown-Listen. Sie können das`JavascriptAction` Klasse zum Definieren von JavaScript-Aktionen für verschiedene Formularelemente.

#### F: Ist es möglich, Benutzereingaben in Formularfeldern mit JavaScript zu validieren?

 A: Ja, Sie können JavaScript verwenden, um Benutzereingaben in Formularfeldern zu validieren. Durch die Definition von JavaScript-Aktionen wie`OnBlur` oder`OnKeystroke` Bei einem Formularfeld können Sie die eingegebenen Daten validieren und bei Bedarf Fehlermeldungen anzeigen.

#### F: Kann ich mit Aspose.PDF für .NET komplexe JavaScript-Funktionen ausführen?

 A: Ja, Sie können komplexe JavaScript-Funktionen mit Aspose.PDF für .NET ausführen. Sie haben die Flexibilität, benutzerdefinierte JavaScript-Funktionen zu definieren und diese innerhalb des`JavascriptAction`.

#### F: Unterstützt Aspose.PDF für .NET andere JavaScript-Ereignisse als die, die in diesem Tutorial erwähnt werden?

 A: Ja, Aspose.PDF für .NET unterstützt eine breite Palette von JavaScript-Ereignissen, einschließlich`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Und`OnMouseUp`, unter anderem. Sie können diese Ereignisse verwenden, um JavaScript-Aktionen basierend auf Benutzerinteraktionen auszulösen.

#### F: Kann ich Aspose.PDF für .NET verwenden, um JavaScript-Code aus vorhandenen PDF-Dokumenten zu extrahieren?

 A: Aspose.PDF für .NET bietet die Möglichkeit, JavaScript-Code aus vorhandenen PDF-Dokumenten zu extrahieren. Sie können den`JavascriptAction` Klasse und andere relevante Methoden, um auf JavaScript-Aktionen in einem PDF-Formular zuzugreifen und diese zu analysieren.