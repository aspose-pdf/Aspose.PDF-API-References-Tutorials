---
title: Δημιουργία εγγράφου
linktitle: Δημιουργία εγγράφου
second_title: Aspose.PDF για Αναφορά API .NET
description: Δημιουργήστε εύκολα ένα έγγραφο με κουμπιά επιλογής χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 40
url: /el/net/programming-with-forms/create-doc/
---
Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να δημιουργήσετε ένα έγγραφο με κουμπιά επιλογής χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# βήμα προς βήμα για να σας καθοδηγήσουμε σε αυτήν τη διαδικασία.

##Βήμα 1: Προετοιμασία

Πρώτα, βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες βιβλιοθήκες και έχετε ορίσει τη διαδρομή προς τον κατάλογο εγγράφων:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο

Δημιουργήστε ένα νέο αντικείμενο Document για να κρατήσετε το έγγραφο PDF:

```csharp
Document doc = new Document();
```

## Βήμα 3: Προσθέστε μια σελίδα

Προσθέστε μια νέα σελίδα στο έγγραφο:

```csharp
Page page = doc.Pages.Add();
```

## Βήμα 4: Προσθέστε ένα πεδίο κουμπιού επιλογής

Δημιουργήστε ένα πεδίο κουμπιού επιλογής και ορίστε τη θέση και το μέγεθός του:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Βήμα 5: Προσθέστε επιλογές κουμπιού επιλογής

Προσθέστε τις επιθυμητές επιλογές στο πεδίο του κουμπιού επιλογής. Μπορείτε να ορίσετε τις συντεταγμένες και το μέγεθος κάθε επιλογής όπως απαιτείται:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Βήμα 6: Προσθέστε το πεδίο του κουμπιού επιλογής στη φόρμα

Προσθέστε το πεδίο του κουμπιού επιλογής στη συλλογή Document Form Fields:

```csharp
doc.Form.Add(field);
```

## Βήμα 7: Αποθηκεύστε το έγγραφο

Αποθηκεύστε το έγγραφο PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Δείγμα πηγαίου κώδικα για το Create Doc χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
try
{
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Δημιουργήστε ένα νέο έγγραφο
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Προσθήκη πεδίου κουμπιού επιλογής
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Προσθήκη επιλογών κουμπιού επιλογής. παρακαλώ σημειώστε ότι αυτές οι επιλογές βρίσκονται
	// Ούτε οριζόντια ούτε κάθετα.
	// Μπορείτε να δοκιμάσετε να ορίσετε οποιεσδήποτε συντεταγμένες (και ακόμη και μέγεθος) για αυτές.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Αποθηκεύστε το έγγραφο PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε ένα έγγραφο με κουμπιά επιλογής χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσθέσετε κουμπιά επιλογής στα έγγραφά σας PDF χρησιμοποιώντας το Aspose.PDF.

### Συχνές ερωτήσεις

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση των κουμπιών επιλογής στο έγγραφο χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των κουμπιών επιλογής στο έγγραφο χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να ορίσετε ιδιότητες όπως μέγεθος, χρώμα, στυλ περιγράμματος και άλλα για να προσαρμόσετε την εμφάνιση των κουμπιών επιλογής.

#### Ε: Πώς μπορώ να προσθέσω ομάδες κουμπιών επιλογής με αμοιβαία αποκλειστικές επιλογές;

Α: Για να δημιουργήσετε αμοιβαία αποκλειστικές επιλογές, μπορείτε να προσθέσετε πολλά πεδία κουμπιών επιλογής με το ίδιο όνομα. Αυτό θα διασφαλίσει ότι όταν επιλεγεί μία επιλογή, οι άλλες επιλογές με το ίδιο όνομα θα αποεπιλεγούν αυτόματα.

#### Ε: Είναι δυνατόν να ορίσετε μια προεπιλεγμένη επιλογή για τα κουμπιά επιλογής;

Α: Ναι, μπορείτε να ορίσετε μια προεπιλεγμένη επιλογή για τα κουμπιά επιλογής χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε το`Selected` ιδιοκτησία του`RadioButtonOptionField` αντικείμενο για να επισημάνετε μια επιλογή ως επιλεγμένη από προεπιλογή.

#### Ε: Μπορώ να προσθέσω προγράμματα χειρισμού συμβάντων στα κουμπιά επιλογής;

 Α: Ναι, μπορείτε να προσθέσετε προγράμματα χειρισμού συμβάντων στα κουμπιά επιλογής χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να συσχετίσετε ενέργειες JavaScript, όπως π.χ`OnValueChanged`, στα κουμπιά επιλογής για να εκτελέσετε συγκεκριμένες ενέργειες όταν ο χρήστης επιλέξει μια επιλογή.

#### Ε: Πώς μπορώ να ανακτήσω την επιλεγμένη επιλογή από την ομάδα κουμπιών επιλογής αφού ο χρήστης κάνει μια επιλογή;

 Α: Μπορείτε να ανακτήσετε την επιλεγμένη επιλογή από την ομάδα κουμπιών επιλογής χρησιμοποιώντας το Aspose.PDF για .NET. Αφού ο χρήστης κάνει μια επιλογή, μπορείτε να αποκτήσετε πρόσβαση στο`Selected` ιδιοκτησία του`RadioButtonOptionField` αντικείμενο για να ελέγξετε ποια επιλογή είναι επιλεγμένη.