---
title: PDF 파일에 파일 정보 설정
linktitle: PDF 파일에 파일 정보 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF 파일에 파일 정보를 설정하는 방법을 알아보세요.
type: docs
weight: 310
url: /ko/net/programming-with-document/setfileinfo/
---
Aspose.PDF for .NET을 사용하여 PDF 파일을 관리해야 하는 프로젝트를 진행 중이라면, 활용하고 싶을 수 있는 기능 중 하나는 PDF 문서에 대한 파일 정보를 설정하는 기능입니다. 파일 정보에는 작성자, 생성 날짜, 키워드, 수정 날짜, 주제, 제목과 같은 다양한 세부 정보가 포함됩니다. 이 가이드에서는 Aspose.PDF for .NET과 함께 C# 소스 코드를 사용하여 PDF 문서에 대한 파일 정보를 설정하는 과정을 안내합니다.

## .NET용 Aspose.PDF를 사용하여 파일 정보를 설정하기 위한 단계별 가이드

1. Visual Studio IDE에서 새로운 C# 프로젝트를 만듭니다.
2. 프로젝트에 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.
3. 파일 정보를 수정하려는 PDF 파일의 경로를 제공하여 새 PDF 문서 객체를 만듭니다.

## 1단계: 문서 디렉토리 경로를 설정합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 열기

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## 3단계: DocumentInfo 객체를 사용하여 PDF 문서의 파일 정보에 액세스합니다.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 4단계: DocumentInfo 개체의 속성을 사용하여 원하는 파일 정보 값을 설정합니다.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## 5단계: 업데이트된 PDF 문서를 지정된 위치에 저장합니다.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 6단계: 파일 정보가 성공적으로 업데이트되었는지 확인합니다.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Aspose.PDF for .NET을 사용하여 PDF 문서의 파일 정보를 성공적으로 설정했습니다.

### .NET용 Aspose.PDF를 사용하여 파일 정보 설정에 대한 예제 소스 코드


```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// 문서 정보를 지정하세요
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// 출력 문서 저장
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## 결론

결론적으로, Aspose.PDF for .NET은 PDF 문서에 대한 파일 정보를 설정하는 간단하고 효과적인 방법을 제공합니다. 위에 언급된 단계를 따르면 C# 소스 코드를 사용하여 PDF 문서에 대한 원하는 파일 정보 값을 쉽게 설정할 수 있습니다.

### PDF 파일의 파일 정보 설정에 대한 FAQ

#### 질문: 예시에 언급되지 않은 추가적인 파일 정보 속성을 설정할 수 있나요?

 A: 예, 다음을 사용하여 추가 파일 정보 속성을 설정할 수 있습니다.`DocumentInfo` .NET용 Aspose.PDF의 개체입니다.`DocumentInfo`클래스는 제작자, 버전, 사용자 정의 속성 등의 추가 정보를 설정할 수 있는 다양한 속성을 제공합니다.

#### 질문: 기존 PDF 문서에서 파일 정보를 검색할 수 있나요?

 A: 네, Aspose.PDF for .NET을 사용하여 기존 PDF 문서에서 파일 정보를 검색할 수 있습니다. 이를 위해 다음을 사용할 수 있습니다.`DocumentInfo` 객체는 파일 정보 속성에 접근하여 PDF 문서에 저장된 정보를 읽습니다.

#### 질문: 파일 정보를 설정하면 원본 PDF 문서가 변경되나요?

A: 아니요, Aspose.PDF for .NET을 사용하여 파일 정보를 설정해도 원래 PDF 문서는 수정되지 않습니다. 대신 업데이트된 파일 정보로 새 PDF 문서를 만듭니다. 원래 PDF 문서는 변경되지 않습니다.