---
title: "Практическое руководство. Операторы меток (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - ": - знак разделителя"
  - "двоеточие (:)"
  - "операторы [Visual Basic], подписи"
  - "код Visual Basic, создание меток для операторов"
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Операторы меток (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Блоки операторов состоят из строк кода, ограниченных знаками двоеточий.  Строки кода, в начале которых находится идентификатор или целое число, называются *помеченными*.  Строки кода помечаются для идентификации их при использовании таких операторов, как `On Error Goto`.  
  
 Метки могут содержать любой допустимый Visual Basic идентификатор\-таким как те, которые определяют литералы программирование элемент\-или целого числа.  Метка должна располагаться в начале строки исходного кода. За ней должен следовать знак двоеточия, независимо от того, расположен ли оператор далее в той же строке.  
  
 Компилятор распознает метки, проверяя, соответствует ли начало строки какому\-либо из уже определенных идентификаторов.  Если соответствия не найдено, компилятор считает это меткой.  
  
 Метки имеют свое собственное пространство для объявления и не пересекаются с другими идентификаторами.  Областью видимости метки является тело метода.  В любой неоднозначной ситуации преимущество в порядке применения имеет объявление метки.  
  
> [!NOTE]
>  Метки могут использоваться только для исполняемых инструкций внутри методов.  
  
### Пометка строки кода  
  
-   Следует разместить идентификатор с последующим знаком двоеточия в начале строки исходного кода.  
  
     Например, следующие строки кода помечаются `Jump` и `120`, соответственно:  
  
     [!CODE [VbVbalrStatements#708](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#708)]  
  
## См. также  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)