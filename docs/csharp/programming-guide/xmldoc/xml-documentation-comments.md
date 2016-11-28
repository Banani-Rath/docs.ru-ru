---
title: "Комментарии к XML-документации (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.xml"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, комментарии к XML-коду"
  - "файлы исходного кода C#"
  - "комментарии [C#], XML"
  - "комментарии к документации [C#]"
  - "XML [C#], комментарии к коду"
  - "комментарии к документации по XML [C#]"
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Комментарии к XML-документации (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В Visual C\# можно создавать документацию для кода путем включения XML\-элементов в специальные поля комментариев \(начинающиеся с трех символов косой черты\) в исходном коде непосредственно перед блоком кода, к которому относятся комментарии. Например:  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 При выполнении компиляции с параметром [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) компилятор осуществляет поиск всех тегов XML в исходном коде и создает XML\-файл документации.  Для получения окончательной документации на основе созданного компилятором файла можно создать пользовательский инструмент или использовать инструмент [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061).  
  
 Для ссылки на XML\-элементы \(например, если функция обрабатывает определенные XML\-элементы, которые требуется включить в комментарии XML\-документации\) можно использовать стандартный механизм заключения в скобки \(`<` и `>`\).  Для ссылки на универсальные идентификаторы в элементах ссылок кода \(`cref`\) можно использовать escape\-символы \(например, `cref="List<T>"`\) или фигурные скобки \(`cref="List{T}"`\).  В особом случае компилятор анализирует фигурные скобки, как угловые, чтобы при ссылке на универсальные идентификаторы сделать комментарий документации менее громоздким.  
  
> [!NOTE]
>  Комментарии XML\-документации не являются метаданными. Они не включаются в скомпилированную сборку, и поэтому не доступны посредством отражения.  
  
## Содержание  
  
-   [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Обработка XML\-файла](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Разделители для тегов документации](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Практическое руководство. Использование XML\-документации](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## Связанные разделы  
 Дополнительные сведения см. в следующем разделе:  
  
-   [\/doc \(обработка комментариев документации\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)