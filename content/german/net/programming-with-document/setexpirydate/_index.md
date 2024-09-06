---
title: Ablaufdatum in PDF-Datei festlegen
linktitle: Ablaufdatum in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET ein Ablaufdatum in einer PDF-Datei festlegen.
type: docs
weight: 300
url: /de/net/programming-with-document/setexpirydate/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die verschiedene Funktionen für die Arbeit mit PDF-Dateien bietet. Eine dieser Funktionen ist die Möglichkeit, ein Ablaufdatum für ein PDF-Dokument festzulegen. In diesem Tutorial führen wir Sie durch den Prozess zum Festlegen eines Ablaufdatums für ein PDF-Dokument mit Aspose.PDF für .NET. 

## Schritt 1: Pfad zum Dokumentverzeichnis festlegen

Bevor wir beginnen, müssen wir den Pfad zum Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir speichern diesen Pfad in einer Variablen namens „dataDir“.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Neues PDF-Dokument erstellen

 Um ein neues PDF-Dokument zu erstellen, müssen wir eine neue`Aspose.Pdf.Document` Objekt. Dies können wir mit dem folgenden Code tun:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Schritt 3: Dem PDF-Dokument eine neue Seite hinzufügen

Nachdem wir das PDF-Dokument erstellt haben, können wir ihm eine neue Seite hinzufügen. Dies können wir mit dem folgenden Code tun:

```csharp
doc.Pages.Add();
```

## Schritt 4: Text zum PDF-Dokument hinzufügen

 Nachdem wir eine Seite zum PDF-Dokument hinzugefügt haben, können wir Text hinzufügen, indem wir`Paragraphs` Sammlung. Dies können wir mit dem folgenden Code tun:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Schritt 5: Festlegen des PDF-Ablaufdatums mit JavaScript

Um das Ablaufdatum der PDF-Datei festzulegen, müssen wir ein JavaScript-Objekt erstellen. Dies können wir mit dem folgenden Code tun:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// JavaScript als PDF-Öffnen-Aktion festlegen
doc.OpenAction = javaScript;
```

In diesem Code legen wir das Ablaufdatum auf Mai 2017 fest.

## Schritt 6: Speichern Sie die PDF-Datei

 Nachdem Sie das Ablaufdatum festgelegt haben, müssen Sie die PDF-Datei speichern. Dazu können Sie das`Save` Methode der`Document` Objekt und geben Sie den Pfad ein, unter dem Sie die aktualisierte PDF-Datei speichern möchten.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
```

### Beispielquellcode zum Festlegen des Ablaufdatums mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Festlegen des Ablaufdatums mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document-Objekt instanziieren
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
// JavaScript als PDF-Öffnen-Aktion festlegen
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
```

## Abschluss

Das Festlegen eines Ablaufdatums für ein PDF-Dokument mit Aspose.PDF für .NET ist eine nützliche Funktion, um sicherzustellen, dass das Dokument nur für einen bestimmten Zeitraum gültig ist. Indem sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können Entwickler das Ablaufdatum problemlos festlegen und PDFs mit zeitlich begrenzter Gültigkeit erstellen. Diese Funktion kann insbesondere für Dokumente hilfreich sein, auf die für eine begrenzte Dauer zugegriffen oder die verteilt werden müssen.

### FAQs zum Festlegen des Ablaufdatums in einer PDF-Datei

#### F: Kann ich für das PDF-Dokument ein anderes Ablaufdatum festlegen?

 A: Ja, Sie können ein anderes Ablaufdatum für das PDF-Dokument festlegen, indem Sie den JavaScript-Code in Schritt 5 ändern. Im angegebenen Beispiel ist das Ablaufdatum auf Mai 2017 eingestellt. Um ein anderes Ablaufdatum festzulegen, müssen Sie den`year` Und`month` Variablen im JavaScript-Code auf das gewünschte Jahr und den gewünschten Monat.

#### F: Was passiert, wenn das PDF-Dokument abgelaufen ist?

A: Wenn das PDF-Dokument abgelaufen ist, wie im JavaScript-Code angegeben, zeigt der Viewer eine Warnmeldung an, die besagt, dass die Datei abgelaufen ist und der Benutzer eine neue benötigt. Diese Warnmeldung wird angezeigt, wenn das PDF geöffnet wird.

#### F: Kann ich als Ablaufdatum eine konkrete Uhrzeit statt nur das Datum verwenden?

 A: Ja, Sie können im JavaScript-Code eine bestimmte Zeit für das Ablaufdatum festlegen. Durch Ändern des`expiry` Mit der Variable im JavaScript-Code, die die gewünschte Zeit enthält, können Sie einen bestimmten Zeitpunkt für das Ablaufdatum festlegen.