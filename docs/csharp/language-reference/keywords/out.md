---
title: "out (Справочник по C#) | Microsoft Docs"
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
  - "out_CSharpKeyword"
  - "out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out [C#]"
  - "out - ключевое слово [C#]"
ms.assetid: 7e911a0c-3f98-4536-87be-d539b7536ca8
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# out (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Контекстно\-зависимое ключевое слово `out` можно использовать в двух контекстах \(каждый представляет собой ссылку на подробные сведения\) — как [модификатор параметра](../../../csharp/language-reference/keywords/out-parameter-modifier.md) или в [объявлениях параметра универсального типа](../../../csharp/language-reference/keywords/out-generic-modifier.md) в интерфейсах и делегатах.  В этом разделе содержатся сведения о модификаторе параметра, однако сведения об объявлениях параметра универсального типа см. в [в этом разделе](../../../csharp/language-reference/keywords/out-generic-modifier.md).  
  
 Ключевое `out` инициирует передачу аргументов по ссылке.  Оно схоже с ключевым словом [ref](../../../csharp/language-reference/keywords/ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.  Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.  Например:  
  
 [!CODE [csrefKeywordsMethodParams#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#1)]  
  
 Несмотря на то, что переменные, передаваемые как аргументы `out`, не нужно инициализировать перед передачей, для назначения значения требуется вызываемый метод.  
  
 Несмотря на то, что ключевые слова `ref` и `out` вызвать другое поведение среды выполнения, они не считаются частью подписи метода во время компиляции.  Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref`, а другой — аргумент `out`.  Следующий код, например, компилироваться не будет.  
  
 [!CODE [csrefKeywordsMethodParams#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#2)]  
  
 Перегрузка возможна, если один метод принимает аргумент `ref` или `out`, а другой не использует ни одного из них, как показано далее.  
  
 [!CODE [csrefKeywordsMethodParams#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#3)]  
  
 Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.  
  
 Сведения об передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.  
  
-   Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Методы итератора, которые включают инструкцию [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  
  
## Пример  
 Объявление метода `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений.  В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.  Обратите внимание, что третьему аргумент присвоено значение null.  Это позволяет методам возвращать значения по желанию.  
  
 [!CODE [csrefKeywordsMethodParams#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#4)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)