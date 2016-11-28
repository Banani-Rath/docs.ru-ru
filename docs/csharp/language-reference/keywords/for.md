---
title: "for (Справочник по C#) | Microsoft Docs"
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
  - "for"
  - "for_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "for - ключевое слово [C#]"
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
caps.handback.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# for (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

С помощью цикла `for` можно выполнять оператор или блока выписок повторно до тех пор, пока указанное выражение не будет оценки к `false`.  Этот тип цикла полезен для перебора массивами и для других приложений, в которых известны заранее, сколько раз необходимо цикл повторных.  
  
## Пример  
 В следующем примере значение `i` записывано на консоль и увеличивается на 1 при каждой итерации цикла.  
  
 [!CODE [csrefKeywordsIteration#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsIteration#2)]  
  
 Оператор `for` в предыдущем примере выполняет следующие действия.  
  
1.  Во\-первых, начальное значение переменной `i` установлена.  Данный шаг возникает только один раз независимо от того, сколько раз цикл повторит.  Можно представить себе как вне этой инициализации случаясь циклической процесс.  
  
2.  Для оценки условия \(`i <= 5`\), значение `i` сравнитьо до 5.  
  
    -   Если `i` меньше или равно 5, то условие принимает значение `true` и выполняются следующие действия.  
  
        1.  Оператор `Console.WriteLine` в теле цикла отображается значение `i`.  
  
        2.  Значение `i` увеличивается на 1.  
  
        3.  Цикл возвращается к началу раздела 2 для оценки условия.  
  
    -   Если `i` превышает 5, то условие принимает значение `false` и выйдете цикл.  
  
 Обратите внимание, что, если начальное значение `i` превышает 5, то тело цикла не выполняется, даже один раз.  
  
 Каждый оператор `for` определяет инициализатор, критерий и разделы итератора.  В этих разделах обычно указывают, сколько раз цикл выполняется итерация.  
  
```c#  
for (initializer; condition; iterator)  
    body  
```  
  
 Разделы используются следующие функции.  
  
-   Раздел инициализатора устанавливает начальные условия.  Выписки в этом распределяют выполнить только один раз, прежде чем вводе цикл.  Раздел может содержать только один из следующих параметров 2.  
  
    -   Показано объявление и инициализации переменной локального очага перетаскивания, как первый пример \(`int i = 1`\).  Переменная является локальной в цикл и не может быть получен доступ вне цикла.  
  
    -   Ноль или более expressons выписки из следующего списка, разделенные запятыми.  
  
        -   Оператор [назначение](../../../csharp/language-reference/operators/assignment-operator.md)  
  
        -   вызов метода  
  
        -   присоедините префикс или postfix выражение [increment](../../../csharp/language-reference/operators/increment-operator.md), как `++i` или `i++`  
  
        -   присоедините префикс или postfix выражение [уменьшение](../../../csharp/language-reference/operators/decrement-operator.md), как `--i` или `i--`  
  
        -   создание объекта с помощью [новый](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   выражение [подождите](../../../csharp/language-reference/keywords/await.md)  
  
-   Раздел условия содержит логическое выражение, вычисляемое для определения того, должен ли цикл оставить или должен выполнить попытку.  
  
-   Раздел итератора определяет, что происходит после каждой итерации тела цикла.  Раздел итератора, содержащая ноль или более следующих выражений выписки, разделенных запятыми.  
  
    -   Оператор [назначение](../../../csharp/language-reference/operators/assignment-operator.md)  
  
    -   вызов метода  
  
    -   присоедините префикс или postfix выражение [increment](../../../csharp/language-reference/operators/increment-operator.md), как `++i` или `i++`  
  
    -   присоедините префикс или postfix выражение [уменьшение](../../../csharp/language-reference/operators/decrement-operator.md), как `--i` или `i--`  
  
    -   создание объекта с помощью [новый](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   выражение [подождите](../../../csharp/language-reference/keywords/await.md)  
  
-   Тело цикла состоит из выписки пустая оператор или блок выписок, которые создании, заключив ноль или более выписок в фигурных скобках.  
  
     Можно прервать из цикла `for` с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или можно осуществлять переход к следующей итерации с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md).  Также можно оставить любой цикл с помощью [go](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или выписки [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 Первый пример в этом разделе показывает типичный цикл `for` самый тип, который выполняет следующие варианты для секций.  
  
-   Инициализатор объявляет и инициализирует переменную локального очага перетаскивания, `i`, которая поддерживает количество итерации цикла.  
  
-   Проверяет условия значение переменной цикла для известного окончательного значения 5.  
  
-   Шаг приращения выписку итератора использует постфиксная, `i++`, чтобы tally каждой итерации цикла.  
  
 Следующий пример иллюстрирует несколько менее общих вариантов: присвоение значения внешней переменной цикла в разделе инициализатора, то вызов метода `Console.WriteLine` как в инициализаторе, так и в разделах итератора, и изменить значения переменных в разделе 2 итератора.  
  
 [!CODE [csrefKeywordsIteration#8](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsIteration#8)]  
  
 Все выражения, определяющие выписку `for` являются необязательными.  Например, следующий оператор создается бесконечный цикл.  
  
 [!CODE [csrefKeywordsIteration#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsIteration#3)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Оператор for \(C\+\+\)](/visual-cpp/cpp/for-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)