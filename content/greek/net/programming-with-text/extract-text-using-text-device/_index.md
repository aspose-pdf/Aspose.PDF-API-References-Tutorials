---
title: Εξαγωγή κειμένου με χρήση συσκευής κειμένου
linktitle: Εξαγωγή κειμένου με χρήση συσκευής κειμένου
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εξάγετε κείμενο από ένα έγγραφο PDF χρησιμοποιώντας τη Συσκευή κειμένου στο Aspose.PDF για .NET.
type: docs
weight: 210
url: /el/net/programming-with-text/extract-text-using-text-device/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία εξαγωγής κειμένου από ένα έγγραφο PDF χρησιμοποιώντας τη Συσκευή κειμένου στο Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να εξαγάγετε κείμενο, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Ανοίξτε το έγγραφο PDF
 Ανοίξτε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document`κατασκευαστή και περνώντας τη διαδρομή προς το αρχείο εισόδου PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Βήμα 5: Εξαγωγή κειμένου χρησιμοποιώντας τη συσκευή κειμένου
 Δημιουργώ ένα`StringBuilder` αντικείμενο για να κρατήσει το εξαγόμενο κείμενο. Επαναλάβετε σε κάθε σελίδα του εγγράφου και χρησιμοποιήστε a`TextDevice` για να εξαγάγετε το κείμενο από κάθε σελίδα.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Βήμα 6: Αποθηκεύστε το εξαγόμενο κείμενο
 Καθορίστε τη διαδρομή του αρχείου εξόδου και αποθηκεύστε το εξαγόμενο κείμενο σε ένα αρχείο κειμένου χρησιμοποιώντας το`File.WriteAllText` μέθοδος.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Δείγμα πηγαίου κώδικα για εξαγωγή κειμένου με χρήση συσκευής κειμένου χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Συμβολοσειρά για τη συγκράτηση του εξαγόμενου κειμένου
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Δημιουργία συσκευής κειμένου
		TextDevice textDevice = new TextDevice();
		// Ορισμός επιλογών εξαγωγής κειμένου - ορίστε τη λειτουργία εξαγωγής κειμένου (ακατέργαστο ή καθαρό)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Μετατρέψτε μια συγκεκριμένη σελίδα και αποθηκεύστε κείμενο στη ροή
		textDevice.Process(pdfPage, textStream);
		// Μετατρέψτε μια συγκεκριμένη σελίδα και αποθηκεύστε κείμενο στη ροή
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Κλείσιμο ροής μνήμης
		textStream.Close();
		// Λήψη κειμένου από τη ροή μνήμης
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Αποθηκεύστε το εξαγόμενο κείμενο σε αρχείο κειμένου
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## συμπέρασμα
Έχετε εξαγάγει με επιτυχία κείμενο από ένα έγγραφο PDF χρησιμοποιώντας τη συσκευή κειμένου στο Aspose.PDF για .NET. Το εξαγόμενο κείμενο έχει αποθηκευτεί στο καθορισμένο αρχείο εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο παρέχει καθοδήγηση σχετικά με την εξαγωγή κειμένου από ένα έγγραφο PDF χρησιμοποιώντας τη δυνατότητα Συσκευής κειμένου στο Aspose.PDF για .NET. Ο συνοδευτικός πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα για την επίτευξη αυτής της εργασίας.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω;

Α: Στο αρχείο κώδικα όπου σκοπεύετε να εξαγάγετε κείμενο, συμπεριλάβετε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Στον κώδικα, βρείτε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να ανοίξω ένα υπάρχον έγγραφο PDF;

 Α: Στο Βήμα 4, θα ανοίξετε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document` κατασκευαστή και παρέχοντας τη διαδρομή προς το αρχείο εισόδου PDF.

#### Ε: Πώς μπορώ να εξαγάγω κείμενο χρησιμοποιώντας τη συσκευή κειμένου;

 Α: Το βήμα 5 περιλαμβάνει τη δημιουργία α`StringBuilder` αντικείμενο για να κρατήσει το εξαγόμενο κείμενο. Στη συνέχεια, θα επαναλάβετε κάθε σελίδα του εγγράφου και θα χρησιμοποιήσετε το α`TextDevice` μαζί με`TextExtractionOptions` για εξαγωγή κειμένου από κάθε σελίδα.

#### Ε: Πώς μπορώ να αποθηκεύσω το εξαγόμενο κείμενο σε ένα αρχείο;

 Α: Στο Βήμα 6, θα καθορίσετε τη διαδρομή του αρχείου εξόδου και θα χρησιμοποιήσετε το`File.WriteAllText`μέθοδος αποθήκευσης του εξαγόμενου κειμένου σε αρχείο κειμένου.

#### Ε: Ποιο είναι το βασικό στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να αξιοποιείτε τη δυνατότητα Συσκευής κειμένου στο Aspose.PDF για .NET για εξαγωγή κειμένου από ένα έγγραφο PDF. Το εξαγόμενο κείμενο έχει αποθηκευτεί σε ένα καθορισμένο αρχείο εξόδου, επιτρέποντάς σας να χειριστείτε και να χρησιμοποιήσετε το εξαγόμενο περιεχόμενο όπως απαιτείται.