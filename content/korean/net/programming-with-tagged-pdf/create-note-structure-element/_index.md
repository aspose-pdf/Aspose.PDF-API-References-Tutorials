---
title: 노트 구조 요소 생성
linktitle: 노트 구조 요소 생성
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 구조화된 메모 항목을 만드는 단계별 가이드입니다.
type: docs
weight: 30
url: /ko/net/programming-with-tagged-pdf/create-note-structure-element/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 노트 구조 요소를 만드는 방법에 대한 단계별 가이드를 제공합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다. Aspose.PDF의 표시된 콘텐츠 구조 기능을 사용하여 PDF 문서에 구조화된 노트를 추가할 수 있습니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET Framework와 함께 설치된 Visual Studio.
2. .NET용 Aspose.PDF 라이브러리.

## 1단계: 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다. Aspose 공식 웹사이트에서 라이브러리를 다운로드하여 컴퓨터에 설치할 수 있습니다.

## 2단계: 필요한 네임스페이스 가져오기

C# 코드 파일에서 Aspose.PDF에서 제공하는 클래스와 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3단계: PDF 문서 만들기 및 구조화된 요소 참고

다음 코드를 사용하여 PDF 문서를 만들고 메모 구조화 요소를 추가하세요.

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

이 코드는 빈 PDF 문서를 만들고 문단에 구조화된 노트 요소를 추가합니다. 각 노트는 Aspose.PDF에서 제공하는 메서드를 사용하여 생성됩니다.

## 4단계: PDF 문서 저장

다음 코드를 사용하여 PDF 문서를 저장하세요.

```csharp
document. Save(outFile);
```

이 코드는 노트 구조 요소가 포함된 PDF 문서를 지정된 파일에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 노트 구조 요소를 만드는 샘플 소스 코드 

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// PDF 문서 생성
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// 문단 요소 추가
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement 추가
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement 추가
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement 추가
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// 예외를 throw해야 함 - Aspose.Pdf.Tagged.TaggedException: ID='note_002'인 구조 요소가 이미 존재합니다.
//note3.SetId("note_002");
// ClearId()가 Note Structure Element에 사용된 경우 결과 문서가 PDF/UA를 준수하지 않습니다.
//note3.ClearId();
// 태그가 지정된 PDF 문서 저장
document.Save(outFile);
// PDF/UA 준수 확인
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 노트 구조 요소를 만드는 방법을 배웠습니다. 구조화된 노트 요소를 사용하면 PDF 문서에 추가적이고 구조화된 정보를 추가할 수 있습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 메모 구조 요소를 만드는 목적은 무엇입니까?

A: Aspose.PDF for .NET을 사용하여 PDF 문서에서 노트 구조 요소를 만들면 문서의 콘텐츠에 구조화된 노트를 추가할 수 있습니다. 이러한 노트는 콘텐츠의 특정 부분에 대한 추가 컨텍스트, 설명 또는 참조를 제공할 수 있습니다.

#### 질문: Aspose.PDF 라이브러리는 PDF 문서에서 메모 구조 요소를 만드는 데 어떻게 도움이 되나요?

A: Aspose.PDF for .NET은 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환하는 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 라이브러리의 표시된 콘텐츠 구조 기능을 사용하여 PDF 문서의 콘텐츠 내에 구조화된 메모 요소를 만듭니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 메모 구조 요소를 만드는 데 필요한 전제 조건은 무엇입니까?

답변: 시작하기 전에 .NET 프레임워크와 함께 Visual Studio가 설치되어 있는지 확인하고 프로젝트에서 .NET용 Aspose.PDF 라이브러리가 참조되었는지 확인하세요.

#### 질문: 제공된 C# 코드는 어떻게 PDF 문서 내용에 메모 구조 요소를 생성하나요?

A: 이 코드는 PDF 문서를 만들고, 노트 구조 요소를 정의하고, 이를 문단에 추가하는 방법을 보여줍니다. 각 노트는 Aspose.PDF에서 제공하는 메서드를 사용하여 생성되므로 구조화된 노트를 콘텐츠에 통합할 수 있습니다.

#### 질문: 내가 만든 노트 구조 요소의 내용과 속성을 사용자 정의할 수 있나요?

A: 네, Aspose.PDF 라이브러리에서 제공하는 메서드와 속성을 사용하여 노트 구조 요소의 내용과 속성을 사용자 정의할 수 있습니다. 이 코드는 노트 요소의 텍스트와 ID를 설정하는 방법을 보여 주지만 필요에 따라 추가로 사용자 정의할 수 있습니다.

#### 질문: 메모 구조 요소와 문서 내용 사이의 계층적 관계는 어떻게 설정됩니까?

 A: 계층적 관계는 문단과 같은 다른 구조화된 요소의 자식으로 노트 구조 요소를 추가하여 설정됩니다. 코드에서 노트 요소는 다음을 사용하여 문단 요소에 추가됩니다.`AppendChild` 방법.

#### 질문: 노트 구조 요소에 고유한 ID를 할당할 수 있나요?

A: 예, 다음을 사용하여 노트 구조 요소에 고유 ID를 할당할 수 있습니다.`SetId` 방법. 이 코드는 노트 요소의 ID를 고유한 값으로 설정하는 방법을 보여줍니다.

#### 질문: 노트 구조 요소에 중복된 ID를 지정하려고 하면 어떻게 되나요?

A: 노트 구조 요소에 중복된 ID를 할당하려고 하면 예외가 발생합니다. 튜토리얼에 제공된 코드에는 이 시나리오를 설명하는 주석이 포함되어 있습니다.

#### 질문: 메모 구조 요소를 만들 때 PDF/UA 규정 준수를 어떻게 보장할 수 있나요?

 A: 튜토리얼에 제공된 코드는 다음을 사용하여 PDF/UA 준수 여부를 확인하는 방법을 보여줍니다.`Validate` 방법. PDF/UA 표준에 대해 문서를 검증하면 추가된 노트 구조 요소가 접근성 지침을 준수하는지 확인할 수 있습니다.

#### 질문: 이 방법을 사용하면 기존 PDF 문서에 메모 구조 요소를 추가할 수 있나요?

A: 네, 제공된 접근 방식을 수정하여 기존 PDF 문서에 노트 구조 요소를 추가할 수 있습니다. 새 문서를 만드는 대신 Aspose.PDF를 사용하여 기존 문서를 로드한 다음 비슷한 단계에 따라 노트 요소를 추가합니다.
