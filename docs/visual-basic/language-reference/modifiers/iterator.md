---
title: "Итератор (Visual Basic) | Microsoft Docs"
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
  - "vb.Iterator"
helpviewer_keywords: 
  - "Iterator - ключевое слово [Visual Basic]"
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Итератор (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что функция или метод доступа `Get` итератор.  
  
## Заметки  
 *Итератор* выполняет пользовательскую итерацию по коллекции.  Итератор выписку [yield](../../../visual-basic/language-reference/statements/yield-statement.md) используется для возвращения каждый элемент в коллекции одной записи за раз.  Оператор `Yield` при достижении текущего расположения в коде сохраняется.  Выполнение будет перезапущено из этого местоположения при следующем вызове функции итератора.  
  
 Итератор можно реализовать как функции или в качестве метода доступа `Get` определения свойства.  Модификатор `Iterator` отображается в объявление функции итератора или метода доступа `Get`.  
  
 Итератор можно вызывать из кода клиента с помощью [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Возвращаемый тип функции итератора или метода доступа `Get` может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Итератор не может содержать любые параметры `ByRef`.  
  
 Итератор не может произойти в событии конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Итератор может быть анонимной функции.  Дополнительные сведения см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Дополнительные сведения об итераторах см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Использование  
 Модификатор `Iterator` можно использовать в следующих контекстах:  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Пример  
 Следующий пример демонстрирует функцию итератора.  Функция итератора имеет выписку `Yield`, которая находится внутри цикла [For… next](../../../visual-basic/language-reference/statements/for-next-statement.md).  Каждая итерация тела выписки [Оператор For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в `Main` создает вызов функции итератора `Power`.  Каждый вызов функции итератора переход к следующему выполнению выписки `Yield`, которая происходит во время следующей итерации цикла `For…Next`.  
  
 [!CODE [VbVbalrStatements#98](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#98)]  
  
## Пример  
 В следующем примере показан метод доступа `Get`, итератор.  Модификатор `Iterator` в объявлении свойства.  
  
 [!CODE [VbVbalrStatements#99](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#99)]  
  
 Дополнительные примеры см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## См. также  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>   
 [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md)