---
title: "Арифметические операторы в Visual Basic | Microsoft Docs"
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
  - "арифметические операторы, сведения об арифметических операторах"
  - "операторы сдвига разряда"
  - "побитовые операторы"
  - "деление, на ноль"
  - "операторы [Visual Basic], арифметические"
  - "операторы [Visual Basic], сдвиг битов"
  - "операторы [Visual Basic], побитовые"
  - "безопасность типа"
  - "код Visual Basic, операторы"
  - "ноль, деление на ноль"
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Арифметические операторы в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Арифметические операторы используются для выполнения многих известных арифметических операций, включая вычисление числовых значений, представленных литералами, переменными, другими выражениями, вызовами функций и свойств, а также константами.  Также с арифметическими операторами рассматриваются операторы поразрядного сдвига, которые работают на уровне отдельных битов операндов и осуществляют их сдвиг влево или вправо.  
  
## Арифметические операции  
 Можно сложить два значения в выражении с помощью оператора [Оператор \+](../../../../visual-basic/language-reference/operators/addition-operator.md) или вычесть одно из другого с помощью оператора [Оператор "\-"](../../../../visual-basic/language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!CODE [VbVbalrOperators#57](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#57)]  
  
 Отрицание также использует оператор [Оператор "\-"](../../../../visual-basic/language-reference/operators/subtraction-operator.md), но только с одним операндом, как показано в следующем примере.  
  
 [!CODE [VbVbalrOperators#58](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#58)]  
  
 Умножение и деление используют, соответственно, операторы [Оператор \*](../../../../visual-basic/language-reference/operators/multiplication-operator.md) и [Оператор \/](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), как показано в следующем примере.  
  
 [!CODE [VbVbalrOperators#59](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#59)]  
  
 Для возведения в степень используется оператор [Оператор ^](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!CODE [VbVbalrOperators#60](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#60)]  
  
 Целочисленное деление выполняется с помощью оператора [Оператор \\](../../../../visual-basic/language-reference/operators/integer-division-operator.md).  Целочисленное деление возвращает частное, т.е. целое число, представляющее — сколько раз делимое делится на делитель без остатка.  Делитель и делимое должны быть целыми типами \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` и `ULong`\) для использования данного оператора.  Все другие типы сначала необходимо преобразовать к целому типу.  Ниже представлен пример целочисленного деления.  
  
 [!CODE [VbVbalrOperators#61](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#61)]  
  
 Арифметическая операция деления с остатком выполняется с помощью [Оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md).  Этот оператор возвращает остаток от деления делимого на делитель целое количество раз.  Если делитель и делимое являются целыми типами, возвращенное значение является целым.  Если делитель и делимое являются типами с плавающей запятой, возвращенное значение также является переменной с плавающей запятой.  Следующий пример иллюстрирует такое поведение.  
  
 [!CODE [VbVbalrOperators#62](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#62)]  
  
 [!CODE [VbVbalrOperators#63](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#63)]  
  
### Попытка деления на ноль  
 Деление на ноль приводит к разным результатам, в зависимости от типов данных.  При целочисленном делении \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`\), [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] формирует исключение <xref:System.DivideByZeroException>.  При операциях деления с типом данных `Decimal` или `Single` [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] также формирует исключение <xref:System.DivideByZeroException>.  
  
 При делении с плавающей запятой с использованием типа данных `Double` исключение не формируется, а результатом является член класса, представляющий <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>, в зависимости от делимого.  В следующей таблице обобщены различные результаты попытки деления значения типа `Double` на ноль.  
  
|||||  
|-|-|-|-|  
|Тип данных делимого|Тип данных делителя|Значение делимого|Результат|  
|`Double`|`Double`|0|<xref:System.Double.NaN> \(не заданное математически число\)|  
|`Double`|`Double`|\> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 После перехвата исключения <xref:System.DivideByZeroException> можно использовать его члены при обработке.  Например, свойство <xref:System.Exception.Message%2A> содержит текст сообщения для исключения.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Операции поразрядного сдвига  
 Операция поразрядного сдвига выполняет арифметический сдвиг над набором разрядов.  Набор содержится в операнде слева, а операнд справа указывает число позиций для сдвига набора.  Можно сдвинуть биты вправо с помощью оператора [Оператор \>\>](../../../../visual-basic/language-reference/operators/right-shift-operator.md) или влево с помощью оператора [Оператор \<\<](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Тип данных сдвигаемого операнда должен быть `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`.  Тип данных операнда количества разрядов сдвига должен быть `Integer` или его необходимо расширить до `Integer`.  
  
 Арифметические сдвиги не являются циклическими. Это означает, что биты, сдвинутые в один конец результата, не вводятся повторно в другой конец.  Позиции двоичного разряда, освобожденные сдвигом, устанавливаются следующим образом:  
  
-   0 для арифметического сдвига влево  
  
-   0 для арифметического сдвига вправо положительного числа  
  
-   0 для арифметического сдвига вправо беззнакового типа данных \(`Byte`, `UShort`, `UInteger`, `ULong`\)  
  
-   1 для арифметического сдвига вправо отрицательного числа \(`SByte`, `Short`, `Integer` или `Long`\)  
  
 В следующем примере значение `Integer` сдвигается и влево и вправо.  
  
 [!CODE [VbVbalrOperators#64](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#64)]  
  
 В результате арифметического сдвига никогда не создаются исключения переполнения.  
  
## Поразрядные операции  
 Логические операторы `Not`, `Or`, `And` и `Xor` также выполняют поразрядные арифметические операции, если они применяются для числовых значений.  Дополнительные сведения см. в подразделе "Побитовые операции" в разделе [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## Строгая типизация  
 Обычно необходимо, чтобы типы операндов совпадали.  Например, при сложение с переменной типа `Integer`, ее следует складывать с другой переменной типа `Integer` и результат также следует присваивать переменной типа `Integer`.  
  
 Одним из способов корректного программирования с использованием типобезопасного кода является использование [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md).  Если установить `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически выполняет *типобезопасные* преобразования.  Например, при попытке добавить переменную типа `Integer` к переменной типа `Double` и присвоении значения переменной типа `Double`, операция проходит нормально, поскольку значение типа `Integer` может быть преобразовано к типу `Double` без потери данных.  С другой стороны, небезопасные преобразования вызывают ошибку компилятора при использовании `Option Strict On`.  Например, при попытке добавить переменную типа `Integer` к переменной типа `Double` и присвоении значения переменной типа `Integer`, возникнет ошибка компилятора, поскольку переменную типа `Double` нельзя неявно преобразовать в тип `Integer`.  
  
 Но если задать `Option Strict Off`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяет использовать неявные сужающие \(небезопасные\) преобразования, хотя они могут привести к потере данных или точности.  По этой причине рекомендуется использовать `Option Strict On` при написании конечного кода.  Дополнительные сведения см. в разделе [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## См. также  
 [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Операторы поразрядного сдвига](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)