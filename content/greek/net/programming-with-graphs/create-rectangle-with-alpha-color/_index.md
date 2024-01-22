---
title: Δημιουργήστε ορθογώνιο με χρώμα άλφα
linktitle: Δημιουργήστε ορθογώνιο με χρώμα άλφα
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε ένα ορθογώνιο με διαφανές χρώμα χρησιμοποιώντας το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα για την προσαρμογή της διαφάνειας.
type: docs
weight: 60
url: /el/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα στον ακόλουθο πηγαίο κώδικα C# για να δημιουργήσετε ένα ορθογώνιο με χρώμα άλφα χρησιμοποιώντας το Aspose.PDF για .NET.

Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.PDF και έχετε ρυθμίσει το περιβάλλον ανάπτυξης πριν ξεκινήσετε. Επίσης να έχει βασικές γνώσεις προγραμματισμού C#.

## Βήμα 1: Ρύθμιση καταλόγου εγγράφων

Στον παρεχόμενο πηγαίο κώδικα, πρέπει να καθορίσετε τον κατάλογο στον οποίο θέλετε να αποθηκεύσετε το αρχείο PDF που προκύπτει. Αλλάξτε τη μεταβλητή "dataDir" στον επιθυμητό κατάλογο.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία αντικειμένου εγγράφου και προσθήκη σελίδας

Δημιουργούμε μια παρουσία της κλάσης Document και προσθέτουμε μια σελίδα σε αυτό το έγγραφο.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Βήμα 3: Δημιουργία αντικειμένου γραφήματος και ορθογωνίου

Δημιουργούμε ένα αντικείμενο Graph με καθορισμένες διαστάσεις και ένα ορθογώνιο με συγκεκριμένες διαστάσεις.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Βήμα 4: Ρύθμιση του χρώματος άλφα για το ορθογώνιο

Μπορούμε να καθορίσουμε ένα χρώμα άλφα για το ορθογώνιο χρησιμοποιώντας τη μέθοδο FromArgb της κλάσης System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Βήμα 5: Προσθήκη του ορθογωνίου στο αντικείμενο του γραφήματος

Προσθέτουμε το ορθογώνιο στη συλλογή σχημάτων του αντικειμένου Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Βήμα 6: Δημιουργία δεύτερου ορθογωνίου με διαφορετικό χρώμα άλφα

Δημιουργούμε ένα δεύτερο παραλληλόγραμμο με συγκεκριμένες διαστάσεις και άλλο ένα άλφα χρώμα.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Βήμα 7: Προσθήκη του αντικειμένου γραφήματος στη σελίδα

Προσθέτουμε το αντικείμενο Graph στη συλλογή Paragraph του αντικειμένου Σελίδα.

```csharp
page.Paragraphs.Add(canvas);
```

## Βήμα 8: Αποθήκευση του αρχείου PDF που προκύπτει

Τέλος, αποθηκεύουμε το αρχείο PDF που προκύπτει με το όνομα "CreateRectangleWithAlphaColor_out.pdf" στον καθορισμένο κατάλογο.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Δείγμα πηγαίου κώδικα για το Create Rectangle With Alpha Color χρησιμοποιώντας Aspose.PDF για .NET 

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Στιγμιαίο παράδειγμα εγγράφου
Document doc = new Document();
// Προσθήκη σελίδας σε σελίδες συλλογής αρχείου PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Δημιουργία παρουσίας γραφήματος
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Δημιουργήστε ορθογώνιο αντικείμενο με συγκεκριμένες διαστάσεις
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Ορίστε το χρώμα πλήρωσης γραφήματος από τη δομή System.Drawing.Color από μια τιμή ARGB 32 bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Προσθήκη ορθογωνίου αντικειμένου στη συλλογή σχημάτων της παρουσίας γραφήματος
canvas.Shapes.Add(rect);
// Δημιουργήστε δεύτερο ορθογώνιο αντικείμενο
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Προσθήκη στιγμιότυπου γραφήματος στη συλλογή παραγράφων του αντικειμένου σελίδας
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Αποθήκευση αρχείου PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξηγήσαμε πώς να δημιουργήσετε ένα ορθογώνιο με χρώμα άλφα χρησιμοποιώντας το Aspose.PDF για .NET. Τώρα μπορείτε να χρησιμοποιήσετε αυτή τη γνώση για να δημιουργήσετε γεωμετρικά σχήματα με διαφανή χρώματα στα αρχεία PDF σας.

## Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο στοχεύει να σας καθοδηγήσει στη διαδικασία δημιουργίας ενός ορθογωνίου με χρώμα άλφα χρησιμοποιώντας το Aspose.PDF για .NET. Θα μάθετε πώς να προσθέτετε γεωμετρικά σχήματα με διαφανή χρώματα στα αρχεία PDF σας.

#### Ε: Ποιες προϋποθέσεις απαιτούνται πριν ξεκινήσετε;

Α: Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.PDF και ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξής σας. Επιπλέον, συνιστάται η βασική κατανόηση του προγραμματισμού C#.

#### Ε: Πώς μπορώ να καθορίσω τον κατάλογο για την αποθήκευση του αρχείου PDF;

Α: Στον παρεχόμενο πηγαίο κώδικα, μπορείτε να τροποποιήσετε τη μεταβλητή "dataDir" για να υποδείξετε τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που προκύπτει.

#### Ε: Ποιος είναι ο σκοπός του αντικειμένου Graph και του Rectangle;

Α: Το αντικείμενο Graph λειτουργεί ως κοντέινερ για τη σχεδίαση στοιχείων, ενώ το Ορθογώνιο αντιπροσωπεύει το γεωμετρικό σχήμα που θα προσθέσετε στο PDF.

#### Ε: Πώς μπορώ να ρυθμίσω ένα χρώμα άλφα για το ορθογώνιο;

Α: Μπορείτε να καθορίσετε ένα χρώμα άλφα για το ορθογώνιο χρησιμοποιώντας το`FillColor` ιδιοκτησία του`GraphInfo` αντικείμενο και το`Color.FromRgb` μέθοδος με τιμή ARGB.

#### Ε: Μπορώ να δημιουργήσω πολλά ορθογώνια με διαφορετικά χρώματα άλφα;

Α: Ναι, μπορείτε να δημιουργήσετε πολλά ορθογώνια με διαφορετικά χρώματα άλφα ακολουθώντας παρόμοια βήματα όπως φαίνεται στο σεμινάριο.

#### Ε: Πώς μπορώ να αποθηκεύσω το αρχείο PDF που προκύπτει αφού δημιουργήσω ορθογώνια με χρώματα άλφα;

 Α: Αφού δημιουργήσετε τα ορθογώνια με χρώματα άλφα, μπορείτε να αποθηκεύσετε το αρχείο PDF που προκύπτει χρησιμοποιώντας το`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` γραμμή στον παρεχόμενο πηγαίο κώδικα.