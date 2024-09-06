---
title: पीडीएफ फाइल में नंबर स्टाइल लागू करें
linktitle: पीडीएफ फाइल में नंबर स्टाइल लागू करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शीर्षकों पर नंबरिंग शैली लागू करना सीखें। चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-headings/apply-number-style/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में नंबरिंग शैली लागू करने के लिए निम्नलिखित C# स्रोत कोड के माध्यम से चरण दर चरण मार्गदर्शन करेंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना डेवलपमेंट एनवायरनमेंट सेट कर लिया है। साथ ही C# प्रोग्रामिंग का बुनियादी ज्ञान भी रखें।

### चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए सोर्स कोड में, आपको वह डायरेक्टरी निर्दिष्ट करनी होगी जहाँ आप जेनरेट की गई PDF फ़ाइल को सहेजना चाहते हैं। "dataDir" वैरिएबल को वांछित डायरेक्टरी में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### चरण 2: पीडीएफ दस्तावेज़ बनाना

हम निर्दिष्ट आयामों और मार्जिन के साथ एक नया पीडीएफ दस्तावेज़ बनाते हैं।

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### चरण 3: पेज और फ्लोटिंग कंटेनर बनाना

हम दस्तावेज़ में एक पृष्ठ जोड़ते हैं और सामग्री को व्यवस्थित करने के लिए एक फ़्लोटिंग कंटेनर बनाते हैं।

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### चरण 4: क्रमांकन के साथ शीर्षक जोड़ें

हम निर्दिष्ट नंबरिंग के साथ हेडर बनाते हैं और उन्हें फ्लोटिंग कंटेनर में जोड़ते हैं।

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### चरण 5: पीडीएफ दस्तावेज़ को सहेजना

हम उत्पन्न पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं।

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके नंबर स्टाइल लागू करने के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने बताया कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में शीर्षकों पर नंबरिंग शैली कैसे लागू करें। अब आप इस ज्ञान का उपयोग शीर्षकों के लिए कस्टम नंबरिंग के साथ PDF दस्तावेज़ बनाने के लिए कर सकते हैं।

### पीडीएफ फाइल में नंबर शैली लागू करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में नंबरिंग शैली क्या है?

उत्तर: क्रमांकन शैली उस प्रारूप को संदर्भित करती है जिसमें PDF दस्तावेज़ में शीर्षकों या अनुभागों को क्रमांकित किया जाता है। इसमें पदानुक्रमित संरचना प्रदान करने के लिए अंक, अक्षर या अन्य वर्ण शामिल हो सकते हैं।

#### प्रश्न: मुझे PDF दस्तावेज़ में शीर्षकों पर क्रमांकन शैली लागू करने की आवश्यकता क्यों होगी?

उत्तर: शीर्षकों पर नंबरिंग शैली लागू करने से आपके PDF दस्तावेज़ की पठनीयता और संगठन में सुधार होता है। यह पाठकों को आसानी से नेविगेट करने और सामग्री की पदानुक्रमिक संरचना को समझने में मदद करता है।

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उत्तर: .NET के लिए Aspose.PDF एक लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से PDF फ़ाइलों के साथ काम करने की अनुमति देती है। यह PDF दस्तावेज़ों को बनाने, संपादित करने, परिवर्तित करने और हेरफेर करने के लिए कई प्रकार की सुविधाएँ प्रदान करता है।

#### प्रश्न: मैं अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ कैसे आयात करूं?

उत्तर: अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ आयात करने के लिए, निम्नलिखित आयात निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

ये निर्देश आपको PDF दस्तावेज़ों के साथ काम करने और नंबरिंग शैलियों को लागू करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंचने में सक्षम बनाते हैं।

#### प्रश्न: मैं उत्पन्न पीडीएफ फाइल को सहेजने के लिए निर्देशिका कैसे निर्दिष्ट करूं?

उत्तर: दिए गए स्रोत कोड में, "dataDir" वेरिएबल को संशोधित करके वह निर्देशिका निर्दिष्ट करें जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` वास्तविक निर्देशिका पथ के साथ.

#### प्रश्न: मैं निर्दिष्ट आयाम और मार्जिन के साथ पीडीएफ दस्तावेज़ कैसे बनाऊं?

उत्तर: निर्दिष्ट आयाम और मार्जिन के साथ एक पीडीएफ दस्तावेज़ बनाने के लिए, निम्नलिखित कोड का उपयोग करें:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में क्रमांकन शैली के साथ शीर्षक कैसे जोड़ूं?

उत्तर: पीडीएफ दस्तावेज़ में नंबरिंग शैली के साथ शीर्षक जोड़ने के लिए, शीर्षक बनाने और उनकी नंबरिंग शैलियों को अनुकूलित करने के लिए दिए गए कोड नमूनों का उपयोग करें। आवश्यकतानुसार टेक्स्ट, नंबरिंग शैली, आरंभ संख्या और स्वचालित अनुक्रम जैसे गुणों को समायोजित करें।

#### प्रश्न: मैं उत्पन्न पीडीएफ दस्तावेज़ को कैसे सहेजूँ?

 उत्तर: उत्पन्न पीडीएफ दस्तावेज़ को सहेजने के लिए, का उपयोग करें`Save` की विधि`pdfDoc` वस्तु:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### प्रश्न: मैं कैसे पुष्टि कर सकता हूं कि नंबरिंग शैली लागू की गई है?

उत्तर: यह सत्यापित करने के लिए कि निर्दिष्ट क्रमांकन शैली शीर्षकों पर लागू की गई है, उत्पन्न पीडीएफ फाइल खोलें।

#### प्रश्न: क्या मैं नंबरिंग शैली को और अधिक अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप इसके गुणों को समायोजित करके नंबरिंग शैली को और भी अनुकूलित कर सकते हैं।`Heading` ऑब्जेक्ट्स, जैसे कि नंबरिंग शैली प्रकार, प्रारंभ संख्या और स्वचालित अनुक्रम।

#### प्रश्न: क्या मैं दस्तावेज़ के विभिन्न अनुभागों पर अलग-अलग क्रमांकन शैलियाँ लागू कर सकता हूँ?

 उत्तर: हां, आप कई टेम्पलेट बनाकर दस्तावेज़ के विभिन्न अनुभागों पर अलग-अलग नंबरिंग शैलियाँ लागू कर सकते हैं।`Heading` विभिन्न शैलियों और अनुक्रमों वाली वस्तुएं।