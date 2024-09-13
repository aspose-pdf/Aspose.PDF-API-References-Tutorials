---
title: Mudar Orientação
linktitle: Mudar Orientação
second_title: Referência da API do Aspose.PDF para .NET
description: Guia passo a passo para alterar a orientação da página de um PDF com Aspose.PDF para .NET. Fácil de seguir e implementar em seus projetos.
type: docs
weight: 10
url: /pt/net/programming-with-pdf-pages/change-orientation/
---
## Introdução

Você já se viu lutando com um arquivo PDF em que a orientação da página está simplesmente... errada? Talvez você esteja lidando com um documento que foi digitalizado ou criado incorretamente, e as páginas precisam ser giradas para fazer sentido. Para nossa sorte, o Aspose.PDF para .NET fornece uma maneira fácil e poderosa de manipular arquivos PDF de praticamente qualquer maneira imaginável — incluindo alterar a orientação de suas páginas. Quer você queira alternar de retrato para paisagem ou vice-versa, este guia o guiará pelo processo passo a passo.

Então, se você estiver pronto para começar e girar essas páginas de PDF com facilidade, vamos começar!

## Pré-requisitos

Antes de entrarmos nos detalhes da alteração da orientação da página no seu PDF, vamos abordar rapidamente o que você precisa ter em mãos:

-  Aspose.PDF para .NET: Certifique-se de ter instalado a biblioteca Aspose.PDF para .NET. Se não tiver, você pode[baixe aqui](https://releases.aspose.com/pdf/net/).
- Um ambiente de desenvolvimento .NET: você pode usar o Visual Studio, o JetBrains Rider ou qualquer IDE preferido para trabalhar com o .NET.
- Conhecimento básico de C#: embora este guia seja simples, algum conhecimento básico de C# o tornará ainda mais fácil de seguir.
- Um arquivo PDF: O exemplo abaixo pressupõe que você tenha um arquivo PDF com várias páginas. Se você não tiver um à mão, crie ou baixe um PDF de amostra para trabalhar.

 Além disso, se você está apenas começando, você pode tentar Aspose.PDF com um[licença temporária gratuita](https://purchase.aspose.com/temporary-license/) antes de decidir[compre a versão completa](https://purchase.aspose.com/buy).

## Importar namespaces

Antes de poder manipular a orientação das páginas no seu PDF, você precisará importar os namespaces necessários no seu projeto C#. Certifique-se de ter o seguinte:

```csharp
using System.IO;
using Aspose.Pdf;
```

Com isso importado, vamos pular para a parte principal do tutorial.

## Etapa 1: Carregue o documento PDF

 A primeira coisa que precisamos fazer é carregar o arquivo PDF que você deseja modificar. Você pode usar o`Document` classe do namespace Aspose.PDF para abrir seu PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Esta linha carrega o PDF do diretório especificado. Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o seu arquivo. O`"input.pdf"` é o PDF cuja orientação você deseja alterar.

## Etapa 2: faça um loop em cada página

 Agora que temos o documento carregado, vamos percorrer cada página do PDF. Usaremos um`foreach` loop para percorrer todas as páginas, permitindo-nos aplicar a mudança de orientação a todas elas.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipule cada página
}
```

Este loop percorrerá todas as páginas do documento.

## Etapa 3: Obtenha o MediaBox da página

 Cada página em um PDF tem um`MediaBox` que define os limites da página. Precisamos acessar isso para determinar a orientação atual e modificá-la.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 O`MediaBox` nos dá as dimensões da página, como largura, altura e posicionamento.

## Etapa 4: troque a largura e a altura

Para alterar a orientação da página de retrato para paisagem ou de paisagem para retrato, simplesmente trocamos os valores de largura e altura. Esta etapa ajustará as dimensões da página.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Este código troca a altura e a largura e reposiciona o canto inferior esquerdo (`LLY`) para que o conteúdo se ajuste perfeitamente após a rotação.

## Etapa 5: atualize o MediaBox e o CropBox

Agora que temos a nova altura e largura, vamos aplicar as alterações à página`MediaBox` e`CropBox` . O`CropBox` é essencial se o documento original tiver um conjunto, garantindo que toda a página seja exibida corretamente.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Esta etapa redimensiona a página com base nas novas dimensões que acabamos de calcular.

## Etapa 6: Gire a página

Por fim, definimos o ângulo de rotação da página. O Aspose.PDF torna isso super simples. Podemos girar a página 90 graus para mudar de retrato para paisagem ou vice-versa.

```csharp
page.Rotate = Rotation.on90;
```

Este código gira a página em 90 graus, invertendo-a para a orientação desejada.

## Etapa 7: Salve o PDF de saída

Depois de aplicar as alterações de orientação a todas as páginas, salvamos o documento modificado em um novo arquivo. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Certifique-se de fornecer um novo nome de arquivo (neste caso,`ChangeOrientation_out.pdf`) para salvar a saída. Dessa forma, você não sobrescreve seu arquivo original.

### Conclusão

aí está! Alterar a orientação da página de um arquivo PDF usando o Aspose.PDF para .NET é tão simples quanto carregar o documento, percorrer as páginas, ajustar o MediaBox e salvar o arquivo atualizado. Quer você esteja lidando com um documento mal digitalizado ou precise girar páginas para corresponder às suas necessidades de formatação, este guia passo a passo deve ajudar.

## Perguntas frequentes

### Posso girar páginas específicas em vez de todas as páginas do PDF?  
Sim, você pode modificar o loop para atingir páginas específicas usando seu índice em vez de percorrer todas as páginas.

###  O que é o`MediaBox`?  
 O`MediaBox` define o tamanho e a forma da página em um arquivo PDF. É onde o conteúdo da página é colocado.

### O Aspose.PDF para .NET funciona com outros formatos de arquivo?  
Sim, o Aspose.PDF pode lidar com uma variedade de formatos de arquivo como HTML, XML, XPS e muito mais.

### Existe uma versão gratuita do Aspose.PDF para .NET?  
 Sim, você pode começar com um[teste gratuito](https://releases.aspose.com/) ou solicite um[licença temporária](https://purchase.aspose.com/temporary-license/).

### Posso desfazer as alterações depois de salvá-las?  
Depois que você salvar o documento, as alterações serão permanentes. Certifique-se de trabalhar em uma cópia ou manter um backup do arquivo original.