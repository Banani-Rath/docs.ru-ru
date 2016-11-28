---
title: "Оператор Call (Visual Basic) | Microsoft Docs"
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
  - "vb.Call"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Call - оператор"
  - "процедуры, Call - оператор"
  - "процедуры, вызов"
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Call (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Передает управление в процедуру `Function`, `Sub` или процедуру библиотеки динамической компоновки \(DLL\).  
  
## Синтаксис  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## Части  
 `procedureName`  
 Обязательный.  Имя вызываемой процедуры.  
  
 `argumentList`  
 Необязательный.  Список переменных или выражений, передаваемых вызываемой процедуре.  Несколько аргументов разделяются запятыми.  При включении `argumentList` следует заключить его в скобки.  
  
## Заметки  
 Можно использовать ключевое слово `Call` при вызове процедуры.  Для большинства вызовов процедуры не требуется использовать ключевое слово this.  
  
 Обычно используется ключевое слово `Call` если выражение с именем не начинается с идентификатором.  Не рекомендуется использование ключевого слова `Call` для другого.  
  
 Если процедура возвращает значение, то оператор `Call` отбрасывает его.  
  
## Пример  
 Следующий код демонстрирует 2 примерам ключевого слова where `Call` необходимости для вызова процедуры.  В обоих примерах, выражение не начинается с идентификатором.  
  
 [!CODE [VbVbalrStatements#97](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#97)]  
  
## См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)