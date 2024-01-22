---
title: टेबल एलिमेंट बनाएं
linktitle: टेबल एलिमेंट बनाएं
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ एक ऐरे तत्व बनाने के लिए चरण दर चरण मार्गदर्शिका। तालिकाओं के साथ आसानी से गतिशील पीडीएफ़ उत्पन्न करें।
type: docs
weight: 80
url: /hi/net/programming-with-tagged-pdf/create-table-element/
---
इस चरण-दर-चरण मार्गदर्शिका में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक सरणी तत्व बनाने की प्रक्रिया के बारे में बताएंगे। Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ों में हेरफेर करने देती है। गतिशील पीडीएफ उत्पन्न करते समय एक सरणी तत्व बनाना एक सामान्य आवश्यकता है, और Aspose.PDF इसे पूरा करने का एक आसान और कुशल तरीका प्रदान करता है।

आइए कोड के बारे में गहराई से जानें और जानें कि .NET के लिए Aspose.PDF का उपयोग करके एक ऐरे तत्व कैसे बनाया जाए।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. .NET के लिए Aspose.PDF लाइब्रेरी स्थापित।
2. C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।

## चरण 1: वातावरण स्थापित करना

आरंभ करने के लिए, अपना C# विकास परिवेश खोलें और एक नया प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET के लिए Aspose.PDF लाइब्रेरी का संदर्भ जोड़ा है।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाना

 पहला कदम इसका उपयोग करके एक नया पीडीएफ दस्तावेज़ बनाना है`Document` कक्षा।

```csharp
// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

यहां हम टैग की गई सामग्री के लिए शीर्षक और भाषा भी निर्धारित करते हैं।

## चरण 3: सरणी तत्व बनाना

इसके बाद, हमें ऐरे एलिमेंट बनाना होगा और उसे दस्तावेज़ में जोड़ना होगा। हम मूल संरचना तत्व प्राप्त करके प्रारंभ करते हैं, फिर हम इसका उपयोग करके एक नया तालिका तत्व बनाते हैं`CreateTableElement` तरीका।

```csharp
// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "CreateTableElement.pdf");

// पीडीएफ/यूए अनुपालन जांच
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### .NET के लिए Aspose.PDF का उपयोग करके तालिका तत्व बनाने के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// जड़ संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "CreateTableElement.pdf");

// पीडीएफ/यूए अनुपालन की जाँच करना
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

आपने सीखा है कि .NET के लिए Aspose.PDF का उपयोग करके एक ऐरे तत्व कैसे बनाया जाता है। अब आप इस पद्धति का उपयोग करके गतिशील तालिकाओं के साथ पीडीएफ दस्तावेज़ तैयार कर सकते हैं। Aspose.PDF की पूरी क्षमता जानने के लिए बेझिझक इसकी और अधिक विशेषताओं का पता लगाएं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ में एक ऐरे तत्व क्या है, और मुझे .NET के लिए Aspose.PDF का उपयोग करके इसे बनाने की आवश्यकता क्यों होगी?

ए: पीडीएफ दस्तावेज़ में एक सरणी तत्व डेटा के संरचित संग्रह का प्रतिनिधित्व करता है, जिसका उपयोग अक्सर टेबल या ग्रिड बनाने के लिए किया जाता है। गतिशील पीडीएफ उत्पन्न करते समय आपको .NET के लिए Aspose.PDF का उपयोग करके एक सरणी तत्व बनाने की आवश्यकता हो सकती है, जिसके लिए सारणीबद्ध जानकारी या ग्रिड जैसे संरचित डेटा प्रस्तुति की आवश्यकता होती है।

#### प्रश्न: .NET के लिए Aspose.PDF एक सरणी तत्व बनाने की प्रक्रिया को कैसे सरल बनाता है?

उत्तर: .NET के लिए Aspose.PDF कक्षाओं और विधियों का एक व्यापक सेट प्रदान करता है जो आपको प्रोग्रामेटिक रूप से PDF दस्तावेज़ में सरणी तत्वों (तालिकाओं) को बनाने, अनुकूलित करने और प्रबंधित करने की अनुमति देता है। यह मैन्युअल पीडीएफ हेरफेर की आवश्यकता को समाप्त करता है और संरचित डेटा प्रतिनिधित्व के निर्माण को सुव्यवस्थित करता है।

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके एक ऐरे तत्व बनाने में शामिल मुख्य चरण क्या हैं?

ए: मुख्य चरणों में पर्यावरण स्थापित करना, दस्तावेज़ बनाना, मूल संरचना तत्व प्राप्त करना, तालिका तत्व बनाना, तालिका के भीतर पंक्तियों और कोशिकाओं को परिभाषित करना और तत्वों के लिए स्वरूपण और गुणों को निर्दिष्ट करना शामिल है। प्रदान किया गया कोड उदाहरण इन चरणों को प्रदर्शित करता है।

####  प्रश्न: क्या भूमिका है`taggedContent` object play in creating an array element?

 ए: द`taggedContent` दस्तावेज़ से प्राप्त वस्तु`TaggedContent`संपत्ति, आपको पीडीएफ दस्तावेज़ के भीतर टैग की गई सामग्री की संरचना को परिभाषित करने की अनुमति देती है। इसमें श्रेणीबद्ध तरीके से सरणी तत्वों और उनके चाइल्ड तत्वों को बनाना और व्यवस्थित करना शामिल है।

#### प्रश्न: कोड निर्मित सरणी तत्व की पहुंच और शब्दार्थ को कैसे सुनिश्चित करता है?

 ए: कोड जैसे गुण सेट करता है`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , और`ColSpan` सरणी तत्व की पहुंच और शब्दार्थ को बढ़ाने के लिए। ये विशेषताएँ डेटा के एक अच्छी तरह से संरचित, सूचनात्मक और दृश्य रूप से आकर्षक प्रतिनिधित्व में योगदान करती हैं।

#### प्रश्न: सरणी तत्व बनाने के संदर्भ में पीडीएफ/यूए अनुपालन का क्या महत्व है?

 उत्तर: पीडीएफ/यूए (यूनिवर्सल एक्सेसिबिलिटी) अनुपालन सुनिश्चित करता है कि जेनरेट किए गए पीडीएफ दस्तावेज़ विकलांग उपयोगकर्ताओं के लिए पहुंच योग्य हैं और कुछ पहुंच मानकों को पूरा करते हैं। कोड उदाहरण का उपयोग करके पीडीएफ/यूए अनुपालन की जांच करता है`Validate` विधि, आपको ऐसे दस्तावेज़ बनाने में मदद करती है जो समावेशी और सुलभ हों।

#### प्रश्न: क्या मैं सरणी तत्वों के स्वरूपण और स्वरूप को और अधिक अनुकूलित कर सकता हूँ?

उत्तर: हां, आप पृष्ठभूमि रंग, सीमा शैली, फ़ॉन्ट आकार और संरेखण जैसी विशेषताओं को समायोजित करके सरणी तत्वों के स्वरूपण और उपस्थिति को अनुकूलित कर सकते हैं। .NET के लिए Aspose.PDF आपकी आवश्यकताओं के अनुरूप दृश्य प्रस्तुति को तैयार करने के लिए गुणों की एक विस्तृत श्रृंखला प्रदान करता है।

#### प्रश्न: मैं अधिक जटिल तालिका संरचनाएं बनाने या बड़े पीडीएफ दस्तावेज़ों में सरणी तत्वों को शामिल करने के लिए इस ज्ञान का विस्तार कैसे कर सकता हूं?

उ: आप .NET के लिए Aspose.PDF की अतिरिक्त सुविधाओं की खोज करके इस ज्ञान को बढ़ा सकते हैं, जैसे कि एकाधिक सरणी तत्वों को मर्ज करना, नेस्टेड टेबल बनाना, हेडर और फ़ुटर जोड़ना, और सरणी तत्वों को बड़े पीडीएफ लेआउट में एकीकृत करना। लाइब्रेरी के दस्तावेज़ीकरण और उदाहरण इन उन्नत परिदृश्यों के लिए मार्गदर्शन प्रदान करते हैं।

#### प्रश्न: क्या सरणी तत्वों को भरने के लिए डेटाबेस या स्प्रेडशीट जैसे बाहरी स्रोतों से डेटा आयात करना संभव है?

उ: हाँ, आप सरणी तत्वों को भरने के लिए बाहरी स्रोतों से डेटा आयात कर सकते हैं। आप डेटाबेस, स्प्रेडशीट या अन्य स्रोतों से डेटा लाने के लिए C# में डेटा पुनर्प्राप्ति और परिवर्तन तकनीकों का उपयोग कर सकते हैं और फिर तदनुसार सरणी तत्वों को पॉप्युलेट कर सकते हैं।

#### प्रश्न: मैं इस ट्यूटोरियल से प्राप्त ज्ञान का उपयोग प्रोग्रामेटिक रूप से बनाए गए पीडीएफ दस्तावेजों की गुणवत्ता और उपयोगिता को बढ़ाने के लिए कैसे कर सकता हूं?

उ: इस ट्यूटोरियल से प्राप्त ज्ञान आपको पीडीएफ दस्तावेज़ों में संरचित और दृश्य रूप से आकर्षक सरणी तत्व (टेबल) बनाने की अनुमति देता है। इन तकनीकों को शामिल करके, आप गतिशील रूप से उत्पन्न पीडीएफ की पठनीयता, पहुंच और उपयोगकर्ता अनुभव में सुधार कर सकते हैं, जिससे वे अधिक जानकारीपूर्ण और उपयोगकर्ता के अनुकूल बन जाएंगे।