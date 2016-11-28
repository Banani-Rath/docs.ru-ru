---
title: "Строковые функции (Visual Basic) | Microsoft Docs"
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
  - "строковые функции"
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Строковые функции (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующей таблице перечислены имеющиеся в Visual Basic функции поиска в строках и работы с ними.  
  
|Метод .NET Framework|Описание|  
|--------------------------|--------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Возвращает значение типа `Integer`, представляющее код знака, соответствующий знаку.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Возвращает знак, связанный с указанным кодом знака.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Возвращает массив \(с индексацией от нуля\), который содержит подмножество массива типа `String`, выделяемое согласно указанным условиям фильтрации.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Возвращает строку, отформатированную в соответствии с инструкциями, содержащимися в формате выражения `String`.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Возвращает выражение в формате денежной единицы с использованием символа денежной единицы, определенного в системной панели управления.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Возвращает строковое выражение, представляющее значение даты и времени.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Возвращает выражение в формате числа.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Возвращает выражение в формате процента \(т. е. с коэффициентом 100\), в конец которого добавлен знак %.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Возвращает целое число, указывающее начальную позицию первого вхождения одной строки в другую.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Возвращает позицию первого вхождения одной строки в другую, начиная с правого конца строки.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Возвращает строку, образуемую путем соединения нескольких подстрок, содержащихся в массиве.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Возвращает строку или символ, преобразованные в нижний регистр.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Возвращает строку, содержащую указанное число знаков с левой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Возвращает целое число, показывающее число знаков в строке.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Возвращает выровненную по левому краю строку запрашиваемой длины, содержащую указанную строку.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Возвращает строку, содержащую копию указанной строки без пробелов в начале.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Возвращает строку, содержащую указанное число знаков строки.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Возвращает строку, в которой указанная подстрока заданное число раз заменена другой подстрокой.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Возвращает строку, содержащую указанное число знаков с правой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Возвращает выровненную по правому краю строку, содержащую указанную строку, настроенную под указанную длину.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Возвращает строку, содержащую копию указанной строки без пробелов в конце.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Возвращает строку, состоящую из указанного числа пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Возвращает одномерный массив \(с индексацией от нуля\), содержащий указанное число подстрок.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Возвращает \-1, 0 или 1 в зависимости от результата сравнения строк.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Возвращает строку, преобразованную как указано.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Возвращает строку или объект, состоящие из указанного знака, повторенного определенное количество раз.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Возвращает строку, содержащую те же знаки, что и в заданной строке, но в противоположном порядке.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Возвращает строку, содержащую копию указанной строки без пробелов в начале и конце.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Возвращает строку или знак, содержащий указанную строку, преобразованную в верхний регистр.|  
  
 С помощью оператора [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) можно указать, следует ли выполнять сравнение строк с использованием порядка сортировки текста без учета регистра, определяемого языковым стандартом системы \(`Text`\), или же вести сортировку по внутренним двоичным представлениям знаков \(`Binary`\).  По умолчанию задан метод сравнения текста `Binary`.  
  
## Пример  
 В данном примере функция `UCase` используется для возврата строки в верхнем регистре.  
  
 [!CODE [VbVbalrStrings#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#31)]  
  
## Пример  
 В данном примере функция `LTrim` используется, чтобы убрать пробелы в начале, а функция `RTrim` — чтобы убрать пробелы в конце строковой переменной.  Функция `Trim` в примере используется для удаления обоих типов пробелов.  
  
 [!CODE [VbVbalrStrings#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#25)]  
  
## Пример  
 В данном примере функция `Mid` используется для возврата указанного числа знаков строки.  
  
 [!CODE [VbVbalrStrings#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#17)]  
  
## Пример  
 В данном примере `Len` используется для возврата числа знаков в строке.  
  
 [!CODE [VbVbalrStrings#33](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#33)]  
  
## Пример  
 В данном примере функция `InStr` используется для возврата позиции первого вхождения одной строки в другую.  
  
 [!CODE [VbVbalrStrings#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#8)]  
  
## Пример  
 В данном примере показаны различные способы использования функции `Format` для форматирования значений с применением как форматов `String`, так и определенных пользователем форматов.  Фактическое отображение системой разделителя даты \(`/`\), разделителя времени \(`:` и индикаторов AM\/PM \(`t` и `tt`\) зависит от региональных параметров, применяемых кодом.  При отображении времени и даты в среде разработки используется короткий формат времени и даты региональных установок кода.  
  
> [!NOTE]
>  Для языков, использующих 24\-часовой формат, индикаторы AM\/PM \(`t` и `tt`\) не отображаются.  
  
 [!CODE [VbVbalrStrings#27](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#27)]  
  
## См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Члены библиотеки времени выполнения Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)   
 [Сводка по работе со строками](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)