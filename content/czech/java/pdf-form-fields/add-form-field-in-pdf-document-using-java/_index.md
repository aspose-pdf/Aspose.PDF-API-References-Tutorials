---
title: Přidejte pole formuláře do dokumentu PDF pomocí Java
linktitle: Přidejte pole formuláře do dokumentu PDF pomocí Java
second_title: Aspose.PDF Java PDF Processing API
description: Naučte se, jak přidat interaktivní pole formuláře do dokumentů PDF pomocí Java a Aspose.PDF for Java. Snadno vytvářejte uživatelsky přívětivé formuláře PDF.
type: docs
weight: 10
url: /cs/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## Zavedení

Přidání polí formuláře do dokumentu PDF vylepšuje jeho funkčnost tím, že uživatelům umožňuje vkládat data přímo do dokumentu. To může být neuvěřitelně užitečné pro různé účely, jako je vytváření vyplnitelných formulářů, průzkumů nebo zpráv s obsahem vytvářeným uživateli.

Budeme používat Aspose.PDF for Java, výkonnou knihovnu, která zjednodušuje manipulaci s PDF v aplikacích Java. S Aspose.PDF můžete snadno vytvářet, upravovat a manipulovat s dokumenty PDF, včetně dynamického přidávání polí formulářů.

## Nastavení prostředí

Než se vrhneme na kód, musíte nastavit vývojové prostředí. Postupujte takto:

1.  Stáhnout Aspose.PDF pro Java: Navštivte web Aspose a stáhněte si nejnovější verzi Aspose.PDF pro Java. Můžete to najít[zde](https://releases.aspose.com/pdf/java/).

2. Instalace Aspose.PDF: Po stažení nainstalujte Aspose.PDF podle pokynů k instalaci uvedených na webu.

3. Vytvoření projektu Java: Vytvořte nový projekt Java ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a zahrňte do svého projektu knihovnu Aspose.PDF.

## Vytvoření nového dokumentu PDF

Začněme vytvořením nového dokumentu PDF. V tomto příkladu vytvoříme jednoduchý soubor PDF s názvem a několika pokyny.

```java
// Importujte knihovnu Aspose.PDF
import com.aspose.pdf.*;

public class AddFormFieldPDF {
    public static void main(String[] args) {
        // Vytvořte nový dokument PDF
        Document doc = new Document();

        // Přidejte do dokumentu stránku
        Page page = doc.getPages().add();

        // Přidejte nadpis
        TextFragment title = new TextFragment("Feedback Form");
        title.getTextState().setFontSize(18);
        title.getTextState().setFont(FontRepository.findFont("Arial"));
        page.getParagraphs().add(title);

        // Přidejte pokyny
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // Uložte dokument do souboru
        doc.save("FeedbackForm.pdf");
    }
}
```

tomto úryvku kódu vytvoříme nový dokument PDF, přidáme stránku a vložíme nadpis a nějaké pokyny.

## Přidání polí formuláře

Nyní přejdeme k přidávání polí formuláře do našeho dokumentu PDF. Zahrneme textová pole, zaškrtávací políčka a přepínače pro vytvoření interaktivního formuláře zpětné vazby.

### Textová pole

Textová pole umožňují uživatelům vkládat text. Zde je návod, jak přidat textové pole:

```java
// Vytvořte textové pole
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // Nastavit styl ohraničení
textField.setPartialName("txtName"); // Nastavit název pole
textField.setMultiline(false); // Zakázat víceřádkový
page.getAnnotations().add(textField);
```

### Zaškrtávací políčka

Zaškrtávací políčka se používají pro binární opce (např. otázky ano/ne). Zde je návod, jak přidat zaškrtávací políčko:

```java
// Vytvořte zaškrtávací políčko
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // Nastavit název pole
checkboxField.setChecked(false); // Zpočátku nezaškrtnuté
page.getAnnotations().add(checkboxField);
```

### Přepínače

Přepínače se používají, když uživatelé potřebují vybrat jednu možnost ze skupiny. Každá možnost je samostatný přepínač, ale patří do stejné skupiny. Zde je návod, jak přidat přepínače:

```java
// Vytvořte přepínače
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // Nastavte název pole pro volbu 1
option2.setPartialName("optNo"); // Nastavte název pole pro volbu 2

//Přidejte možnosti do skupiny přepínačů
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

Pomocí těchto příkladů kódu můžete do dokumentu PDF přidat textová pole, zaškrtávací políčka a přepínače. Nezapomeňte upravit jejich vlastnosti podle potřeby, jako jsou názvy polí a výchozí hodnoty.

## Přizpůsobení polí formuláře

Přizpůsobení polí formuláře vám umožňuje řídit jejich vzhled a chování. Můžete změnit vlastnosti, jako je velikost písma, barva textu, styl ohraničení a další.

### Změna vlastností pole

Řekněme, že chcete změnit velikost písma a barvu textu textového pole:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### Ověření v terénu

Můžete také nastavit ověřovací pravidla pro pole formuláře. Můžete například požadovat, aby uživatelé zadali platnou e-mailovou adresu do textového pole:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## Nastavení hodnot polí

Chcete-li pole formuláře předem vyplnit daty, můžete programově nastavit jejich výchozí hodnoty. To je užitečné pro vytváření šablon nebo předvyplnění známých informací.

```java
textField.setValue("John Doe"); // Nastavit výchozí hodnotu pro textové pole
checkboxField.setChecked(true); // Ve výchozím nastavení zaškrtněte políčko
```

## Odeslání a ověření formuláře

Přidání polí formuláře je jen polovina příběhu; budete chtít také

 umožňující odeslání a ověření formuláře.

### Odeslání formuláře

Chcete-li uživatelům umožnit odesílat data formuláře, musíte zadat akci, jako je odeslání e-mailu nebo odeslání na webový server. Zde je příklad, jak nastavit tlačítko pro odeslání:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit", SubmitFormActionType.URL, "FeedbackForm.pdf"));
page.getAnnotations().add(submitButton);
```

### Ověření formuláře

Ověření zajišťuje, že vstup uživatele splňuje specifická kritéria. Můžete například ověřit pole pro telefonní číslo, aby přijímalo pouze čísla:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## Ukládání a export

Jakmile vytvoříte a přizpůsobíte dokument PDF pomocí polí formuláře, je čas jej uložit nebo exportovat. Aspose.PDF k tomu poskytuje různé možnosti.

### Uložit do místního souboru

Chcete-li uložit dokument PDF do místního souboru, použijte následující kód:

```java
doc.save("FeedbackForm.pdf");
```

### Uložit do streamu

 Chcete-li uložit dokument PDF do streamu, můžete použít`OutputStream` třída:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## Závěr

tomto komplexním průvodci jsme prozkoumali, jak přidat pole formuláře do dokumentu PDF pomocí Java a Aspose.PDF for Java. Naučili jste se vytvářet textová pole, zaškrtávací políčka a přepínače, upravovat jejich vlastnosti, nastavovat výchozí hodnoty, povolit odesílání a ověřování formulářů a ukládat/exportovat dokument PDF.

## Nejčastější dotazy

### Jak mohu nastavit rozevírací seznam ve formátu PDF?

 Chcete-li vytvořit rozevírací seznam (rozbalovací seznam) ve formuláři PDF, můžete použít`ComboBoxField` třídy poskytované Aspose.PDF pro Javu. Postupujte podobným způsobem, jaký je zobrazen pro ostatní pole formuláře, a přizpůsobte možnosti pomocí`AddItem` metoda. Podrobnou dokumentaci k tomu najdete na webu Aspose.

### Je Aspose.PDF for Java kompatibilní s jinými knihovnami a frameworky Java?

Ano, Aspose.PDF for Java je kompatibilní s různými Java knihovnami a frameworky. Můžete jej integrovat do svých aplikací Java, ať už používáte Spring, JavaFX nebo jiné populární frameworky. Nezapomeňte zkontrolovat dokumentaci a zdroje pro konkrétní pokyny pro integraci.

### Mohu chránit heslem formulář PDF vytvořený pomocí Aspose.PDF for Java?

Absolutně! Aspose.PDF for Java vám umožňuje přidat ochranu heslem k vašim dokumentům PDF, včetně formulářů. Pro omezení přístupu a oprávnění můžete nastavit hesla na úrovni uživatele i vlastníka. Podrobné pokyny k implementaci této funkce zabezpečení naleznete v dokumentaci.

### Jak mohu extrahovat data odeslaná prostřednictvím formuláře PDF?

Chcete-li extrahovat data odeslaná prostřednictvím formuláře PDF, budete muset zpracovat odeslání formuláře na vašem serveru nebo backendu aplikace. Když uživatel odešle formulář, můžete obdržet data a zpracovat je podle potřeby. Aspose.PDF poskytuje nástroje pro extrahování dat formuláře programově z dokumentu PDF na straně serveru.

### Mohu dynamicky generovat formuláře PDF na základě vstupu uživatele?

Ano, pomocí Aspose.PDF for Java můžete dynamicky generovat formuláře PDF na základě vstupu uživatele. V závislosti na uživatelském vstupu nebo aplikační logice můžete vytvářet dokumenty PDF s různými poli formuláře a rozvržením. Tato flexibilita umožňuje vytvářet přizpůsobené formuláře přizpůsobené konkrétním potřebám nebo scénářům uživatelů.