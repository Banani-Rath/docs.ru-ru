---
title: "Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "as - оператор [C#]"
  - "операторы приведения [C#], операторы as и is"
  - "оператор is [C#]"
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Поскольку объекты являются полиморфными, в переменной типа базового класса может храниться производный тип.  Для доступа к методу производного типа необходимо выполнить приведение значения обратно в производный тип.  Однако попытка выполнения простого приведения в этих случаях создает риск возникновения <xref:System.InvalidCastException>.  Вот почему в С\# предоставлены операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md).  Эти операторы можно использовать, чтобы проверить, будет ли приведение успешным, не вызывая исключение.  В общем оператор `as` более эффективен, поскольку он фактически возвращает значение приведения, если приведение может быть выполнено успешно.  Оператор `is` возвращает только логическое значение.  Поэтому его можно использовать, если необходимо определить тип объекта, но нет необходимости выполнить его фактическое приведение.  
  
## Пример  
 В следующем примере показано использование операторов `is` и `as` для выполнения приведения от одного ссылочного типа к другому, не вызывая исключение.  Также в примере показано использование оператора `as` с нулевыми типами значений.  
  
 [!CODE [csProgGuideTypes#40](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#40)]  
  
## См. также  
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)