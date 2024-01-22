---
title: Παρέχετε διαπιστευτήρια κατά τη διάρκεια HTML σε PDF
linktitle: Παρέχετε διαπιστευτήρια κατά τη διάρκεια HTML σε PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη μετατροπή HTML σε PDF παρέχοντας διαπιστευτήρια με το Aspose.PDF για .NET.
type: docs
weight: 240
url: /el/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία μετατροπής ενός αρχείου HTML σε PDF παρέχοντας ταυτόχρονα διαπιστευτήρια κατά την πρόσβαση σε μια ασφαλή διεύθυνση URL χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τα παρακάτω βήματα, θα μπορείτε να μετατρέψετε περιεχόμενο HTML σε PDF χρησιμοποιώντας τα κατάλληλα διαπιστευτήρια.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι πληροίτε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις της γλώσσας προγραμματισμού C#.
- Η βιβλιοθήκη Aspose.PDF για .NET είναι εγκατεστημένη στο σύστημά σας.
- Ένα περιβάλλον ανάπτυξης όπως το Visual Studio.

## Βήμα 1: Λήψη ασφαλούς περιεχομένου HTML
Σε αυτό το βήμα, θα λάβουμε ασφαλές περιεχόμενο HTML από μια διεύθυνση URL χρησιμοποιώντας τα κατάλληλα διαπιστευτήρια. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε ένα αίτημα για τη διεύθυνση URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Εάν χρειάζεται για διακομιστή, ορίστε διαπιστευτήρια.
request.Credentials = CredentialCache.DefaultCredentials;
// Λάβετε την απάντηση.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Λάβετε τη ροή που περιέχει το περιεχόμενο που επιστρέφεται από τον διακομιστή.
Stream dataStream = response. GetResponseStream();
// Ανοίξτε τη ροή χρησιμοποιώντας ένα StreamReader για εύκολη πρόσβαση.
StreamReader reader = new StreamReader(dataStream);
// Διαβάστε το περιεχόμενο.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENTS DIRECTORY"` με τον πραγματικό κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που προκύπτει.

## Βήμα 2: Μετατρέψτε το HTML σε PDF παρέχοντας διαπιστευτήρια
Τώρα θα φορτώσουμε το ανακτηθέν περιεχόμενο HTML και θα το μετατρέψουμε σε μορφή PDF παρέχοντας παράλληλα τα κατάλληλα διαπιστευτήρια. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Φορτώστε το αρχείο HTML
Document pdfDocument = new Document(stream, options);
```

## Βήμα 3: Αποθήκευση του αρχείου PDF που προκύπτει
Τέλος, θα αποθηκεύσουμε το αρχείο PDF που προκύπτει. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αποθηκεύστε το αρχείο PDF που προκύπτει
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Ο παραπάνω κώδικας αποθηκεύει το αρχείο PDF που προκύπτει με το όνομα αρχείου`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Παράδειγμα πηγαίου κώδικα για Παροχή διαπιστευτηρίων κατά τη διάρκεια HTML σε PDF χρησιμοποιώντας Aspose.PDF για .NET

```csharp
try
{
	
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Δημιουργήστε ένα αίτημα για τη διεύθυνση URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Εάν απαιτείται από τον διακομιστή, ορίστε τα διαπιστευτήρια.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Λάβετε την απάντηση.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Λάβετε τη ροή που περιέχει περιεχόμενο που επιστρέφεται από τον διακομιστή.
	Stream dataStream = response.GetResponseStream();
	// Ανοίξτε τη ροή χρησιμοποιώντας ένα StreamReader για εύκολη πρόσβαση.
	StreamReader reader = new StreamReader(dataStream);
	// Διαβάστε το περιεχόμενο.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Φόρτωση αρχείου HTML
	Document pdfDocument = new Document(stream, options);
	// Αποθηκεύστε το αρχείο που προκύπτει
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία βήμα προς βήμα μετατροπής ενός αρχείου HTML σε PDF παρέχοντας ταυτόχρονα διαπιστευτήρια κατά την πρόσβαση σε μια ασφαλή διεύθυνση URL χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τις οδηγίες που περιγράφονται παραπάνω, θα μπορείτε να μετατρέψετε με επιτυχία περιεχόμενο HTML σε PDF παρέχοντας παράλληλα τα σωστά διαπιστευτήρια.

### Συχνές ερωτήσεις

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές να εργάζονται με έγγραφα PDF σε εφαρμογές C#. Προσφέρει ένα ευρύ φάσμα λειτουργιών, συμπεριλαμβανομένης της μετατροπής HTML σε PDF.

#### Ε: Πώς μπορώ να ανακτήσω ασφαλές περιεχόμενο HTML από μια διεύθυνση URL;

 Α: Για να λάβετε ασφαλές περιεχόμενο HTML από μια διεύθυνση URL, μπορείτε να χρησιμοποιήσετε το`WebRequest` τάξη στην C#. Βεβαιωθείτε ότι έχετε ορίσει τα κατάλληλα διαπιστευτήρια χρησιμοποιώντας το`Credentials` ιδιοκτησία.

#### Ε: Ποιες είναι οι προϋποθέσεις για αυτό το σεμινάριο;

Α: Πριν συνεχίσετε με το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις της γλώσσας προγραμματισμού C#.
- Η βιβλιοθήκη Aspose.PDF για .NET είναι εγκατεστημένη στο σύστημά σας.
- Ένα περιβάλλον ανάπτυξης όπως το Visual Studio.

#### Ε: Πώς χειρίζεται το Aspose.PDF για .NET εξωτερικούς πόρους κατά τη μετατροπή HTML σε PDF;

 Α: Το Aspose.PDF για .NET παρέχει το`HtmlLoadOptions`κλάση για το χειρισμό εξωτερικών πόρων κατά τη μετατροπή HTML σε PDF. Μπορείτε να ορίσετε τα διαπιστευτήρια εξωτερικού πόρου χρησιμοποιώντας το`ExternalResourcesCredentials` ιδιοκτησία.

#### Ε: Μπορώ να προσαρμόσω το όνομα αρχείου για το αρχείο PDF που προκύπτει;

 Α: Ναι, μπορείτε να προσαρμόσετε το όνομα αρχείου για το αρχείο PDF που προκύπτει τροποποιώντας τον κώδικα που αποθηκεύει το έγγραφο PDF. Απλώς αλλάξτε το επιθυμητό όνομα αρχείου στο`pdfDocument.Save()` μέθοδος.