---
title: Bloco de texto oculto em arquivo PDF
linktitle: Bloco de texto oculto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como criar blocos de texto ocultos em arquivos PDF usando Aspose.PDF for .NET.
type: docs
weight: 230
url: /pt/net/programming-with-text/hidden-text-block/
---
Neste tutorial, explicaremos como criar um bloco de texto oculto em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. Um bloco de texto oculto é um texto flutuante que se torna visível quando o cursor do mouse passa sobre uma área específica. Seguiremos o processo passo a passo de criação do bloco de texto oculto usando o código-fonte C# fornecido.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação C#.

## Etapa 1: configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde deseja salvar o arquivo PDF gerado. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir`variável com o caminho para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento de amostra

Nesta etapa, criamos um documento PDF de amostra e adicionamos um fragmento de texto a ele. O fragmento de texto servirá como gatilho para exibir o bloco de texto oculto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Etapa 3: abra o documento

 Agora, abrimos o documento criado anteriormente usando o`Document` aula.

```csharp
Document document = new Document(outputFile);
```

## Etapa 4: Encontre o fragmento de texto

 Usamos um`TextFragmentAbsorber` objeto para encontrar o fragmento de texto que acionará a exibição do bloco de texto oculto. Neste caso, estamos procurando o texto exato “Mova o cursor do mouse aqui para exibir o texto flutuante”.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Etapa 5: crie o campo de texto oculto

 Nós criamos um`TextBoxField` objeto para representar o campo de texto oculto. Este campo conterá o texto que se torna visível quando o cursor do mouse passa sobre o texto do gatilho.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Etapa 6: adicione o campo de texto oculto ao documento

Adicionamos o campo de texto oculto à coleção de formulários do documento.

```csharp
document.Form.Add(floatingField);
```

## Etapa 7: crie o botão invisível

Criamos um campo de botão invisível que será posicionado no topo do fragmento de texto do gatilho. Este campo de botão terá ações associadas aos eventos de entrada e saída do mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Etapa 8: salve o documento

Finalmente, salvamos o documento modificado com o bloco de texto oculto.

```csharp
document. Save(outputFile);
```

### Exemplo de código-fonte para bloco de texto oculto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Crie um documento de amostra com texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Abrir documento com texto
Document document = new Document(outputFile);
// Crie o objeto TextAbsorber para encontrar todas as frases que correspondem à expressão regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Aceite o absorvedor para as páginas do documento
document.Pages.Accept(absorber);
// Obtenha o primeiro fragmento de texto extraído
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Crie um campo de texto oculto para texto flutuante no retângulo especificado da página
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Defina o texto a ser exibido como valor do campo
floatingField.Value = "This is the \"floating text field\".";
// Recomendamos tornar o campo 'somente leitura' para este cenário
floatingField.ReadOnly = true;
// Defina o sinalizador 'oculto' para tornar o campo invisível na abertura do documento
floatingField.Flags |= AnnotationFlags.Hidden;
// Definir um nome de campo exclusivo não é necessário, mas é permitido
floatingField.PartialName = "FloatingField_1";
// Definir as características da aparência do campo não é necessário, mas torna-o melhor
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Adicionar campo de texto ao documento
document.Form.Add(floatingField);
// Crie um botão invisível na posição do fragmento de texto
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Crie uma nova ação de ocultação para o campo especificado (anotação) e sinalizador de invisibilidade.
//(Você também pode referir-se ao campo flutuante pelo nome, se o tiver especificado acima.)
// Adicione ações ao entrar/sair do mouse no campo do botão invisível
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Adicionar campo de botão ao documento
document.Form.Add(buttonField);
// Salvar documento
document.Save(outputFile);
```

## Conclusão

Neste tutorial, você aprendeu como criar um bloco de texto oculto usando a biblioteca Aspose.PDF for .NET. Seguindo o guia passo a passo, você pode gerar um documento PDF com um campo de texto oculto que fica visível quando o cursor do mouse passa sobre uma área específica. Você pode personalizar a aparência e o comportamento do bloco de texto oculto de acordo com suas necessidades.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Bloco de texto oculto em arquivo PDF"?

R: O tutorial "Bloco de texto oculto em arquivo PDF" explica como criar um bloco de texto oculto em um arquivo PDF usando a biblioteca Aspose.PDF para .NET. Um bloco de texto oculto é um texto flutuante que se torna visível quando o cursor do mouse passa sobre uma área específica. Este tutorial fornece um guia passo a passo usando código-fonte C#.

#### P: Por que eu desejaria criar um bloco de texto oculto em um arquivo PDF?

R: A criação de um bloco de texto oculto pode ser útil para documentos PDF interativos onde você deseja fornecer informações ou contexto adicionais que só se tornam visíveis quando um usuário passa o cursor do mouse sobre uma área designada.

#### P: Como configuro o diretório de documentos?

R: Para configurar o diretório de documentos:

1.  Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório onde deseja salvar o arquivo PDF gerado.

#### P: Como posso criar um documento de amostra e adicionar um fragmento de texto a ele?

R: No tutorial, você usa o`Document` class para criar um documento PDF de amostra e adicionar um fragmento de texto. Este fragmento de texto serve como gatilho para exibir o bloco de texto oculto.

#### P: Como encontro o fragmento de texto que aciona o bloco de texto oculto?

 R: O tutorial demonstra como usar um`TextFragmentAbsorber` objeto para localizar o fragmento de texto que aciona a exibição do bloco de texto oculto. Ele procura uma sequência de texto específica no documento PDF.

#### P: Como posso criar e personalizar o campo de texto oculto?

 R: Você cria um`TextBoxField` objeto para representar o campo de texto oculto. O tutorial fornece código para definir várias propriedades, como posição, valor, aparência e comportamento do campo de texto oculto.

#### P: Como posso criar um botão invisível associado ao bloco de texto oculto?

 R: Um campo de botão invisível é criado usando o`ButtonField` aula. Este campo de botão está posicionado no topo do fragmento de texto do gatilho e possui ações associadas aos eventos de entrada e saída do mouse. Estas ações controlam a visibilidade do bloco de texto oculto.

#### P: Posso personalizar a aparência do bloco de texto oculto e da área de acionamento?

R: Sim, você pode personalizar várias propriedades do campo de texto oculto e do botão invisível, incluindo fonte, cor, tamanho e posicionamento.

#### P: Como salvo o documento modificado com o bloco de texto oculto?

 R: O tutorial demonstra como salvar o documento modificado usando o`Save` método do`Document` aula.