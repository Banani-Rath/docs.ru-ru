---
title: "Небезопасный код и указатели (Руководство по программированию в C#) | Microsoft Docs"
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
  - "безопасность [C#], безопасность типов"
  - "язык C#, небезопасный код"
  - "строгая типизация [C#]"
  - "unsafe - ключевое слово [C#]"
  - "небезопасный код [C#]"
  - "язык C#, указатели"
  - "указатели [C#], сведения об указателях"
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Небезопасный код и указатели (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для обеспечения строгой типизации и безопасности C\# по умолчанию не поддерживает арифметические операции над указателями.  Однако с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) можно определить небезопасный контекст для использования указателей.  Дополнительные сведения об указателях см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  В среде CLR небезопасный код называют непроверяемым.  Небезопасный код в C\# не обязательно представляет опасность. Это просто код, безопасность которого не может быть проверена средой CLR.  Поэтому CLR выполнит этот код, только если он находится в полностью надежной сборке.  При использовании небезопасного кода необходимо обеспечить гарантию того, что он не создаст угрозу безопасности и не вызовет ошибки указателей.  
  
## Общие сведения о небезопасном коде  
 Небезопасный код имеет следующие свойства.  
  
-   Методы, типы и блоки кода могут определяться как небезопасные.  
  
-   В некоторых случаях небезопасный код может повысить производительность приложения за счет удаления проверок границ массива.  
  
-   Использование небезопасного кода рекомендуется при вызове встроенных функций, требующих указателей.  
  
-   Использование небезопасного кода создает угрозу безопасности и стабильной работы.  
  
-   Для компиляции небезопасного кода в C\# необходимо, чтобы приложение было скомпилировано с помощью [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  
  
## Связанные разделы  
 Дополнительные сведения см. в следующих разделах.  
  
-   [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Практическое руководство. Использование указателей для копирования массива байтов](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)