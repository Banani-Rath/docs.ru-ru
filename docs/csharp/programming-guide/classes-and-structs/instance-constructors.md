---
title: "Конструкторы экземпляров (Руководство по программированию в C#) | Microsoft Docs"
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
  - "конструкторы [C#], конструкторы экземпляров"
  - "конструкторы экземпляров [C#]"
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Конструкторы экземпляров (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Конструкторы экземпляров используются для создания переменных члена экземпляра, если создание объекта [class](../../../csharp/language-reference/keywords/class.md) осуществляется с помощью выражения [new](../../../csharp/language-reference/keywords/new.md).  Для инициализации класса с модификатором [static](../../../csharp/language-reference/keywords/static.md) или статических переменных в нестатическом классе необходимо определить статический конструктор.  Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
 В следующем примере показан конструктор экземпляра.  
  
 [!CODE [csProgGuideObjects#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#5)]  
  
> [!NOTE]
>  Следует пояснить, что этот класс содержит открытые поля.  Использование открытых полей не рекомендуется использовать на практике, поскольку в этом случае любой метод в любом месте программы получает неограниченный и неконтролируемый доступ к внутренней работе объекта.  Члены данных обычно должны быть закрытыми, а доступ к ним должен осуществляться только посредством методов и свойства класса.  
  
 Этот конструктор экземпляра вызывается каждый раз при создании объекта на базе класса `CoOrds`.  Такой конструктор без аргументов называется *конструктором по умолчанию*.  Зачастую такие конструкторы используются для предоставления дополнительных конструкторов.  Например, можно добавить конструктор в класс `CoOrds`, позволяющий указывать начальные значения для членов данных:  
  
 [!CODE [csProgGuideObjects#76](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#76)]  
  
 Это позволяет создавать объекты `CoOrd` с начальными значениями по умолчанию или с другими начальными значениями:  
  
 [!CODE [csProgGuideObjects#77](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#77)]  
  
 Если класс не содержит конструктор, автоматически создается конструктор по умолчанию и для инициализации полей объекта используются значения по умолчанию.  Например, [int](../../../csharp/language-reference/keywords/int.md) инициализируется значением 0.  Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  Следовательно, поскольку конструктор по умолчанию класса `CoOrds` инициализирует все члены данных с нулевыми значениями, его можно удалить, при этом порядок работы класса не изменится.  Полный пример использования нескольких конструкторов см. в данном разделе в примере 1; пример автоматически созданного конструктора см. в примере 2.  
  
 Конструкторы экземпляров также можно использовать для вызова конструкторов экземпляров базового класса.  Конструктор класса может вызвать конструктор базового класса с помощью инициализатора:  
  
 [!CODE [csProgGuideObjects#78](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#78)]  
  
 В этом примере класс `Circle` передает значения радиуса и высоты конструктору, предоставленному классом `Shape`, для которого класс `Circle` является производным.  Полный текст кода с использованием классов `Shape` и `Circle` см. в данном разделе в примере 3.  
  
## Пример 1  
 В следующем примере демонстрируется класс с двумя конструкторами, один из которых не имеет аргументов, а второй имеет два аргумента.  
  
 [!CODE [csProgGuideObjects#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#4)]  
  
## Пример 2  
 В этом примере класс `Person` не имеет конструкторов, поэтому автоматически предоставляется конструктор по умолчанию, а все поля инициализируются со значениями по умолчанию.  
  
 [!CODE [csProgGuideObjects#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#8)]  
  
 Обратите внимание, что в значение по умолчанию `age` равно `0`, а значение по умолчанию `name` равно `null`.  Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## Пример 3  
 В следующем примере кода демонстрируется использование инициализатора базового класса.  Класс `Circle` является производным от основного класса `Shape`, а класс `Cylinder` является производным от класса `Circle`.  Конструктор каждого производного класса использует инициализатор своего базового класса.  
  
 [!CODE [csProgGuideObjects#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#9)]  
  
 Дополнительные примеры вызова конструкторов базовых классов см. в разделах [виртуальные](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) и [базовые](../../../csharp/language-reference/keywords/base.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [статический](../../../csharp/language-reference/keywords/static.md)