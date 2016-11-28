---
title: "Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#) | Microsoft Docs"
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
  - "индексированные свойства [C#]"
  - "программирование для Office [C#], индексированные свойства"
  - "свойства [C#], индексированные"
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C\# более удобным.  Индексированные свойства используются совместно с другими компонентами, представленными в Visual C\# 2010, например [именованными и необязательными аргументами](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), новым типом \([dynamic](../../../csharp/language-reference/keywords/dynamic.md)\) и [внедренными сведениями о типах](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) для расширения возможностей программирования для Microsoft Office.  
  
 В более ранних версиях C\# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения.  Однако не все свойства COM удовлетворяют этим ограничениям.  Например, свойство [Range](http://go.microsoft.com/fwlink/?LinkId=166053) Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона.  Раньше из\-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.  
  
 [!CODE [csProgGuideIndexedProperties#1](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideindexedproperties#1)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код:  
  
 [!CODE [csProgGuideIndexedProperties#2](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideindexedproperties#2)]  
  
> [!NOTE]
>  В предыдущем примере также используются [необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), представленные в Visual C\# 2010, которые позволяют опустить `Type.Missing`.  
  
 Подобным образом для задания значения свойства `Value` объекта [Range](http://go.microsoft.com/fwlink/?LinkId=179211) в Visual C\# 2008 и более ранних версий требуется два аргумента.  Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона.  Другой предоставляет значение для свойства `Value`.  До появления Visual C\# 2010 язык C\# допускал использование всего одного аргумента.  Поэтому вместо использования обычного метода "set" необходимо использовать метод `set_Value` или другое свойство — [Value2](http://go.microsoft.com/fwlink/?LinkId=166050).  В следующих примерах демонстрируются эти методы.  В примерах ячейке A1 задается значение `Name`.  
  
 [!CODE [csProgGuideIndexedProperties#3](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideindexedproperties#3)]  
  
 Индексированные свойства позволяют вместо этого использовать следующий код.  
  
 [!CODE [csProgGuideIndexedProperties#4](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideindexedproperties#4)]  
  
 Разработчики не могут создавать собственные индексированные свойства.  Эта функция поддерживает только использование имеющихся индексированных свойств.  
  
## Пример  
 Ниже приведен полный пример кода.  Подробные сведения о создании проекта, обращающегося к Office API, см. в разделе [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!CODE [csProgGuideIndexedProperties#5](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideindexedproperties#5)]  
  
## См. также  
 [Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)   
 [Пошаговое руководство. Программирование приложений Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)