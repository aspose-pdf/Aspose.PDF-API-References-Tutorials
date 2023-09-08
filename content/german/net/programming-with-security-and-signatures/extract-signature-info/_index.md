---
title: Signaturinformationen extrahieren
linktitle: Signaturinformationen extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren von Signaturinformationen mit Aspose.PDF für .NET.
type: docs
weight: 80
url: /de/net/programming-with-security-and-signatures/extract-signature-info/
---
Das Extrahieren von Signaturinformationen aus einem PDF-Dokument kann in verschiedenen Szenarien sehr nützlich sein. Unabhängig davon, ob Sie die Authentizität eines signierten Dokuments überprüfen oder das für die Signatur verwendete Zertifikat analysieren müssen, bietet die Bibliothek Aspose.PDF für .NET eine praktische Lösung. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Extraktion von Signaturinformationen mithilfe des bereitgestellten C#-Quellcodes.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Grundkenntnisse der Programmiersprache C#.
2. Aspose.PDF für .NET-Bibliothek auf Ihrem System installiert.
3. Ein gültiges PDF-Dokument mit einem oder mehreren Signaturfeldern.

Kommen wir nun zu den Implementierungsdetails.

## Schritt 1: Importieren der erforderlichen Bibliotheken

 Um zu beginnen, müssen Sie die erforderlichen Bibliotheken in Ihr C#-Projekt importieren. In diesem Fall müssen wir die importieren`Aspose.Pdf` Und`System.IO` Namensräume. Dies können Sie erreichen, indem Sie den folgenden Code am Anfang Ihrer C#-Datei hinzufügen:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Schritt 2: Festlegen des Dokumentpfads

Als Nächstes müssen Sie den Pfad zu dem PDF-Dokument festlegen, aus dem Sie die Signaturinformationen extrahieren möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` im folgenden Codeausschnitt mit dem tatsächlichen Pfad zu Ihrem Dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Schritt 3: Signaturinformationen extrahieren

Kommen wir nun zum Hauptteil des Codes, in dem wir die Signaturinformationen aus dem PDF-Dokument extrahieren. Wir durchlaufen jedes Feld im Formular des Dokuments und prüfen, ob es sich um ein Signaturfeld handelt. Wenn ein Signaturfeld gefunden wird, fahren wir mit der Extraktion des Zertifikats fort. Fügen Sie den folgenden Codeausschnitt hinzu:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Extrahieren Sie das Zertifikat
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Schritt 4: Extrahieren des Zertifikats

In diesem Schritt extrahieren wir das Zertifikat aus dem Signaturfeld und speichern es als Datei. Das extrahierte Zertifikat kann weiter analysiert oder zu Validierungszwecken verwendet werden. Der folgende Codeausschnitt veranschaulicht den Extraktions- und Speichervorgang:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Schritt 5

: Speichern des Zertifikats

Abschließend speichern wir das extrahierte Zertifikat als Datei. In diesem Beispiel wird das Zertifikat unter dem Namen „input.cer“ im angegebenen Verzeichnis gespeichert. Sie können den Code an Ihre Anforderungen anpassen. Hier ist der Codeausschnitt zum Speichern des Zertifikats:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Das ist es! Sie haben die Signaturinformationen mit Aspose.PDF für .NET erfolgreich extrahiert. Sie können diesen Code gerne in Ihre eigenen Anwendungen integrieren oder ihn entsprechend Ihren Bedürfnissen modifizieren.

### Beispielquellcode zum Extrahieren von Signaturinformationen mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung zum Extrahieren von Signaturinformationen aus einem PDF-Dokument mithilfe der Aspose.PDF für .NET-Bibliothek besprochen. Wir haben den Prozess des Importierens der erforderlichen Bibliotheken, des Festlegens des Dokumentpfads, des Extrahierens von Signaturinformationen, des Extrahierens des Zertifikats und des Speicherns in einer Datei behandelt. Wenn Sie diese Schritte befolgen, können Sie Signaturdetails einfach abrufen und bei Bedarf damit arbeiten.

### FAQs

#### F: Warum sollte ich Signaturinformationen aus einem PDF-Dokument extrahieren?

A: Das Extrahieren von Signaturinformationen aus einem PDF-Dokument ist nützlich, um die Authentizität eines signierten Dokuments zu überprüfen und das für die Signatur verwendete Zertifikat zu analysieren. Dieser Prozess trägt dazu bei, die Integrität des signierten Inhalts sicherzustellen und kann aus rechtlichen und sicherheitstechnischen Gründen von entscheidender Bedeutung sein.

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, mit PDF-Dokumenten in .NET-Anwendungen zu arbeiten. Es bietet eine breite Palette von Funktionen zum programmgesteuerten Erstellen, Ändern und Interagieren mit PDF-Dateien.

#### F: Was sind die Voraussetzungen zum Extrahieren von Signaturinformationen mit Aspose.PDF für .NET?

A: Um Signaturinformationen zu extrahieren, benötigen Sie Grundkenntnisse der Programmiersprache C#, die auf Ihrem System installierte Aspose.PDF für .NET-Bibliothek und ein gültiges PDF-Dokument, das ein oder mehrere Signaturfelder enthält.

#### F: Wie importiere ich die erforderlichen Bibliotheken für den Extraktionsprozess?

A: Sie können die erforderlichen Bibliotheken importieren, indem Sie die hinzufügen`using` Richtlinien für`Aspose.Pdf` Und`System.IO` am Anfang Ihrer C#-Datei. Mit diesen Anweisungen können Sie die zum Extrahieren von Signaturinformationen erforderlichen Klassen und Methoden verwenden.

#### F: Wie spezifiziere ich das PDF-Dokument zum Extrahieren von Signaturinformationen?

 A: Sie können den Pfad zum PDF-Dokument durch Ersetzen festlegen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokument im bereitgestellten Code-Snippet. Dieser Pfad wird zum Laden des PDF-Dokuments verwendet, aus dem Sie Signaturinformationen extrahieren möchten.

#### F: Wie werden Signaturinformationen aus einem PDF-Dokument extrahiert?

A: Der Extraktionsprozess umfasst das Durchlaufen der Formularfelder des PDF-Dokuments, die Prüfung, ob es sich bei jedem Feld um ein Signaturfeld handelt, und gegebenenfalls das Extrahieren des zugehörigen Zertifikats. Das extrahierte Zertifikat kann zur weiteren Analyse oder Validierung als Datei gespeichert werden.

#### F: Wie wird das Zertifikat aus einem Signaturfeld extrahiert?

A: Das Zertifikat wird mithilfe von aus einem Signaturfeld extrahiert`ExtractCertificate()` Methode, die von der bereitgestellt wird`SignatureField` Klasse in Aspose.PDF für .NET. Diese Methode gibt einen Stream zurück, der die Zertifikatsdaten enthält.

#### F: Wie speichere ich das extrahierte Zertifikat als Datei?

 A: Sie können das extrahierte Zertifikat als Datei speichern, indem Sie den Zertifikatsstream lesen und seinen Inhalt mithilfe von in eine Datei schreiben`FileStream` Klasse. Der im Tutorial bereitgestellte Code veranschaulicht diesen Prozess.

#### F: Kann ich dieses extrahierte Zertifikat zur Signaturvalidierung verwenden?

A: Ja, das extrahierte Zertifikat kann zur Signaturvalidierung verwendet werden. Sie können die Details des Zertifikats analysieren und seine Authentizität überprüfen, um die Integrität des signierten Dokuments sicherzustellen.

#### F: Wie kann ich diesen Code in meine eigenen Anwendungen integrieren?

A: Sie können den bereitgestellten Code in Ihre eigenen C#-Anwendungen integrieren, indem Sie der Schritt-für-Schritt-Anleitung folgen. Ändern Sie die Pfade und Dateinamen nach Bedarf und integrieren Sie den Code in Ihre vorhandenen Projekte.

#### F: Gibt es in Aspose.PDF für .NET weitere Funktionen im Zusammenhang mit der Signaturverwaltung?

A: Ja, Aspose.PDF für .NET bietet eine Reihe von Funktionen für die Arbeit mit digitalen Signaturen, darunter das Signieren von Dokumenten, das Überprüfen von Signaturen und das Hinzufügen von Zeitstempelinformationen. Weitere Einzelheiten zu diesen Funktionen finden Sie in der offiziellen Dokumentation.

#### F: Wo finde ich zusätzliche Ressourcen für die Verwendung von Aspose.PDF für .NET?

 A: Weitere Informationen, Tutorials und Ressourcen zur Verwendung von Aspose.PDF für .NET finden Sie unter[Aspose.PDF für .NET](https://reference.aspose.com/pdf/net/).

#### F: Ist es möglich, Signaturen aus verschlüsselten PDF-Dokumenten zu extrahieren?

A: Die Möglichkeit, Signaturen aus verschlüsselten PDF-Dokumenten zu extrahieren, kann von den Verschlüsselungseinstellungen und Berechtigungen des Dokuments abhängen. Möglicherweise müssen Sie sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen, um auf Signaturinformationen zuzugreifen und diese zu extrahieren.

#### F: Kann ich mehrere Signaturen aus einem einzelnen PDF-Dokument extrahieren?

A: Ja, Sie können den bereitgestellten Code ändern, um alle Signaturfelder im PDF-Dokument zu durchlaufen und Signaturinformationen aus jedem einzelnen zu extrahieren. Dadurch können Sie Informationen über mehrere im Dokument vorhandene Signaturen extrahieren.

#### F: Welche praktischen Anwendungsfälle gibt es für die Extraktion von Signaturinformationen?

A: Einige praktische Anwendungsfälle zum Extrahieren von Signaturinformationen umfassen die Validierung der Authentizität digital signierter Dokumente, die Analyse von Zertifikatsdetails für Compliance-Zwecke und die Führung einer Aufzeichnung von Signaturen und Unterzeichnern für Prüfzwecke.

#### F: Gibt es rechtliche Aspekte beim Extrahieren von Signaturinformationen?

A: Das Extrahieren von Signaturinformationen kann rechtliche Auswirkungen haben, insbesondere beim Umgang mit rechtsverbindlichen Dokumenten. Stellen Sie sicher, dass Sie die relevanten Vorschriften und Gesetze in Bezug auf elektronische Signaturen und Dokumentenauthentizität in Ihrem Land einhalten.