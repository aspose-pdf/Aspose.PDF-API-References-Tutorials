---
title: पीडीएफ फाइल में सभी टेक्स्ट हटाएं
linktitle: पीडीएफ फाइल में सभी टेक्स्ट हटाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में सभी टेक्स्ट को हटाने का तरीका जानें।
type: docs
weight: 280
url: /hi/net/programming-with-text/remove-all-text/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ फाइल में सभी टेक्स्ट को कैसे हटाया जाए। हम पीडीएफ खोलने, प्रत्येक पृष्ठ से टेक्स्ट को चुनने और हटाने और दिए गए सी# स्रोत कोड का उपयोग करके संशोधित पीडीएफ को सहेजने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित किया गया।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस निर्देशिका के लिए पथ सेट करना होगा जहां आपकी पीडीएफ फाइलें स्थित हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` आपकी पीडीएफ फाइलों के पथ के साथ परिवर्तनशील।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: पीडीएफ दस्तावेज़ खोलें

 इसके बाद, हम इसका उपयोग करके पीडीएफ दस्तावेज़ खोलते हैं`Document` Aspose.PDF लाइब्रेरी से कक्षा।

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## चरण 3: प्रत्येक पृष्ठ से टेक्स्ट हटाएँ

 हम पीडीएफ दस्तावेज़ के सभी पृष्ठों को लूप करते हैं और एक का उपयोग करते हैं`OperatorSelector` प्रत्येक पृष्ठ पर सभी पाठ का चयन करने के लिए। फिर, हम चयनित टेक्स्ट को हटा देते हैं।

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## चरण 4: संशोधित पीडीएफ को सहेजें

अंत में, हम संशोधित पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### .NET के लिए Aspose.PDF का उपयोग करके सभी टेक्स्ट हटाने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// पीडीएफ दस्तावेज़ के सभी पृष्ठों को लूप करें
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// पृष्ठ पर सभी पाठ का चयन करें
	page.Contents.Accept(operatorSelector);
	// सभी पाठ हटाएँ
	page.Contents.Delete(operatorSelector.Selected);
}
// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ से सभी टेक्स्ट को कैसे हटाया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक पीडीएफ खोल सकते हैं, प्रत्येक पृष्ठ से टेक्स्ट का चयन कर सकते हैं और हटा सकते हैं, और संशोधित पीडीएफ को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "पीडीएफ फाइल में सभी टेक्स्ट हटाएं" ट्यूटोरियल का उद्देश्य क्या है?

उ: "पीडीएफ फाइल में सभी टेक्स्ट हटाएं" ट्यूटोरियल का उद्देश्य यह प्रदर्शित करना है कि पीडीएफ दस्तावेज़ से सभी टेक्स्ट को हटाने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग कैसे करें। ट्यूटोरियल आपको एक पीडीएफ दस्तावेज़ खोलने, प्रत्येक पृष्ठ से पाठ का चयन करने और हटाने और संशोधित पीडीएफ को सहेजने में मदद करने के लिए चरण-दर-चरण मार्गदर्शिका और सी # स्रोत कोड प्रदान करता है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ से सभी पाठ क्यों हटाना चाहूंगा?

उ: ऐसे कई परिदृश्य हैं जहां पीडीएफ दस्तावेज़ से सभी पाठ को हटाना उपयोगी हो सकता है। उदाहरण के लिए, हो सकता है कि आप संवेदनशील जानकारी को हटाकर किसी दस्तावेज़ का संशोधित संस्करण बनाना चाहें, या आपको दस्तावेज़ की पाठ्य सामग्री के बिना उसका एक दृश्य प्रतिनिधित्व तैयार करने की आवश्यकता हो सकती है।

#### प्रश्न: मैं दस्तावेज़ निर्देशिका कैसे सेट करूँ?

उ: दस्तावेज़ निर्देशिका स्थापित करने के लिए:

1.  प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir` उस निर्देशिका के पथ के साथ परिवर्तनीय जहां आपकी पीडीएफ फाइलें स्थित हैं।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ के प्रत्येक पृष्ठ से टेक्स्ट कैसे हटाऊं?

 उ: ट्यूटोरियल आपको पीडीएफ दस्तावेज़ के सभी पृष्ठों के माध्यम से लूपिंग की प्रक्रिया के माध्यम से मार्गदर्शन करता है, प्रत्येक पृष्ठ पर सभी टेक्स्ट का उपयोग करके चयन करता है।`OperatorSelector`, और फिर चयनित पाठ को हटा दें।

#### प्रश्न: क्या मैं विशिष्ट पृष्ठों से पाठ को चुनिंदा रूप से हटा सकता हूँ?

उत्तर: हाँ, आप जिस पृष्ठ संख्या को संसाधित करना चाहते हैं उसे निर्दिष्ट करके विशिष्ट पृष्ठों से पाठ को चुनिंदा रूप से हटाने के लिए लूप को संशोधित कर सकते हैं। ट्यूटोरियल में दिया गया उदाहरण दर्शाता है कि सभी पृष्ठों के माध्यम से कैसे लूप किया जाए, लेकिन आप अपनी आवश्यकताओं को पूरा करने के लिए इसे समायोजित कर सकते हैं।

#### प्रश्न: मैं संशोधित पीडीएफ दस्तावेज़ को कैसे सहेजूं?

 उ: प्रत्येक पृष्ठ से पाठ हटाने के बाद, आप इसका उपयोग करके संशोधित पीडीएफ दस्तावेज़ को सहेज सकते हैं`Save` की विधि`Document`कक्षा। वांछित आउटपुट फ़ाइल पथ प्रदान करें और वांछित सेव प्रारूप को तर्क के रूप में निर्दिष्ट करें`Save` तरीका।

#### प्रश्न: इस ट्यूटोरियल का अपेक्षित आउटपुट क्या है?

उ: ट्यूटोरियल का अनुसरण करके और दिए गए C# कोड को निष्पादित करके, आप एक संशोधित पीडीएफ दस्तावेज़ तैयार करेंगे जहां प्रत्येक पृष्ठ पर सभी पाठ हटा दिए गए हैं।

#### प्रश्न: क्या मैं अन्य प्रकार की सामग्री को हटाने के लिए विभिन्न ऑपरेटरों का उपयोग कर सकता हूँ?

उ: हां, आप पीडीएफ दस्तावेज़ से विभिन्न प्रकार की सामग्री, जैसे चित्र या ग्राफिकल तत्वों को लक्षित करने और हटाने के लिए विभिन्न ऑपरेटरों का उपयोग कर सकते हैं। ट्यूटोरियल में दिया गया उदाहरण विशेष रूप से टेक्स्ट को हटाने पर केंद्रित है।

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध Aspose लाइसेंस आवश्यक है?

उत्तर: हां, इस ट्यूटोरियल को सही ढंग से काम करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से पूर्ण लाइसेंस खरीद सकते हैं या 30-दिवसीय अस्थायी लाइसेंस प्राप्त कर सकते हैं।