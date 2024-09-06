---
title: Κουμπί ραδιοφώνου με επιλογές
linktitle: Κουμπί ραδιοφώνου με επιλογές
second_title: Aspose.PDF για Αναφορά API .NET
description: Προσθέστε εύκολα ένα κουμπί επιλογής με επιλογές σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 230
url: /el/net/programming-with-forms/radio-button-with-options/
---

Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να προσθέσετε ένα κουμπί επιλογής με επιλογές σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# βήμα προς βήμα για να σας καθοδηγήσουμε σε αυτήν τη διαδικασία.

## Βήμα 1: Προετοιμασία

Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες βιβλιοθήκες και έχετε ορίσει τη διαδρομή προς τον κατάλογο των εγγράφων σας:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα αντικείμενο εγγράφου

Δημιουργήστε ένα αντικείμενο Document για να δημιουργήσετε ένα νέο έγγραφο PDF:

```csharp
Document doc = new Document();
```

## Βήμα 3: Προσθήκη σελίδας και πίνακα

Προσθέστε μια σελίδα στο έγγραφο και δημιουργήστε έναν πίνακα για να κρατήσετε τις επιλογές του κουμπιού επιλογής:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Βήμα 4: Δημιουργήστε ένα αντικείμενο πεδίου RadioButton

Δημιουργήστε ένα αντικείμενο RadioButtonField για να αναπαραστήσετε το κουμπί επιλογής:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Βήμα 5: Προσθέστε επιλογές κουμπιού επιλογής

Προσθέστε τις επιλογές του κουμπιού επιλογής στο αντικείμενο RadioButtonField:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## Βήμα 6: Προσαρμόστε τις επιλογές των κουμπιών επιλογής

Προσαρμόστε τις επιλογές των κουμπιών επιλογής ορίζοντας χαρακτηριστικά όπως περίγραμμα, χρώμα κειμένου και κείμενο λεζάντας:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Επαναλάβετε τα ίδια βήματα για το opt2 και το opt3

```

## Βήμα 7: Προσθέστε τις επιλογές του κουμπιού επιλογής στον πίνακα

Προσθέστε τις επιλογές του κουμπιού επιλογής στον πίνακα για να τις εμφανίσετε:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο PDF

Αποθηκεύστε το έγγραφο PDF που δημιουργήθηκε:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Δείγμα πηγαίου κώδικα για το κουμπί ραδιοφώνου με επιλογές χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
try
{
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Αποθηκεύστε το αρχείο PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Σύναψη

Συγχαρητήρια ! Προσθέσατε επιτυχώς ένα κουμπί επιλογής με επιλογές σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Τώρα μπορείτε να χρησιμοποιήσετε αυτήν τη μέθοδο για να δημιουργήσετε διαδραστικές φόρμες στα έγγραφά σας PDF.