---
title: Legen Sie das Ablaufdatum in der PDF-Datei fest
linktitle: Legen Sie das Ablaufdatum in der PDF-Datei fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET das Ablaufdatum in einer PDF-Datei festlegen.
type: docs
weight: 300
url: /de/net/programming-with-document/setexpirydate/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die verschiedene Funktionen für die Arbeit mit PDF-Dateien bietet. Eine dieser Funktionen ist die Möglichkeit, ein Ablaufdatum für ein PDF-Dokument festzulegen. In diesem Tutorial führen wir Sie durch den Prozess des Festlegens eines Ablaufdatums für ein PDF-Dokument mithilfe von Aspose.PDF für .NET. 

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

Bevor wir beginnen, müssen wir den Pfad zu dem Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir werden diesen Pfad in einer Variablen namens „dataDir“ speichern.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen eines neuen PDF-Dokuments

 Um ein neues PDF-Dokument zu erstellen, müssen wir ein neues instanziieren`Aspose.Pdf.Document` Objekt. Wir können dies mit dem folgenden Code tun:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Schritt 3: Hinzufügen einer neuen Seite zum PDF-Dokument

Sobald wir das PDF-Dokument erstellt haben, können wir ihm eine neue Seite hinzufügen. Wir können dies mit dem folgenden Code tun:

```csharp
doc.Pages.Add();
```

## Schritt 4: Text zum PDF-Dokument hinzufügen

Nachdem wir dem PDF-Dokument eine Seite hinzugefügt haben, können wir mit dem Text hinzufügen`Paragraphs` Sammlung. Wir können dies mit dem folgenden Code tun:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Schritt 5: PDF-Ablaufdatum mit JavaScript festlegen

Um das PDF-Ablaufdatum festzulegen, müssen wir ein JavaScript-Objekt erstellen. Wir können dies mit dem folgenden Code tun:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Legen Sie JavaScript als PDF-Öffnungsaktion fest
doc.OpenAction = javaScript;
```

In diesem Code legen wir das Ablaufdatum auf Mai 2017 fest.

## Schritt 6: Speichern Sie die PDF-Datei

 Nachdem Sie das Ablaufdatum festgelegt haben, müssen Sie die PDF-Datei speichern. Dazu können Sie die verwenden`Save` Methode der`Document` Objekt und übergeben Sie den Pfad zu dem Ort, an dem Sie die aktualisierte PDF-Datei speichern möchten.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
```

### Beispielquellcode für „Ablaufdatum festlegen“ mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Festlegen des Ablaufdatums mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentobjekt instanziieren
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
doc.Pages.Add();
// Textfragment zur Absatzsammlung des Seitenobjekts hinzufügen
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Erstellen Sie ein JavaScript-Objekt, um das PDF-Ablaufdatum festzulegen
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Legen Sie JavaScript als PDF-Öffnungsaktion fest
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
```

## Abschluss

Das Festlegen eines Ablaufdatums für ein PDF-Dokument mit Aspose.PDF für .NET ist eine nützliche Funktion, um sicherzustellen, dass das Dokument nur für einen bestimmten Zeitraum gültig ist. Indem Entwickler der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können sie ganz einfach das Ablaufdatum festlegen und PDFs mit zeitlich begrenzter Gültigkeit erstellen. Diese Funktion kann besonders hilfreich sein für Dokumente, auf die nur für einen begrenzten Zeitraum zugegriffen werden muss oder die verteilt werden müssen.

### FAQs zum Festlegen des Ablaufdatums in der PDF-Datei

#### F: Kann ich ein anderes Ablaufdatum für das PDF-Dokument festlegen?

 A: Ja, Sie können ein anderes Ablaufdatum für das PDF-Dokument festlegen, indem Sie den JavaScript-Code in Schritt 5 ändern. Im bereitgestellten Beispiel ist das Ablaufdatum auf Mai 2017 festgelegt. Um ein anderes Ablaufdatum festzulegen, müssen Sie das ändern`year` Und`month` Variablen im JavaScript-Code auf das gewünschte Jahr und den gewünschten Monat.

#### F: Was passiert, wenn das PDF-Dokument abgelaufen ist?

A: Wenn das PDF-Dokument abgelaufen ist, wie im JavaScript-Code angegeben, zeigt der Viewer eine Warnmeldung an, die darauf hinweist, dass die Datei abgelaufen ist und der Benutzer eine neue benötigt. Diese Warnmeldung wird angezeigt, wenn das PDF geöffnet wird.

#### F: Kann ich für das Ablaufdatum eine bestimmte Uhrzeit anstelle nur des Datums verwenden?

 A: Ja, Sie können im JavaScript-Code eine bestimmte Zeit für das Ablaufdatum festlegen. Durch die Änderung der`expiry` Um die gewünschte Zeit in die Variable im JavaScript-Code einzubeziehen, können Sie eine bestimmte Zeit für das Ablaufdatum festlegen.