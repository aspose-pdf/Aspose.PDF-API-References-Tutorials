---
title: पीडीएफ फाइल में संख्या शैली लागू करें
linktitle: पीडीएफ फाइल में संख्या शैली लागू करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में शीर्षकों पर क्रमांकन शैली लागू करना सीखें। चरण दर चरण मार्गदर्शिका.
type: docs
weight: 10
url: /hi/net/programming-with-headings/apply-number-style/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में नंबरिंग शैली लागू करने के लिए चरण दर चरण निम्नलिखित C# स्रोत कोड के बारे में बताएंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है। C# प्रोग्रामिंग का बुनियादी ज्ञान भी हो।

### चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए स्रोत कोड में, आपको उस निर्देशिका को निर्दिष्ट करना होगा जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं। "डेटाडिर" वेरिएबल को वांछित निर्देशिका में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### चरण 2: पीडीएफ दस्तावेज़ बनाना

हम निर्दिष्ट आयामों और हाशिये के साथ एक नया पीडीएफ दस्तावेज़ बनाते हैं।

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

### चरण 3: एक पेज और फ्लोटिंग कंटेनर बनाना

हम दस्तावेज़ में एक पेज जोड़ते हैं और सामग्री को व्यवस्थित करने के लिए एक फ्लोटिंग कंटेनर बनाते हैं।

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

हम निर्दिष्ट क्रमांकन के साथ हेडर बनाते हैं और उन्हें फ़्लोटिंग कंटेनर में जोड़ते हैं।

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

हम जेनरेट किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजते हैं।

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके संख्या शैली लागू करने के लिए नमूना स्रोत कोड 
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

इस ट्यूटोरियल में, हमने समझाया कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में शीर्षकों में नंबरिंग शैली कैसे लागू करें। अब आप इस ज्ञान का उपयोग शीर्षकों के लिए कस्टम नंबरिंग के साथ पीडीएफ दस्तावेज़ बनाने के लिए कर सकते हैं।

### पीडीएफ फ़ाइल में संख्या शैली लागू करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में क्रमांकन शैली क्या है?

उत्तर: क्रमांकन शैली उस प्रारूप को संदर्भित करती है जिसमें पीडीएफ दस्तावेज़ में शीर्षकों या अनुभागों को क्रमांकित किया जाता है। इसमें पदानुक्रमित संरचना प्रदान करने के लिए अंक, अक्षर या अन्य वर्ण शामिल हो सकते हैं।

#### प्रश्न: मुझे पीडीएफ दस्तावेज़ में शीर्षकों पर क्रमांकन शैली लागू करने की आवश्यकता क्यों होगी?

उत्तर: शीर्षकों में क्रमांकन शैली लागू करने से आपके पीडीएफ दस्तावेज़ की पठनीयता और संगठन में वृद्धि होती है। यह पाठकों को सामग्री की पदानुक्रमित संरचना को आसानी से नेविगेट करने और समझने में मदद करता है।

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उ: .NET के लिए Aspose.PDF एक लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से पीडीएफ फाइलों के साथ काम करने की अनुमति देती है। यह पीडीएफ दस्तावेजों को बनाने, संपादित करने, परिवर्तित करने और हेरफेर करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### प्रश्न: मैं अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी कैसे आयात करूं?

उ: अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करने के लिए, निम्नलिखित आयात निर्देश शामिल करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

ये निर्देश आपको पीडीएफ दस्तावेज़ों के साथ काम करने और नंबरिंग शैलियों को लागू करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंचने में सक्षम बनाते हैं।

#### प्रश्न: मैं जेनरेट की गई पीडीएफ फाइल को सहेजने के लिए निर्देशिका कैसे निर्दिष्ट करूं?

उ: दिए गए स्रोत कोड में, उस निर्देशिका को निर्दिष्ट करने के लिए "डेटाडिर" वेरिएबल को संशोधित करें जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` वास्तविक निर्देशिका पथ के साथ।

#### प्रश्न: मैं निर्दिष्ट आयामों और मार्जिन के साथ एक पीडीएफ दस्तावेज़ कैसे बना सकता हूं?

उ: निर्दिष्ट आयामों और हाशिये के साथ एक पीडीएफ दस्तावेज़ बनाने के लिए, निम्नलिखित कोड का उपयोग करें:

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

उ: पीडीएफ दस्तावेज़ में क्रमांकन शैली के साथ शीर्षक जोड़ने के लिए, शीर्षक बनाने और उनकी क्रमांकन शैली को अनुकूलित करने के लिए दिए गए कोड नमूनों का उपयोग करें। आवश्यकतानुसार टेक्स्ट, नंबरिंग स्टाइल, स्टार्ट नंबर और ऑटो अनुक्रम जैसे गुणों को समायोजित करें।

#### प्रश्न: मैं जेनरेट किए गए पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: जनरेट किए गए पीडीएफ दस्तावेज़ को सहेजने के लिए, का उपयोग करें`Save` की विधि`pdfDoc` वस्तु:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### प्रश्न: मैं कैसे पुष्टि कर सकता हूं कि नंबरिंग शैली लागू की गई है?

उ: यह सत्यापित करने के लिए जेनरेट की गई पीडीएफ फाइल खोलें कि निर्दिष्ट क्रमांकन शैली शीर्षकों पर लागू की गई है।

#### प्रश्न: क्या मैं क्रमांकन शैली को और अधिक अनुकूलित कर सकता हूँ?

 उत्तर: हाँ, आप गुणों को समायोजित करके क्रमांकन शैली को और अधिक अनुकूलित कर सकते हैं`Heading` ऑब्जेक्ट, जैसे क्रमांकन शैली प्रकार, प्रारंभ संख्या और ऑटो अनुक्रम।

#### प्रश्न: क्या मैं दस्तावेज़ के विभिन्न अनुभागों में अलग-अलग क्रमांकन शैलियाँ लागू कर सकता हूँ?

उ: हाँ, आप एकाधिक बनाकर दस्तावेज़ के विभिन्न अनुभागों में भिन्न क्रमांकन शैलियाँ लागू कर सकते हैं`Heading` विभिन्न शैलियों और अनुक्रमों वाली वस्तुएं।