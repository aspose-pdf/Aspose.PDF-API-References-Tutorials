---
title: Εισαγωγή Διακοπής σελίδας σε αρχείο PDF
linktitle: Εισαγωγή Διακοπής σελίδας σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εισάγετε μια αλλαγή σελίδας σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 110
url: /el/net/programming-with-tables/insert-page-break/
---
Σε αυτό το σεμινάριο, θα μάθουμε πώς να εισάγετε μια αλλαγή σελίδας σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα σε C# βήμα προς βήμα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να προσθέσετε μια αλλαγή σελίδας μετά από έναν ορισμένο αριθμό γραμμών σε έναν πίνακα ενός εγγράφου PDF. Ας αρχίσουμε!

## Βήμα 1: Ρύθμιση περιβάλλοντος
Βεβαιωθείτε ότι έχετε διαμορφώσει το περιβάλλον ανάπτυξης C# με το Aspose.PDF για .NET. Προσθέστε την αναφορά στη βιβλιοθήκη και εισαγάγετε τους απαραίτητους χώρους ονομάτων.

## Βήμα 2: Δημιουργία εγγράφου και πίνακα
Δημιουργούμε μια νέα παρουσία εγγράφου και προσθέτουμε μια σελίδα σε αυτό το έγγραφο. Στη συνέχεια, δημιουργούμε μια παρουσία πίνακα για να αναπαραστήσουμε τον πίνακά μας στο έγγραφο PDF. Ορίζουμε επίσης τα στυλ περιγράμματος για τον πίνακα.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Βήμα 3: Προσθήκη σειρών στον πίνακα
Χρησιμοποιούμε έναν βρόχο για να προσθέσουμε 200 σειρές στον πίνακα. Για κάθε σειρά, δημιουργούμε μια παρουσία της σειράς και προσθέτουμε δύο κελιά με περιεχόμενο κειμένου.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Όταν προστεθούν 10 γραμμές, εισάγουμε μια νέα αλλαγή σελίδας
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Βήμα 4: Προσθήκη του πίνακα στο έγγραφο
Προσθέτουμε τον πίνακα στη συλλογή παραγράφων της σελίδας του εγγράφου.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
Αποθηκεύουμε το έγγραφο PDF με την εισαγωγή της αλλαγής σελίδας.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Παράδειγμα πηγαίου κώδικα για Εισαγωγή αλλαγής σελίδας χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Στιγμιαίο παράδειγμα εγγράφου
Document doc = new Document();
// Προσθήκη σελίδας σε σελίδες συλλογής αρχείου PDF
doc.Pages.Add();
// Δημιουργία παρουσίας πίνακα
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Ορίστε στυλ περιγράμματος για τραπέζι
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Ορίστε το προεπιλεγμένο στυλ περιγράμματος για τραπέζι με χρώμα περιγράμματος ως Κόκκινο
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Καθορίστε το πλάτος στηλών του πίνακα
tab.ColumnWidths = "100 100";
// Δημιουργήστε έναν βρόχο για να προσθέσετε 200 σειρές για τον πίνακα
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Όταν προστεθούν 10 σειρές, αποδώστε τη νέα σειρά σε νέα σελίδα
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Προσθήκη πίνακα στη συλλογή παραγράφων του αρχείου PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Αποθηκεύστε το έγγραφο PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εισάγουμε μια αλλαγή σελίδας σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε αυτόν τον οδηγό βήμα προς βήμα για να προσθέσετε μια αλλαγή σελίδας μετά από έναν ορισμένο αριθμό γραμμών σε έναν πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας C#.

### Συχνές ερωτήσεις για την εισαγωγή αλλαγής σελίδας σε αρχείο PDF

#### Ε: Πώς μπορώ να αλλάξω το μέγεθος σελίδας για τις νέες σελίδες που δημιουργήθηκαν μετά την αλλαγή σελίδας;

 Α: Για να αλλάξετε το μέγεθος σελίδας για τις νέες σελίδες που δημιουργήθηκαν μετά την αλλαγή σελίδας, μπορείτε να ορίσετε το`PageSize` ιδιοκτησία του`Page` αντικείμενο. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα για να ορίσετε το μέγεθος σελίδας σε A4:

```csharp
// Ορίστε το μέγεθος σελίδας σε Α4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Ε: Μπορώ να ελέγξω τα περιθώρια σελίδας για τις νέες σελίδες μετά την αλλαγή σελίδας;

 Α: Ναι, μπορείτε να ελέγξετε τα περιθώρια σελίδας για τις νέες σελίδες μετά την αλλαγή σελίδας. Χρησιμοποιήστε το`Margin` ιδιοκτησία του`Page` αντικείμενο για να ορίσετε τα περιθώρια σελίδας. Για παράδειγμα, για να ορίσετε όλα τα περιθώρια σε 10 σημεία, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```csharp
// Ορίστε όλα τα περιθώρια σε 10 πόντους
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Ε: Είναι δυνατή η προσθήκη κεφαλίδων και υποσέλιδων στις νέες σελίδες μετά την αλλαγή σελίδας;

 Α: Ναι, μπορείτε να προσθέσετε κεφαλίδες και υποσέλιδα στις νέες σελίδες μετά την αλλαγή σελίδας. Χρησιμοποιήστε το`Page.Header` και`Page.Footer` ιδιότητες για να προσθέσετε περιεχόμενο στις ενότητες κεφαλίδας και υποσέλιδου της σελίδας. Για παράδειγμα:

```csharp
// Προσθήκη κεφαλίδας στις νέες σελίδες
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Προσθήκη υποσέλιδου στις νέες σελίδες
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Ε: Μπορώ να εισαγάγω αλλαγές σελίδας σε συγκεκριμένες τοποθεσίες εκτός από έναν συγκεκριμένο αριθμό σειρών;

 Α: Ναι, μπορείτε να εισαγάγετε αλλαγές σελίδας σε συγκεκριμένες τοποθεσίες εκτός από έναν συγκεκριμένο αριθμό σειρών. Μπορείτε να ορίσετε το`IsInNewPage` ιδιοκτησία μιας σειράς προς`true` για να αναγκάσετε τον πίνακα να ξεκινήσει μια νέα σελίδα μετά από αυτήν τη σειρά.

#### Ε: Πώς μπορώ να προσαρμόσω τη συμπεριφορά αλλαγής σελίδας με βάση το ύψος του περιεχομένου;

Α: Μπορείτε να χρησιμοποιήσετε το`IsBroken` ιδιότητα του πίνακα για την ενεργοποίηση ή απενεργοποίηση της αυτόματης αλλαγής σειρών στις σελίδες. Όταν έχει οριστεί σε`true`, επιτρέπει στις σειρές να σπάσουν στις σελίδες με βάση το ύψος του περιεχομένου.