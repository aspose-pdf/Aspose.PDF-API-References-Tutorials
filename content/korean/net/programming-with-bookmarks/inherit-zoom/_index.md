---
title: PDF 파일 확대 상속
linktitle: PDF 파일 확대 상속
second_title: .NET API 참조용 Aspose.PDF
description: Aspose.PDF for .NET을 사용하면 PDF 파일에서 북마크 확대/축소를 쉽게 상속받을 수 있습니다.
type: docs
weight: 90
url: /ko/net/programming-with-bookmarks/inherit-zoom/
---
PDF 파일의 확대/축소 상속을 통해 책갈피의 기본 확대/축소 수준을 지정할 수 있습니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 확대/축소를 쉽게 상속할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 확대/축소를 상속하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이제 다음 코드를 사용하여 확대/축소를 상속하려는 PDF 문서를 열겠습니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4단계: 북마크 컬렉션 가져오기

 이 단계에서는 다음을 사용하여 문서의 북마크 또는 랜드마크 컬렉션을 가져옵니다.`Outlines` 의 재산`doc` 물체. 해당 코드는 다음과 같습니다.

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 5단계: 확대/축소 수준 설정

 이제 확대/축소 수준을 설정하겠습니다.`XYZExplicitDestination` 지정된 x, y 및 z 좌표를 가진 객체입니다. 여기서는 확대/축소 2로 좌표(100, 100, 0)를 사용합니다. 해당 코드는 다음과 같습니다.

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 6단계: 북마크에 확대/축소 수준 추가

 이 단계에서는`XYZExplicitDestination` 개체의 북마크에 대한 작업으로 개체`item` 수집. 해당 코드는 다음과 같습니다.

```csharp
item. Action = new GoToAction(dest);
```

## 7단계: 문서에 업데이트된 북마크 추가

 마지막으로 업데이트된 북마크를 다음을 사용하여 문서의 북마크 컬렉션에 추가합니다.`Add` 의 방법`doc.Outlines` 물체. 해당 코드는 다음과 같습니다.

```csharp
doc. Outlines. Add(item);
```

## 8단계: 업데이트된 파일 저장

 이제 다음을 사용하여 업데이트된 PDF 파일을 저장해 보겠습니다.`Save` 의 방법`doc` 물체. 해당 코드는 다음과 같습니다.

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 Inherit Zoom의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document doc = new Document(dataDir + "input.pdf");
// PDF 파일의 개요/북마크 컬렉션 가져오기
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// 확대/축소 수준을 0으로 설정
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// PDF의 개요 컬렉션에 XYZExplicitDestination을 작업으로 추가
item.Action = new GoToAction(dest);
// PDF 파일의 개요 컬렉션에 항목 추가
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// 출력 저장
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 Zoom 상속에 대한 단계별 가이드가 제공됩니다. 이 코드를 사용하여 PDF 문서의 책갈피에 대한 기본 확대/축소 수준을 지정할 수 있습니다.

고급 북마크 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### PDF 파일의 확대/축소 상속에 대한 FAQ

#### Q: PDF 파일의 확대/축소 상속이란 무엇입니까?

A: 확대/축소 상속이란 PDF 문서의 책갈피에 대한 기본 확대/축소 수준을 지정하는 기능을 의미합니다. 이를 통해 사용자가 책갈피와 상호 작용할 때 일관되고 사용자 친화적인 탐색이 가능합니다.

#### Q: 북마크의 확대/축소 수준을 상속하려는 이유는 무엇입니까?

A: 확대/축소 수준을 상속하면 사용자가 PDF 문서의 책갈피를 탐색할 때 일관된 보기 환경을 누릴 수 있습니다. 문서의 여러 섹션에 대한 특정 보기를 제공하려는 경우 특히 유용할 수 있습니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 포함하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

이러한 지시어를 사용하면 PDF 문서 및 책갈피 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.

#### Q: 문서 폴더의 경로를 어떻게 지정합니까?

 A: 제공된 소스 코드에서`"YOUR DOCUMENT DIRECTORY"` 확대/축소 수준을 상속하려는 PDF 파일이 포함된 폴더의 실제 경로를 사용합니다.

#### Q: 확대/축소 수준을 상속하기 위해 PDF 문서를 어떻게 열 수 있나요?

A: 확대/축소 수준을 상속하기 위해 PDF 문서를 열려면 다음 코드를 사용하십시오.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 바꾸다`"input.pdf"` 실제 파일 이름으로.

#### Q: 북마크의 확대/축소 수준을 어떻게 설정합니까?

 A: 확대/축소 수준을 설정하려면`XYZExplicitDestination` 원하는 좌표와 확대/축소 비율을 사용하여 개체를 만듭니다. 예는 다음과 같습니다.

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

그러면 좌표(100, 100)에서 확대/축소 수준이 2로 설정됩니다.

#### Q: 북마크에 확대/축소 수준을 어떻게 추가하나요?

 답:`XYZExplicitDestination` 북마크 컬렉션에 대한 작업으로 개체:

```csharp
item.Action = new GoToAction(dest);
```

 어디`item` 이다`OutlineItemCollection` 북마크를 나타냅니다.

#### Q: 업데이트된 PDF 파일을 어떻게 저장합니까?

 A: 다음을 사용하여 업데이트된 PDF 파일을 저장합니다.`Save` 의 방법`doc` 물체:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Q: 다양한 북마크에 대한 확대/축소 수준을 맞춤 설정할 수 있나요?

 A: 예, 여러 북마크를 생성하여 다양한 북마크에 대한 확대/축소 수준을 사용자 정의할 수 있습니다.`XYZExplicitDestination` 좌표와 확대/축소 비율이 다른 개체.

#### Q: 확대/축소 상속을 적용할 수 있는 북마크 수에 제한이 있나요?

A: 일반적으로 확대/축소 상속을 적용할 수 있는 북마크 수에는 엄격한 제한이 없습니다. 그러나 북마크 수가 너무 많은 매우 큰 문서의 경우 효율적인 메모리 관리가 필요할 수 있습니다.

#### Q: 확대/축소 상속이 적용되었는지 어떻게 확인할 수 있나요?

A: 생성된 PDF 파일을 열어 지정된 확대/축소 수준이 책갈피에 상속되었는지 확인하세요.