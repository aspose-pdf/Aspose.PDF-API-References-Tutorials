---
title: 웹페이지를 PDF로
linktitle: 웹페이지를 PDF로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 웹 페이지를 PDF로 변환하는 단계별 가이드입니다.
type: docs
weight: 320
url: /ko/net/document-conversion/web-page-to-pdf/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 웹 페이지를 PDF로 변환하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다. 이 튜토리얼이 끝나면 웹 페이지를 PDF 문서로 쉽게 변환할 수 있습니다.

## 소개
웹 페이지를 PDF 형식으로 변환하는 것은 많은 응용 프로그램에서 일반적인 요구 사항입니다. 웹 콘텐츠를 PDF로 변환하면 원본 웹 페이지의 레이아웃, 서식, 이미지를 쉽게 보존할 수 있습니다. .NET용 Aspose.PDF는 이러한 변환을 효율적이고 정확하게 수행할 수 있는 강력한 라이브러리입니다.

## 요구사항
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 컴퓨터에 설치된 Visual Studio
- .NET 라이브러리용 Aspose.PDF(공식 Aspose 웹사이트에서 다운로드 가능)
- C# 프로그래밍에 대한 기본 지식


## 1단계: 문서 디렉터리 정의
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 바꾸다`"YOUR DOCUMENT DIRECTORY"` 생성된 PDF 파일을 저장하려는 경로를 사용하세요.

## 2단계: 웹 요청 생성
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
웹 요청 객체를 생성하고 변환하려는 웹 페이지의 URL을 지정하세요. URL을 원하는 웹페이지로 바꿀 수 있습니다.

## 3단계: 웹 응답 받기
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
웹 요청을 보내고 서버에서 응답을 검색합니다.

## 4단계: 웹 콘텐츠 읽기
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 다음을 사용하여 웹페이지의 내용을 읽습니다.`StreamReader`그리고 그것을`responseFromServer` 변하기 쉬운.

## 5단계: HTML을 PDF로 변환
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 만들기`MemoryStream` 웹 페이지 콘텐츠를 로드하는 개체입니다. 그런 다음`HtmlLoadOptions` 웹페이지의 기본 URL을 전달합니다. 다음으로`Document` 로드된 스트림과 HTML 로드 옵션을 사용하는 개체입니다. 설정`IsLandscape` 재산`true` PDF를 가로 방향으로 만들고 싶다면. 마지막으로 PDF 문서를 지정된 디렉터리에 저장합니다.

.

## 6단계: 예외 처리
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
변환 프로세스 중에 발생할 수 있는 예외를 포착하고 오류 메시지를 표시합니다.

### .NET용 Aspose.PDF를 사용하여 웹페이지를 PDF로 변환하는 예제 소스 코드

```csharp
try
{
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// URL에 대한 요청을 만듭니다.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// 서버에서 요구하는 경우 자격 증명을 설정합니다.
	request.Credentials = CredentialCache.DefaultCredentials;
	// 요청 시간이 초과되기 전 시간 초과(밀리초)
	// 요청.시간 초과 = 100;

	// 응답을 받으세요.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// 서버에서 반환한 콘텐츠가 포함된 스트림을 가져옵니다.
	Stream dataStream = response.GetResponseStream();
	// 쉽게 액세스할 수 있도록 StreamReader를 사용하여 스트림을 엽니다.
	StreamReader reader = new StreamReader(dataStream);
	// 내용을 읽어보세요.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// HTML 파일 로드
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// 출력을 PDF 형식으로 저장
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 웹 페이지를 PDF로 변환하는 방법을 배웠습니다. 제공된 C# 소스 코드를 설명하는 단계별 가이드를 살펴보았습니다. 이러한 지침을 따르면 웹 페이지를 PDF로 변환하는 기능을 자신의 .NET 애플리케이션에 쉽게 통합할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서로 작업할 수 있는 강력한 라이브러리입니다. 웹페이지를 PDF로 변환하는 등 다양한 기능을 제공합니다.

#### Q: 웹페이지를 PDF로 변환하려는 이유는 무엇입니까?

A: 웹 페이지를 PDF로 변환하면 원본 웹 콘텐츠의 레이아웃, 서식 및 이미지를 보존하는 데 유용합니다. 이를 통해 오프라인으로 보거나 다른 사람과 공유할 수 있도록 웹 페이지의 스냅샷을 만들 수 있습니다.

#### Q: 이 튜토리얼의 전제 조건은 무엇입니까?

A: 이 튜토리얼을 따르려면 컴퓨터에 Visual Studio가 설치되어 있어야 하고, .NET용 Aspose.PDF 라이브러리가 있어야 하며, C# 프로그래밍에 대한 기본적인 이해가 있어야 합니다.

#### Q: 모든 웹페이지를 PDF로 변환할 수 있나요?

A: 예, 코드에 웹 페이지의 URL을 제공하면 모든 웹 페이지를 PDF로 변환할 수 있습니다. .NET용 Aspose.PDF는 웹 콘텐츠를 검색하여 PDF 형식으로 변환합니다.

#### Q: 페이지 방향 등 PDF 출력을 사용자 정의하려면 어떻게 해야 합니까?

 A: 다음과 같은 옵션을 사용하여 PDF 출력을 사용자 정의할 수 있습니다.`IsLandscape` 페이지 방향을 설정합니다. 제공된 코드에서,`options.PageInfo.IsLandscape = true` 가로 방향으로 PDF를 만드는 데 사용됩니다.