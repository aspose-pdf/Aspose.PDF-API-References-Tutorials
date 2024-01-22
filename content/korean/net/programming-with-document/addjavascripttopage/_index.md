---
title: PDF 파일에 Java 스크립트 추가
linktitle: 자바 스크립트 PDF 파일 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 JavaScript를 추가하는 방법을 알아보세요. 문서 및 페이지 수준 스크립팅을 위한 코드 튜토리얼이 포함된 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document/addjavascripttopage/
---
PDF 파일에 JavaScript를 추가하려면 .NET용 Aspose.PDF를 사용하겠습니다. 이 라이브러리는 .NET 애플리케이션에서 PDF 파일을 작업하는 간단하고 효율적인 방법을 제공합니다. 다음 단계는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 JavaScript를 추가하는 과정을 안내합니다.

## 1단계: PDF 파일 로드

 첫 번째 단계는 JavaScript를 추가하려는 PDF 파일을 로드하는 것입니다. 다음을 사용하여 이 작업을 수행할 수 있습니다.`Document` .NET용 Aspose.PDF에서 제공하는 클래스입니다. 그만큼`Document` 클래스는 PDF 파일을 로드, 저장 및 조작하는 방법을 제공합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 기존 PDF 파일 로드
Document doc = new Document(dataDir + "input.pdf");
```

## 2단계: 문서 수준에서 JavaScript 추가

문서 수준에서 JavaScript를 추가하려면 다음을 사용합니다.`JavascriptAction` .NET용 Aspose.PDF에서 제공하는 클래스입니다. 이 클래스를 사용하면 PDF 파일에 추가하려는 JavaScript 문을 지정할 수 있습니다.

```csharp
// 문서 수준에서 JavaScript 추가
// 원하는 JavaScript 문으로 JavascriptAction을 인스턴스화합니다.
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// 문서의 원하는 작업에 JavascriptAction 객체 할당
doc.OpenAction = javaScript;
```

이 튜토리얼에서는 문서가 열릴 때 지정된 옵션으로 PDF 파일을 인쇄하는 JavaScript 문을 추가합니다.

## 3단계: 페이지 수준에서 JavaScript 추가

 페이지 수준에서 JavaScript를 추가하려면 다음을 사용합니다.`JavascriptAction` 수업과`Actions` .NET용 Aspose.PDF에서 제공하는 속성입니다. 이 속성을 사용하면 페이지를 열거나 닫을 때 실행될 JavaScript 문을 지정할 수 있습니다.

```csharp
// 페이지 수준에서 JavaScript 추가
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

이 튜토리얼에서는 페이지가 열리거나 닫힐 때 경고 메시지를 표시하는 JavaScript 문을 추가합니다.

## 4단계: PDF 파일 저장

PDF 파일에 JavaScript를 추가한 후 수정된 파일을 저장해야 합니다. 다음을 사용하여 이 작업을 수행할 수 있습니다.`Save` 에서 제공하는 방법`Document` 수업.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

이 코드는 수정된 PDF 파일을 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 페이지에 Java 스크립트 추가에 대한 예제 소스 코드

```csharp
            
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 기존 PDF 파일 로드
Document doc = new Document(dataDir + "input.pdf");

// 문서 수준에서 JavaScript 추가
// 설명된 JavaScript 문으로 JavascriptAction을 인스턴스화합니다.
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// 문서의 원하는 작업에 JavascriptAction 객체 할당
doc.OpenAction = javaScript;

// 페이지 수준에서 JavaScript 추가
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## 결론

이 기사에서는 Aspose.PDF for .NET을 사용하여 문서 수준과 페이지 수준 모두에서 PDF 파일에 JavaScript를 추가하는 방법을 설명했습니다. 우리는 단계별 지침을 제공하고 각 예제에 대한 전체 소스 코드를 포함했습니다. 이러한 지식을 바탕으로 PDF 파일에 JavaScript를 추가하고 필요에 따라 해당 동작을 사용자 정의할 수 있습니다.


### PDF 파일에 Java 스크립트 추가에 대한 FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 파일로 작업할 수 있게 해주는 강력한 라이브러리입니다. PDF 문서 생성, 수정 및 조작을 위한 광범위한 기능을 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 JavaScript를 추가할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 PDF 파일의 문서 수준과 페이지 수준 모두에 JavaScript를 추가하여 동적 및 대화형 PDF 문서를 만들 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 기존 PDF 파일을 어떻게 로드합니까?

 A: 다음을 사용하여 기존 PDF 파일을 로드할 수 있습니다.`Document` 단계별 가이드에 표시된 대로 클래스와 해당 메서드를 살펴보세요.

#### Q: PDF 문서에 어떤 유형의 JavaScript 작업을 추가할 수 있습니까?

A: .NET용 Aspose.PDF를 사용하면 인쇄, 경고 메시지, 양식 필드 조작 등과 같은 다양한 JavaScript 작업을 추가할 수 있습니다.

#### Q: Aspose.PDF for .NET은 상업용 프로젝트에 적합합니까?

A: 예, .NET용 Aspose.PDF는 PDF 조작 및 생성 작업을 위한 상업용 프로젝트에서 일반적으로 사용되는 안정적이고 강력한 라이브러리입니다.

