---
title: स्टाइल टेबल सेल
linktitle: स्टाइल टेबल सेल
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ टेबल सेल को स्टाइल करना सीखें। तालिकाएँ बनाने और अनुकूलित करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 160
url: /hi/net/programming-with-tagged-pdf/style-table-cell/
---
.NET के लिए Aspose.PDF का उपयोग करके तालिका कोशिकाओं को फ़ॉर्मेट करने पर इस विस्तृत ट्यूटोरियल में आपका स्वागत है। इस गाइड में, हम आपको टेबल सेल को स्टाइल करने के तरीके को समझने में मदद करने के लिए दिए गए C# स्रोत कोड के प्रत्येक चरण के बारे में विस्तार से बताएंगे। सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF स्थापित कर लिया है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपने विकास परिवेश को कॉन्फ़िगर कर लिया है। इसमें Aspose.PDF लाइब्रेरी स्थापित करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

## चरण 2: एक दस्तावेज़ बनाना

इस चरण में, हम एक नया दस्तावेज़ ऑब्जेक्ट Aspose.PDF बनाएंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

हमने एक नया दस्तावेज़ बनाया है और दस्तावेज़ का शीर्षक और भाषा निर्धारित की है।

## चरण 3: मूल संरचना तत्व प्राप्त करना

इस चरण में हम अपने दस्तावेज़ के लिए मूल संरचना तत्व प्राप्त करेंगे।

```csharp
//मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
```

हमें मूल संरचना तत्व मिला जो सरणी तत्वों के लिए एक कंटेनर के रूप में काम करेगा।

## चरण 4: सरणी संरचना तत्व बनाना

आइए अब अपने दस्तावेज़ के लिए एक नया तालिका संरचना तत्व बनाएं।

```csharp
// सरणी संरचना तत्व बनाएं
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

हमने एक नया ऐरे स्ट्रक्चर एलिमेंट बनाया है और इसे रूट स्ट्रक्चर एलिमेंट में जोड़ा है। हमने टेबल हेडर, बॉडी और फ़ुटर तत्व भी बनाए।

## चरण 5: टेबल हेडर जोड़ना

इस चरण में हम टेबल हेडर को अपनी टेबल में जोड़ेंगे।

```csharp
// तालिका में पंक्तियों और स्तंभों की संख्या
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// टेबल हेडर पंक्ति बनाएं
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

हमने अपनी तालिका के लिए एक हेडर पंक्ति बनाई और पृष्ठभूमि रंग, बॉर्डर, मार्जिन और संरेखण जैसे स्वरूपण गुणों के साथ हेडर सेल जोड़े।

## चरण 6: तालिका की मुख्य पंक्तियाँ जोड़ना

आइए अब टेबल बॉडी पंक्तियों को अपनी टेबल में जोड़ें।
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

हमने प्रत्येक तालिका सेल पर पुनरावृति करने के लिए लूप का उपयोग करके तालिका के मुख्य भाग में पंक्तियाँ जोड़ीं। हम प्रत्येक सेल के लिए फ़ॉर्मेटिंग गुण सेट करते हैं, जैसे पृष्ठभूमि रंग, बॉर्डर, मार्जिन, टेक्स्ट संरेखण, आदि।

## चरण 7: पादलेख जोड़ना

अंत में, हम टेबल फ़ूटर को अपनी टेबल में जोड़ देंगे।

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

हमने अपनी तालिका के लिए एक पाद लेख बनाया और पाठ के साथ पाद लेख कक्ष जोड़े।



## चरण 8: टैग किए गए पीडीएफ दस्तावेज़ को सहेजना

अब जब हमने अपना दस्तावेज़ स्टाइल तालिका के साथ बना लिया है, तो हम इसे टैग किए गए पीडीएफ दस्तावेज़ के रूप में सहेजेंगे।

```csharp
// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableCell.pdf");
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजा है।

## चरण 9: पीडीएफ/यूए अनुपालन सत्यापन

इसके बाद, हम अपने दस्तावेज़ की पीडीएफ/यूए अनुरूपता को सत्यापित करेंगे।

```csharp
// पीडीएफ/यूए अनुपालन जांच
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को अपलोड किया और एक एक्सएमएल रिपोर्ट तैयार करके इसके पीडीएफ/यूए अनुपालन को मान्य किया।

### .NET के लिए Aspose.PDF का उपयोग करके स्टाइल टेबल सेल के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// जड़ संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// तालिका संरचना तत्व बनाएं
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableCell.pdf");

// पीडीएफ/यूए अनुपालन की जाँच करना
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके टेबल सेल को कैसे स्टाइल किया जाए। हमने देखा है कि दस्तावेज़ कैसे बनाएं, हेडर, बॉडी रो और फ़ुटर के साथ एक तालिका जोड़ें और सेल शैलियों को कस्टमाइज़ करें। अंत में, हमने टैग किए गए पीडीएफ दस्तावेज़ को सहेजा और इसके पीडीएफ/यूए अनुपालन को सत्यापित किया। अब आप अपने .NET अनुप्रयोगों में टेबल बनाने और स्टाइल करने के लिए .NET के लिए Aspose.PDF का उपयोग कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके तालिका कोशिकाओं को फ़ॉर्मेट करने पर इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ में टेबल सेल को कैसे स्टाइल किया जाए, इस पर एक व्यापक गाइड प्रदान करना है। इसमें टेबल सेल फ़ॉर्मेटिंग को समझने और कार्यान्वित करने में आपकी सहायता के लिए चरण-दर-चरण निर्देश और C# स्रोत कोड उदाहरण शामिल हैं।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए आवश्यक शर्तें क्या हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF स्थापित कर लिया है और अपना विकास वातावरण स्थापित कर लिया है। इसमें Aspose.PDF लाइब्रेरी को संदर्भित करने के लिए आपके प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक नया PDF दस्तावेज़ कैसे बना सकता हूँ?

उ: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, आपको एक इंस्टेंटियेट करना होगा`Document` Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। प्रदान किया गया C# स्रोत कोड दर्शाता है कि दस्तावेज़ कैसे बनाया जाए और उसका शीर्षक और भाषा कैसे निर्धारित की जाए।

#### प्रश्न: पीडीएफ दस्तावेज़ में मूल संरचना तत्व का क्या महत्व है?

ए: मूल संरचना तत्व अन्य संरचना तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जो पीडीएफ दस्तावेज़ की सामग्री को व्यवस्थित और वर्गीकृत करने में मदद करता है। यह दस्तावेज़ की तार्किक संरचना स्थापित करने में महत्वपूर्ण भूमिका निभाता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक तालिका संरचना तत्व कैसे बना सकता हूं और उसके स्वरूप को कैसे अनुकूलित कर सकता हूं?

 उ: आप इसका उपयोग करके एक तालिका संरचना तत्व बना सकते हैं`CreateTableElement()` तरीका। प्रदान किया गया स्रोत कोड दर्शाता है कि पृष्ठभूमि रंग, बॉर्डर, मार्जिन और संरेखण जैसे गुणों को सेट करके, इसके हेडर, बॉडी और पाद लेख सहित तालिका की उपस्थिति को कैसे अनुकूलित किया जाए।

#### प्रश्न: क्या मैं तालिका के मुख्य भाग में अनेक पंक्तियाँ और स्तंभ जोड़ सकता हूँ और उनके स्वरूपण को अनुकूलित कर सकता हूँ?

उ: हाँ, ट्यूटोरियल दर्शाता है कि लूप का उपयोग करके तालिका के मुख्य भाग में एकाधिक पंक्तियाँ और कॉलम कैसे जोड़े जाएं। यह सेल फ़ॉर्मेटिंग को अनुकूलित करने के उदाहरण भी प्रदान करता है, जैसे पृष्ठभूमि रंग, बॉर्डर, टेक्स्ट संरेखण, फ़ॉन्ट शैली और बहुत कुछ।

#### प्रश्न: पीडीएफ/यूए अनुपालन को सत्यापित करने का उद्देश्य क्या है, और मैं यह सत्यापन कैसे कर सकता हूं?

 उत्तर: पीडीएफ/यूए अनुपालन को मान्य करने से यह सुनिश्चित होता है कि पीडीएफ दस्तावेज़ पहुंच मानकों का पालन करता है, जिससे यह विकलांग उपयोगकर्ताओं के लिए अधिक सुलभ हो जाता है। ट्यूटोरियल दिखाता है कि इसका उपयोग करके पीडीएफ/यूए अनुरूपता को कैसे मान्य किया जाए`Validate()` विधि और एक XML रिपोर्ट तैयार करें।

#### प्रश्न: मैं इन अवधारणाओं को अपने .NET अनुप्रयोगों पर कैसे लागू कर सकता हूं?

उ: आप अपने स्वयं के .NET अनुप्रयोगों में टेबल सेल फ़ॉर्मेटिंग को लागू करने के लिए एक गाइड के रूप में दिए गए C# स्रोत कोड उदाहरणों का उपयोग कर सकते हैं। अपनी आवश्यकताओं के अनुरूप कोड को आवश्यकतानुसार अनुकूलित करें और इसे अपनी परियोजनाओं में एकीकृत करें।

#### प्रश्न: क्या पीडीएफ दस्तावेजों में टेबल सेल को स्टाइल करने के लिए कोई अनुशंसित सर्वोत्तम अभ्यास हैं?

उ: टेबल सेल को स्टाइल करते समय, पहुंच संबंधी आवश्यकताओं सहित अपने दर्शकों की जरूरतों पर विचार करें। पठनीयता बढ़ाने के लिए विपरीत रंगों, उपयुक्त फ़ॉन्ट और स्पष्ट सेल संरेखण का उपयोग करें। इसके अतिरिक्त, पहुंच मानकों को पूरा करने के लिए पीडीएफ/यूए अनुपालन को मान्य करें।

#### प्रश्न: पीडीएफ दस्तावेज़ हेरफेर के लिए मैं .NET के लिए Aspose.PDF की अन्य कौन सी विशेषताओं का पता लगा सकता हूँ?

उ: .NET के लिए Aspose.PDF पीडीएफ दस्तावेज़ हेरफेर के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें टेक्स्ट निष्कर्षण, छवि प्रविष्टि, फॉर्म फ़ील्ड प्रबंधन, डिजिटल हस्ताक्षर और बहुत कुछ शामिल है। अतिरिक्त कार्यक्षमताओं के बारे में जानने के लिए आधिकारिक दस्तावेज़ीकरण और संसाधनों का अन्वेषण करें।
