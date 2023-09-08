---
title: Нарисовать XForm на странице
linktitle: Нарисовать XForm на странице
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по рисованию формы XForm на странице PDF с использованием Aspose.PDF для .NET. Добавьте и разместите форму на странице.
type: docs
weight: 10
url: /ru/net/programming-with-operators/draw-xform-on-page/
---
В этом уроке мы предоставим вам пошаговое руководство о том, как нарисовать XForm на странице с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, манипулировать и конвертировать PDF-документы. Используя операторы, предоставляемые Aspose.PDF, вы можете добавить и разместить форму XForm на существующей странице PDF.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET Framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете скачать библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен.

В файл кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Шаг 3. Установка путей к файлам

Определите пути к файлам фонового изображения, входного PDF-файла и выходного PDF-файла:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Обязательно укажите фактические пути к файлам на вашем компьютере.

## Шаг 4. Загрузка входного PDF-файла

Используйте следующий код для загрузки входного PDF-файла:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// В следующем коде используются операторы GSave/GResstore.
// В коде используется оператор ContatenateMatrix для позиционирования XForm.
// В коде используется оператор Do для рисования XForm на странице.
// Операторы GSave/GResstore оборачивают существующий контент
// это сделано для получения исходного состояния графики в конце существующего контента.
// в противном случае в конце цепочки существующих операторов могут остаться нежелательные преобразования.
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Добавьте оператор GSave для правильного сброса состояния графики после новых команд.
pageContents. Add(new GSave());

// Создайте X-форму
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Установите ширину и высоту изображения
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Загрузите изображение в поток
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Добавьте изображение в коллекцию изображений ресурсов XForm.
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Использование оператора Do: этот оператор рисует изображение
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Расположите XForm по координатам x=100 и y=500.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Расположите XForm по координатам x=100 и y=300.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Нарисуйте XForm с помощью оператора Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Восстановите состояние графики с помощью GRestore после GSave.
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Обязательно укажите фактические пути к файлам и при необходимости измените номер страницы и положение XForm.

### Пример исходного кода для Draw XForm On Page с использованием Aspose.PDF для .NET
 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Образец демонстрирует
	// Использование операторов GSave/GResstore
	// Использование оператора ContatenateMatrix для позиционирования xForm
	// Использование оператора для рисования xForm на странице
	// Оберните существующее содержимое парой операторов GSave/GResstore.
	// это для получения исходного состояния графики существующего содержимого
	// в противном случае в конце существующей цепочки операторов могут остаться нежелательные преобразования.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Добавлен оператор сохранения состояния графики, чтобы правильно очищать состояние графики после новых команд.
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Создать xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Определите ширину и высоту изображения
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Загрузить изображение в поток
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Добавить изображение в коллекцию изображений ресурсов XForm.
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Использование оператора Do: этот оператор рисует изображение.
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=500.
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Нарисовать форму с помощью оператора Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Поместите форму в координаты x=100 y=300.
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Нарисовать форму с помощью оператора Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Восстановите состояние графики с помощью GRestore после GSave.
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Заключение

В этом уроке вы узнали, как нарисовать форму XForm на странице PDF с помощью Aspose.PDF для .NET. Выполнив описанные шаги, вы сможете добавить и разместить форму XForm на существующей странице, тем самым придав большую гибкость вашим PDF-документам.

### Часто задаваемые вопросы по рисованию XForm на странице

#### Вопрос: Что такое XForm в Aspose.PDF?

О: XForm — это многократно используемый графический объект в документе PDF. Он позволяет определять и рисовать сложную графику, изображения или текст, которые можно многократно использовать на разных страницах.

#### Вопрос: Как мне импортировать необходимые пространства имен для Aspose.PDF?

 О: В файле кода C# используйте`using` директива для импорта необходимых пространств имен для доступа к классам и методам, предоставляемым Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Вопрос: Какова цель операторов GSave и GRestore?

 А:`GSave` и`GRestore`операторы в Aspose.PDF используются для сохранения и восстановления состояния графики. Они помогают гарантировать, что преобразования и настройки, примененные к одному разделу контента, не влияют на последующие разделы.

#### Вопрос: Как определить XForm с помощью Aspose.PDF?

 О: Чтобы создать XForm, используйте команду`XForm.CreateNewForm` метод и добавьте его в`Resources.Forms` коллекция конкретной страницы. Затем вы можете добавить контент в XForm.`Contents` свойство.

#### Вопрос: Как нарисовать изображение в XForm?

 О: Загрузите изображение в поток и добавьте его в`Resources.Images` коллекция XForm. Использовать`Do` оператор в XForm`Contents` нарисовать изображение.

#### Вопрос: Как разместить XForm на странице PDF?

 О: Чтобы разместить XForm на странице, используйте`ConcatenateMatrix` оператор на странице`Contents`. Настройте параметры матрицы, чтобы указать перевод (положение) и масштабирование XForm.

#### Вопрос: Могу ли я нарисовать несколько XForms на одной странице?

 О: Да, вы можете нарисовать несколько XForms на одной странице, настроив`ConcatenateMatrix`параметры для размещения каждой XForm в разных координатах.

#### Вопрос: Могу ли я изменить содержимое XForm после его создания?

 О: Да, вы можете изменить содержимое XForm после создания, добавив в него дополнительные операторы.`Contents` свойство.

#### Вопрос: Что произойдет, если я опущу операторы GSave и GRestore?

О: Отсутствие операторов GSave и GRestore может привести к нежелательным преобразованиям или настройкам, которые будут применены к последующему содержимому. Их использование помогает поддерживать чистое состояние графики.

#### Вопрос: Могу ли я повторно использовать XForms на разных страницах PDF-документа?

 О: Да, вы можете повторно использовать XForm на нескольких страницах, добавив одну и ту же XForm в`Resources.Forms` коллекция разных страниц.

#### Вопрос: Существует ли ограничение на количество XForms, которые я могу создать?

О: Хотя не существует строгого ограничения на количество создаваемых вами XForms, имейте в виду, что слишком большое количество XForms может повлиять на производительность и использование памяти. Используйте их разумно.

#### Вопрос: Могу ли я повернуть XForm или применить другие преобразования?

 О: Да, вы можете использовать`ConcatenateMatrix`оператор для применения таких преобразований, как вращение, масштабирование и перевод, к XForm.
