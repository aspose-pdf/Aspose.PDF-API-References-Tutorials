---
title: Konfigurieren Sie die gemessene Lizenz
linktitle: Konfigurieren Sie die gemessene Lizenz
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einrichten einer getakteten Lizenz mit Aspose.PDF für .NET und zum Profitieren von erweiterten Funktionen.
type: docs
weight: 10
url: /de/net/licensing-aspose-pdf/configure-metered-license/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Einrichtung einer gemessenen Lizenz mit Aspose.PDF für .NET. Mit der gemessenen Lizenz können Sie die erweiterten Funktionen von Aspose.PDF basierend auf Ihrem tatsächlichen Verbrauch nutzen.

### Schritt 1: Lizenzschlüssel konfigurieren

Im bereitgestellten Quellcode müssen Sie den öffentlichen und privaten Schlüssel der gemessenen Lizenz angeben. Ersetze das "*****"-Werte mit Ihren eigenen Schlüsseln. Diese Schlüssel werden Ihnen beim Kauf einer Messlizenz von Aspose zur Verfügung gestellt.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Schritt 2: Laden des Dokuments

 Laden Sie das PDF-Dokument mit von der Festplatte`Document`Klasse von Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Schritt 3: Ermitteln Sie die Seitenzahl des Dokuments

 Benutzen Sie die`Count` Eigentum der`Pages` Sammlung, um die Gesamtzahl der Seiten im Dokument zu erhalten.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Beispielquellcode für die Konfiguration einer gemessenen Lizenz mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Legen Sie gemessene öffentliche und private Schlüssel fest
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Greifen Sie auf die Eigenschaft setMeteredKey zu und übergeben Sie öffentliche und private Schlüssel als Parameter
metered.SetMeteredKey("*****", "*****");
// Laden Sie das Dokument von der Festplatte.
Document doc = new Document(dataDir + "input.pdf");
//Ermitteln Sie die Seitenzahl des Dokuments
Console.WriteLine(doc.Pages.Count);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET eine getaktete Lizenz einrichtet. Durch die Verwendung einer gebührenpflichtigen Lizenz können Sie basierend auf Ihrer tatsächlichen Nutzung von den erweiterten Funktionen von Aspose.PDF profitieren. Stellen Sie sicher, dass Sie gültige Lizenzschlüssel bereitstellen, um Aspose.PDF mit all seinen Funktionen nutzen zu können.
