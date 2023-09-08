---
title: Удалить гиперссылки после преобразования из HTML
linktitle: Удалить гиперссылки после преобразования из HTML
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по удалению гиперссылок после преобразования HTML в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 250
url: /ru/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
В этом руководстве мы покажем вам процесс удаления гиперссылок из файла PDF, созданного из файла HTML с помощью Aspose.PDF для .NET. Гиперссылки — это интерактивные ссылки, которые могут перенаправлять на другие страницы или веб-сайты. Выполнив следующие действия, вы сможете удалить гиперссылки из полученного PDF-файла.

## Предварительные условия
Прежде чем начать, убедитесь, что вы соответствуете следующим предварительным условиям:

- Базовые знания языка программирования C#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Загрузка HTML-файла и удаление гиперссылок.
На этом этапе мы загрузим HTML-файл и удалим гиперссылки из полученного PDF-документа. Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите файл HTML, используя параметры загрузки HTML.
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Просмотрите аннотации на первой странице документа.
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Проверьте, является ли аннотация ссылкой
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Проверьте, имеет ли действие тип GoToURIAction.
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Используйте поглотитель текстовых фрагментов, чтобы найти совпадающие текстовые фрагменты.
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Перебирать совпадающие фрагменты текста и удалять атрибуты из гиперссылок.
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Удалить аннотацию со страницы
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш HTML-файл.

## Шаг 2. Сохранение полученного PDF-файла.
Наконец, мы сохраним полученный PDF-файл без гиперссылок. Используйте следующий код:

```csharp
// Сохраните полученный PDF-файл.
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Приведенный выше код сохраняет полученный PDF-файл с именем файла.`"RemoveHyperlinksFromText_out.pdf"`.

### Пример исходного кода для удаления гиперссылок после преобразования из Html с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Заключение
В этом уроке мы рассмотрели пошаговый процесс удаления гиперссылок из файла PDF, созданного из файла HTML с помощью Aspose.PDF для .NET. Следуя инструкциям, описанным выше, вы сможете успешно удалить гиперссылки из полученного PDF-файла.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.PDF для .NET?

О: Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам работать с PDF-документами в приложениях C#. Он предлагает широкий спектр функций, включая возможность конвертировать HTML-файлы в PDF и манипулировать PDF-содержимым.

#### Вопрос: Зачем мне удалять гиперссылки из PDF-файла?

О: Существуют различные причины удаления гиперссылок из PDF-файла. Например, вы можете захотеть исключить внешние ссылки для целей печати или архивирования или обеспечить невозможность навигации по содержимому PDF с помощью гиперссылок.

#### Вопрос: Как загрузить HTML-файл и удалить гиперссылки с помощью Aspose.PDF для .NET?

 О: Чтобы загрузить файл HTML и удалить гиперссылки, вы можете использовать Aspose.PDF для .NET.`HtmlLoadOptions` сорт. Просмотрите аннотации страниц PDF, чтобы найти аннотации ссылок и изменить их атрибуты.

#### Вопрос: Могу ли я настроить имя выходного файла для полученного PDF-файла?

О: Да, вы можете настроить имя выходного файла полученного PDF-файла, изменив код, сохраняющий PDF-документ. Просто измените желаемое имя файла в`doc.Save()` метод.

#### Вопрос: Можно ли выборочно удалять гиперссылки по определенным критериям?

О: Да, вы можете выборочно удалять гиперссылки на основе определенных критериев. Например, вы можете удалить только внешние ссылки или ссылки, указывающие на определенные URL-адреса.