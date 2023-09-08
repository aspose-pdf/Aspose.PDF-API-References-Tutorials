---
title: Элементы встроенной структуры
linktitle: Элементы встроенной структуры
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по использованию онлайн-структурных элементов с Aspose.PDF для .NET. Организуйте свои PDF-файлы с помощью заголовков и абзацев.
type: docs
weight: 110
url: /ru/net/programming-with-tagged-pdf/inline-structure-elements/
---
В этом пошаговом руководстве мы покажем вам, как использовать элементы встроенной структуры с Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно манипулировать PDF-документами. Элементы встроенной структуры позволяют создать иерархическую структуру в PDF-документе, используя заголовки разных уровней и абзацы.

Давайте углубимся в код и узнаем, как использовать элементы встроенной структуры в Aspose.PDF для .NET.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1. Настройка среды

Для начала откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили ссылку на библиотеку Aspose.PDF для .NET в свой проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

 Первым шагом является создание нового PDF-документа с помощью`Document` сорт.

```csharp
// Создайте PDF-документ
Document document = new Document();
```

## Шаг 3. Работайте с тегированным контентом

Затем мы получаем размеченное содержимое документа для работы.

```csharp
// Получить тегированное содержимое документа
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4. Установите название и язык документа.

Теперь мы можем установить заголовок и язык документа.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5. Добавьте структурные элементы онлайн.

Теперь мы добавим в наш документ элементы встроенной структуры, такие как заголовки разных уровней и абзацы.

```csharp
// Получить элемент корневой структуры
StructureElement rootElement = taggedContent.RootElement;

// Добавляйте заголовки разных уровней
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Добавьте контент в каждый заголовок
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Добавить абзац
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Добавьте контент в абзац
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Здесь мы создаем элементы встроенной структуры, такие как заголовки разных уровней и абзац, и добавляем к ним контент.

## Шаг 6. Сохраните PDF-документ с тегами.

Наконец, мы сохраняем PDF-документ с тегами.

```csharp
// Сохраните PDF-документ с тегами
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Пример исходного кода для элементов встроенной структуры с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать PDF-документ
Document document = new Document();

// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Установите заголовок и язык для Documentnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Сохранить PDF-документ с тегами
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Заключение

Поздравляем! Вы узнали, как использовать элементы встроенной структуры в Aspose.PDF для .NET. Теперь вы можете создать иерархическую структуру в своем PDF-документе, используя заголовки разных уровней и абзацев. Изучите дополнительные возможности Aspose.PDF, чтобы раскрыть весь его потенциал.

### Часто задаваемые вопросы

#### Вопрос: Что такое элементы встроенной структуры в PDF-документе и как они способствуют созданию иерархической структуры?

Ответ: Элементы встроенной структуры в PDF-документе, такие как заголовки разных уровней и абзацы, используются для создания иерархической структуры, которая организует и представляет контент в структурированном виде. Эти элементы позволяют установить четкую иерархию и поток информации внутри документа.

#### Вопрос: Как элементы встроенной структуры могут улучшить читаемость и организацию PDF-документа?

Ответ: Элементы встроенной структуры, особенно заголовки и абзацы, помогают улучшить читаемость и организацию PDF-документа, обеспечивая логическую структуру. Заголовки указывают на разные уровни важности и помогают читателям ориентироваться в контенте, а абзацы группируют связанную информацию вместе.

#### Вопрос: Как Aspose.PDF для .NET упрощает использование элементов встроенной структуры?

О: Aspose.PDF для .NET предлагает классы и методы для создания и управления элементами встроенной структуры, такими как заголовки и абзацы. Эти элементы можно настраивать, организовывать иерархически и дополнять контентом для улучшения визуального представления и доступности документа.

####  Вопрос: Какова цель`taggedContent` object in relation to inline structure elements?

 А:`taggedContent` объект, полученный из`TaggedContent` собственность`Document`, позволяет работать со структурированными элементами, включая элементы встроенной структуры. Он позволяет создавать, настраивать и упорядочивать заголовки и абзацы в документе.

#### Вопрос: Как элементы встроенной структуры помогают создать четкую иерархию документов?

Ответ: Элементы встроенной структуры, такие как заголовки разных уровней, способствуют созданию четкой и четко определенной иерархии в документе. Читатели могут быстро определить основные темы, подтемы и связанное с ними содержимое, что упрощает навигацию и понимание документа.

#### Вопрос: Могу ли я настроить внешний вид и форматирование элементов встроенной структуры с помощью Aspose.PDF для .NET?

О: Да, вы можете настроить внешний вид и форматирование элементов встроенной структуры. Вы можете установить такие свойства, как стили шрифта, размеры, цвета, выравнивание, отступы и интервалы, чтобы добиться желаемого визуального представления заголовков и абзацев.

#### Вопрос: Как создать и добавить в PDF-документ заголовки разных уровней, используя встроенные элементы структуры в Aspose.PDF для .NET?

 О: Вы можете создавать заголовки разного уровня, используя`CreateHeaderElement` метод, а затем добавить их к корневому элементу структуры. Впоследствии вы можете добавить контент к каждому элементу заголовка, используя`CreateSpanElement` метод для создания фрагментов текста.

#### Вопрос: Могу ли я использовать элементы встроенной структуры для создания списков, маркеров или других типов организации контента в документе PDF?

О: Хотя сами элементы встроенной структуры в основном используются для заголовков и абзацев, вы можете использовать их в сочетании с другими функциями, предлагаемыми Aspose.PDF для .NET, для создания списков, маркированных пунктов, таблиц и других типов организации контента для комплексной организации контента. структура документа.

#### Вопрос: Как элементы встроенной структуры способствуют доступности документа?

Ответ: Элементы встроенной структуры играют решающую роль в повышении доступности документа. Правильно структурированные заголовки и абзацы обеспечивают четкую иерархию документов, которая помогает программам чтения с экрана и другим вспомогательным технологиям точно интерпретировать и передавать контент пользователям с ограниченными возможностями.

#### Вопрос: Могу ли я изучить более сложные способы использования элементов встроенной структуры, например создание интерактивных элементов или встраивание мультимедиа?

А: Абсолютно! Хотя это руководство посвящено созданию заголовков и абзацев, Aspose.PDF для .NET предлагает расширенные функции для создания интерактивных элементов, встраивания мультимедиа, добавления гиперссылок и многого другого. Ознакомьтесь с документацией и примерами библиотеки, чтобы углубиться в эти расширенные возможности.