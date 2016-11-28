---
title: "Операторы (Руководство по программированию в C#) | Microsoft Docs"
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
  - "C# - язык, операторы"
  - "операторы [C#], сведения об операторах"
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Операторы (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Действия программы выражаются в операторах.  В общие действия включено объявление переменных, присвоение значений, вызов методов, проход по коллекциям и ветвление на один или другой блок кода, в зависимости от заданного условия.  Порядок выполнения операторов в программе называется потоком управления или потоком выполнения.  Поток управления может отличаться при каждом запуске программы, в зависимости от реакции программы на входные данные, которые она получает во время выполнения.  
  
 Оператор может состоять из одной строки кода, которая заканчивается точкой с запятой, или из ряда однострочных операторов в блоке.  Блок оператора заключен в скобки \({}\) и может содержать вложенные блоки.  В следующем коде показаны два примера однострочных операторов и блок многострочного оператора:  
  
 [!CODE [csProgGuideStatements#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#1)]  
  
## Типы операторов  
 В приведенной ниже таблице перечислены различные типы операторов в C\# и связанные с ними ключевые слова со ссылками на разделы, в которых содержится больше сведений:  
  
|Категория|Ключевые слова \/ примечания C\#|  
|---------------|--------------------------------------|  
|Операторы объявления|Оператор объявления представляет новую переменную или константу.  Объявление переменной может при необходимости присвоить значение переменной.  В объявлении константы необходимо назначение.<br /><br /> [!CODE [csProgGuideStatements#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#23)]|  
|Операторы выражений|Операторы выражений, вычисляющие значение, должны сохранить его в переменной.<br /><br /> [!CODE [csProgGuideStatements#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#24)]|  
|[Операторы выбора](../../../csharp/language-reference/keywords/selection-statements.md)|Операторы выбора позволяют ветвление на разные разделы кода, в зависимости от одного или нескольких заданных условий.  Дополнительные сведения см. в следующих разделах:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)|Операторы итерации позволяют просмотр коллекций как массивов или многократное выполнение того же набора операторов до выполнения заданного условия.  Дополнительные сведения см. в следующих разделах:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)|Операторы перехода осуществляют передачу управления другому разделу кода.  Дополнительные сведения см. в следующих разделах:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Операторы обработки исключений позволяют аккуратно восстановиться после исключительных условий, возникающих во время выполнения.  Дополнительные сведения см. в следующих разделах:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try\-catch](../../../csharp/language-reference/keywords/try-catch.md), [try\-finally](../../../csharp/language-reference/keywords/try-finally.md), [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Операторы checked и unchecked позволяют указать, позволено ли числовым операциям вызывать переполнение, когда результат сохраняется в переменной, которая слишком мала для хранения результирующего значения.  Дополнительные сведения см. в разделах [checked](../../../csharp/language-reference/keywords/checked.md) и [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Оператор `await`.|Если пометить метод с модификатором [async](../../../csharp/language-reference/keywords/async.md), можно использовать оператор [подождите](../../../csharp/language-reference/keywords/await.md) в методе.  Если элемент управления достигает выражение `await` в методе async, передачи вызывающему приложению, а ход выполнения в методе приостанавливается до тех пор, пока подожданная задача не завершится.  Если задача завершена, выполнение может возобновить в методе.<br /><br /> Для простого примера см. раздел "Async" [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md) методов.  Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).|  
|Оператор `yield return`.|Итератор выполняет пользовательскую итерацию по коллекции, например список или массив.  Итератор выписку [получение выходных данных](../../../csharp/language-reference/keywords/yield.md) используется для возвращения поочередно каждый элемент.  Оператор `yield return` при достижении текущего расположения в коде вспомнено.  Выполнение перезагружено из этого расположения, если итератор был вызван при следующем запуске.<br /><br /> Дополнительные сведения см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).|  
|Оператор `fixed`.|Оператор fixed не позволяет сборщику мусора переносить перемещаемую переменную.  Дополнительные сведения см. в разделе [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Оператор `lock`.|Оператор lock позволяет ограничить одновременный доступ к блокам кода только до одного потока.  Дополнительные сведения см. в разделе [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Помеченные операторы|Оператор можно пометить и затем использовать ключевое слово [goto](../../../csharp/language-reference/keywords/goto.md) для перехода к помеченному оператору.  \(См. пример в следующей строке.\)|  
|Пустой оператор|Пустой оператор состоит из точки с запятой.  Он не выполняет никаких действий и его можно использовать в местах, в которых оператор необходим, но нет необходимости в выполнении каких\-либо действий.  В следующем примере показаны два способа использования пустого оператора:<br /><br /> [!CODE [csProgGuideStatements#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#25)]|  
  
## Внедренные операторы  
 В некоторых операторах, включая [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md), всегда есть внедренный оператор, следующий за ними.  Этот внедренный оператор может быть либо одним оператором, либо несколькими операторами, заключенными в скобки \({}\) в блоке оператора.  Даже однострочные внедренные операторы могут быть заключены в скобки \({}\), как показано в следующем примере:  
  
 [!CODE [csProgGuideStatements#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#26)]  
  
 Внедренный оператор, не заключенный в скобки \({}\), не может быть оператором объявления или помеченным оператором.  Это показано в следующем примере:  
  
 [!CODE [csProgGuideStatements#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#27)]  
  
 Чтобы устранить ошибку, поместите внедренный оператор в блок:  
  
 [!CODE [csProgGuideStatements#28](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#28)]  
  
## Вложенные блоки операторов  
 Блоки операторов могут быть вложенными, как показано в следующем коде:  
  
 [!CODE [csProgGuideStatements#29](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#29)]  
  
## Недостижимые операторы  
 Если компилятор определяет, что поток управления ни при каких обстоятельствах не сможет достичь определенного оператора, то он выдаст предупреждение CS0162, как показано в следующем примере:  
  
 [!CODE [csProgGuideStatements#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#22)]  
  
## Связанные разделы  
  
-   [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Выражения](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)