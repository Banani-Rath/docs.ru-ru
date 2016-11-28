---
title: "Тип данных Byte (Visual Basic) | Microsoft Docs"
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
  - "vb.Byte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Byte - тип данных"
  - "типы данных [Visual Basic], назначение"
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Тип данных Byte (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Содержит 8\-битные \(1\-байтовые\) целые числа без знака в диапазоне от –0 до 255.  
  
## Заметки  
 Используйте тип данных `Byte` для хранения двоичных данных.  
  
 Значение по умолчанию для типа `Byte` равно 0.  
  
## Советы по программированию  
  
-   **Отрицательные числа**. Поскольку `Byte` — это тип без знака, он не может представлять отрицательное число.  Если используется оператор унарного минуса \(`-`\) в выражении, вычисляющем значение типа `Byte`, то в Visual Basic сначала выполняется преобразование выражения к типу `Short`.  
  
-   **Преобразования форматов.** Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он автоматически выполняет преобразование форматов.  Двоичные данные, хранящиеся в переменных типа `Byte` и массивах, сохраняются во время преобразования формата.  Не следует использовать переменные `String` для хранения двоичных данных, так как их содержимое может быть повреждено при преобразовании между форматами ANSI и Юникод.  
  
-   **Расширение**. Тип данных `Byte` можно расширить до `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` или `Double`.  Это означает, что можно преобразовать `Byte` к любому из этих типов без появления ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типа.** Тип `Byte` не имеет литералов и идентификаторов.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=fullName>.  
  
## Пример  
 В следующем примере `b` является переменной типа `Byte`.  Инструкции показывают диапазон значений переменной и приложение к ней операторов поразрядного сдвига.  
  
 [!CODE [VbVbalrDataTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrDataTypes#16)]  
  
## См. также  
 <xref:System.Byte?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)