---
title: Gesamten Text entfernen
linktitle: Gesamten Text entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text aus einem PDF-Dokument entfernen.
type: docs
weight: 280
url: /de/net/programming-with-text/remove-all-text/
---

In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text aus einem PDF-Dokument entfernen. Wir werden Schritt für Schritt den Prozess des Öffnens einer PDF-Datei, des Auswählens und Löschens von Text auf jeder Seite und des Speicherns der geänderten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich Ihre PDF-Dateien befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihren PDF-Dateien.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Als nächstes öffnen wir das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Schritt 3: Entfernen Sie Text von jeder Seite

 Wir durchlaufen alle Seiten des PDF-Dokuments und verwenden eine`OperatorSelector` , um den gesamten Text auf jeder Seite auszuwählen. Anschließend löschen wir den ausgewählten Text.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Schritt 4: Speichern Sie das geänderte PDF

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Beispielquellcode für „Gesamten Text entfernen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Durchlaufen Sie alle Seiten des PDF-Dokuments
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Markieren Sie den gesamten Text auf der Seite
	page.Contents.Accept(operatorSelector);
	// Löschen Sie den gesamten Text
	page.Contents.Delete(operatorSelector.Selected);
}
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine PDF-Datei öffnen, Text auf jeder Seite auswählen und löschen und die geänderte PDF-Datei speichern.