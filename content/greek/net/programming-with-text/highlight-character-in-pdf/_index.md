---
title: Επισημάνετε τον χαρακτήρα σε αρχείο PDF
linktitle: Επισημάνετε τον χαρακτήρα σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να επισημαίνετε χαρακτήρες σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 240
url: /el/net/programming-with-text/highlight-character-in-pdf/
---
Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να επισημάνετε χαρακτήρες σε ένα αρχείο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Θα ακολουθήσουμε τη διαδικασία βήμα προς βήμα για την επισήμανση χαρακτήρων σε ένα PDF χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#.

## Απαιτήσεις

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
- Βασική κατανόηση του προγραμματισμού C#.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων

 Αρχικά, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου βρίσκεται το αρχείο εισόδου PDF. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς το αρχείο PDF σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο PDF

 Στη συνέχεια, φορτώνουμε το εισαγόμενο έγγραφο PDF χρησιμοποιώντας το`Aspose.Pdf.Document` τάξη.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Βήμα 3: Μετατροπή PDF σε Εικόνα

 Για να επισημάνουμε χαρακτήρες, μετατρέπουμε το έγγραφο PDF σε εικόνα χρησιμοποιώντας το`PdfConverter` τάξη. Ορίζουμε την ανάλυση για τη μετατροπή και ανακτούμε την εικόνα ως α`Bitmap` αντικείμενο.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Βήμα 4: Επισημάνετε τους χαρακτήρες

 Κάνουμε κύκλο σε κάθε σελίδα του εγγράφου PDF και χρησιμοποιούμε α`TextFragmentAbsorber` αντικείμενο για να βρείτε όλες τις λέξεις στη σελίδα. Στη συνέχεια επαναλαμβάνουμε τα τμήματα κειμένου, τα τμήματα και τους χαρακτήρες για να τα επισημάνουμε χρησιμοποιώντας ορθογώνια.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Ρύθμιση κλίμακας και μεταμόρφωση
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Περιηγηθείτε στις σελίδες
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Βρείτε όλες τις λέξεις στη σελίδα
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Κάντε βρόχο μέσα από θραύσματα κειμένου
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Επισημάνετε χαρακτήρες
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Βρόχος μέσα από τμήματα
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Επισήμανση τμήματος
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Περιηγηθείτε στους χαρακτήρες
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Χαρακτήρας επισήμανσης
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Βήμα 5: Αποθηκεύστε την εικόνα εξόδου

Τέλος, αποθηκεύουμε την τροποποιημένη εικόνα με τους επισημασμένους χαρακτήρες στο καθορισμένο αρχείο εξόδου.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Δείγμα πηγαίου κώδικα για τον χαρακτήρα επισήμανσης σε PDF χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
try
{
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις λέξεις
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Λάβετε τα εξαγόμενα τμήματα κειμένου
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Περιηγηθείτε στα θραύσματα
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Σύναψη

Σε αυτό το σεμινάριο, έχετε μάθει πώς να επισημαίνετε χαρακτήρες σε ένα έγγραφο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και εκτελώντας τον παρεχόμενο κώδικα C#, μπορείτε να επισημάνετε χαρακτήρες σε ένα PDF και να αποθηκεύσετε την έξοδο ως εικόνα.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Highlight Character In PDF File";

Α: Το σεμινάριο "Επισήμανση χαρακτήρα σε αρχείο PDF" εξηγεί πώς να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για .NET για να επισημάνετε χαρακτήρες σε ένα έγγραφο PDF. Το σεμινάριο παρέχει έναν οδηγό βήμα προς βήμα και τον πηγαίο κώδικα C# για να το πετύχετε.

#### Ε: Γιατί θα ήθελα να επισημάνω χαρακτήρες σε ένα έγγραφο PDF;

Α: Η επισήμανση χαρακτήρων σε ένα έγγραφο PDF μπορεί να είναι χρήσιμη για διάφορους σκοπούς, όπως η έμφαση σε συγκεκριμένο περιεχόμενο ή για να γίνει πιο ορατό και διακριτό συγκεκριμένο κείμενο.

#### Ε: Πώς μπορώ να ρυθμίσω τον κατάλογο εγγράφων;

Α: Για να ρυθμίσετε τον κατάλογο εγγράφων:

1.  Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς τον κατάλογο όπου βρίσκεται το αρχείο εισόδου PDF.

#### Ε: Πώς μπορώ να φορτώσω το έγγραφο PDF και να το μετατρέψω σε εικόνα;

 Α: Στο φροντιστήριο, το`Aspose.Pdf.Document` Η κλάση χρησιμοποιείται για τη φόρτωση του εισαγόμενου εγγράφου PDF. Στη συνέχεια, το`PdfConverter` Η κλάση χρησιμοποιείται για τη μετατροπή του εγγράφου PDF σε εικόνα. Η ανάλυση της εικόνας ορίζεται και η εικόνα ανακτάται ως α`Bitmap` αντικείμενο.

#### Ε: Πώς μπορώ να επισημάνω χαρακτήρες στην εικόνα του εγγράφου PDF;

Α: Το σεμινάριο σάς καθοδηγεί στη διαδικασία αναζήτησης σε κάθε σελίδα του εγγράφου PDF, εύρεση λέξεων χρησιμοποιώντας ένα`TextFragmentAbsorber`, και επανάληψη μέσω τμημάτων κειμένου, τμημάτων και χαρακτήρων για να τα επισημάνετε χρησιμοποιώντας ορθογώνια.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση των επισημασμένων χαρακτήρων και τμημάτων;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των επισημασμένων χαρακτήρων και τμημάτων τροποποιώντας τα χρώματα και τα στυλ που χρησιμοποιούνται στις λειτουργίες σχεδίασης.

#### Ε: Πώς μπορώ να αποθηκεύσω την τροποποιημένη εικόνα με τους επισημασμένους χαρακτήρες;

 Α: Το σεμινάριο δείχνει πώς να αποθηκεύσετε την τροποποιημένη εικόνα με τους επισημασμένους χαρακτήρες στο καθορισμένο αρχείο εξόδου χρησιμοποιώντας το`Save` μέθοδος του`Bitmap` τάξη.

#### Ε: Απαιτείται έγκυρη άδεια Aspose για αυτό το σεμινάριο;

Α: Ναι, απαιτείται έγκυρη άδεια Aspose για να λειτουργήσει σωστά αυτό το σεμινάριο. Μπορείτε να αγοράσετε μια πλήρη άδεια χρήσης ή να αποκτήσετε μια προσωρινή άδεια 30 ημερών από τον ιστότοπο Aspose.