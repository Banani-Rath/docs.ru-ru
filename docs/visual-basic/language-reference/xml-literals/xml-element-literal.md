---
title: "Литеральное представление XML-элемента (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralElement"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "литералы XML-элементов [Visual Basic]"
  - "литералы элементов [Visual Basic]"
  - "XML-литералы [Visual Basic], элемент"
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Литеральное представление XML-элемента (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Литерал, представляющий <xref:System.Xml.Linq.XElement> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Части  
  
-   `<`  
  
     Обязательный. Открывает начальный тег элемента.  
  
-   `name`  
  
     Обязательный. Имя элемента. Формат является одним из следующих:  
  
    -   Литеральный текст для имени элемента формы [`ePrefix``:`]`eName`, где:  
  
        |||  
        |-|-|  
        |Отделение|Описание|  
        |`ePrefix`|Необязательный. Префикс пространства имен XML для элемента. Должно быть глобальное пространство имен XML, который определен с `Imports` инструкции в файл или на уровне проекта или локальным пространством имен XML, который определен в этом элементе или родительском элементе.|  
        |`eName`|Обязательный. Имя элемента. Формат является одним из следующих:<br /><br /> -Текста. В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Встроенного выражения формы `<%=` e`NameExp` `%>`. Тип `eNameExp` должно быть `String` или типа, который неявно преобразуется в <xref:System.Xml.Linq.XName>.|  
  
    -   Встроенные выражения в форме `<%=` `nameExp` `%>`. Тип `nameExp` должно быть `String` или неявно преобразовываться в тип <xref:System.Xml.Linq.XName>. Внедренное выражение не допускается в закрывающий тег элемента.  
  
-   `attributeList`  
  
     Необязательный. Список атрибутов, объявленных в литерале.  
  
     `attribute [ attribute ... ]`  
  
     Каждый `attribute` имеет один из следующих вариантов синтаксиса:  
  
    -   Назначение формы атрибутов [`aPrefix``:`]`aName``=``aValue`, где:  
  
        |||  
        |-|-|  
        |Отделение|Описание|  
        |`aPrefix`|Необязательный. Префикс пространства имен XML для атрибута. Должно быть глобальное пространство имен XML, который определен с `Imports` инструкции или локальным пространством имен XML, который определен в этом элементе или родительском элементе.|  
        |`aName`|Обязательный. Имя атрибута. Формат является одним из следующих:<br /><br /> -Текста. В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Встроенного выражения формы `<%=` `aNameExp` `%>`. Тип `aNameExp` должно быть `String` или типа, который неявно преобразуется в <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Необязательный. Значение атрибута. Формат является одним из следующих:<br /><br /> -Литеральный текст, заключенный в кавычки.<br />-Встроенного выражения формы `<%=` `aValueExp` `%>`. Допустим любой тип.|  
  
    -   Встроенные выражения в форме `<%=` `aExp` `%>`.  
  
-   `/>`  
  
     Необязательный. Указывает, что элемент является пустым элементом без содержимого.  
  
-   `>`  
  
     Обязательный. Завершает начальный или пустым тегом элемента.  
  
-   `elementContents`  
  
     Необязательный. Содержимое элемента.  
  
     `content [ content ... ]`  
  
     Каждая `content` может принимать одно из следующих действий:  
  
    -   Обычный текст. Все пробелы в `elementContents` становится значимыми, если любой текст.  
  
    -   Встроенные выражения в форме `<%=` `contentExp` `%>`.  
  
    -   XML-элемент литерала.  
  
    -   XML-литерал комментария. В разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Литерал инструкции обработки XML. В разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   Литеральное представление CDATA XML. В разделе [XML CDATA-литерал](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</`[`name`]`>`  
  
     Необязательно. Представляет закрывающий тег для элемента. Необязательный `name` параметра недопустимо, если он является результатом встроенного выражения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  <xref:System.Xml.Linq.XElement> объекта.  
  
## <a name="remarks"></a>Примечания  
 Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement> объекты в коде.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 Встроенные выражения формы `<%=` `exp` `%>` позволяют добавлять динамические данные литерала XML-элемента. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литералы XML-элементов в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктор и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералы с элементами одного пространства имен много раз в коде. Можно использовать глобальные префиксы пространства имен XML, которые можно определить с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:``xmlPrefix`= «`xmlNamespace`» синтаксис атрибута. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 В соответствии с правилами обзора данных для пространства имен XML локальные префиксы имеют приоритет над глобальные префиксы. Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражений, отображаемых во внедренном выражении. Вложенное выражение можно получить доступ к только глобального пространства имен XML.  
  
  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует каждый глобального пространства имен XML, используется XML-литерал в одно определение Локальное пространство имен в созданном коде. Глобальные пространства имен XML, которые не используются в созданном коде не отображаются.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание простой XML-элемент, который имеет два вложенных пустых элемента.  
  
 [!CODE [VbXMLSamples#20](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#20)]  
  
 В примере отображается следующий текст. Обратите внимание, что литерал сохраняет структуру пустых элементов.  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать внедренные выражения для имени элементу и создания атрибутов.  
  
 [!CODE [VbXMLSamples#21](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#21)]  
  
 Этот пример кода отображает следующий текст:  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и отображается конечная форма элемента.  
  
 [!CODE [VbXMLSamples#22](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#22)]  
  
 Этот пример кода отображает следующий текст:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Обратите внимание, что компилятор преобразовал префикс глобального пространства имен XML в определение префикса для пространства имен XML. Элемент \< ns:middle > переопределяет префикс пространства имен XML для элемента \< ns:inner1 >. Тем не менее, элемент \< ns:inner2 > использует пространство имен, определенное путем `Imports` инструкции.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>   
 [Имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [Литерал XML-раздела CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)