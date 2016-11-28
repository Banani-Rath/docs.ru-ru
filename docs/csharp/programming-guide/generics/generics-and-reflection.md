---
title: "Универсальные типы и отражение (Руководство по программированию в C#) | Microsoft Docs"
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
  - "универсальные шаблоны [C#], отражение"
  - "отражение [C#], универсальные типы"
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Универсальные типы и отражение (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Так как среда CLR имеет доступ к информации универсальных типов во время выполнения, можно использовать отражение для получения информации об универсальных типах таким же образом, как и о не универсальных типах.  Дополнительные сведения см. в разделе [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 В платформе [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] несколько новых членов добавлены в класс <xref:System.Type> для предоставления информации об универсальных типах во время выполнения.  Дополнительную информацию о том, как использовать эти методы и свойства, см. в документацию по этим классам. Пространство имен <xref:System.Reflection.Emit> также содержит новые члены, которые поддерживают универсальность.  Дополнительные сведения см. в разделе [How to: Define a Generic Type with Reflection Emit](../Topic/How%20to:%20Define%20a%20Generic%20Type%20with%20Reflection%20Emit.md).  
  
 Список неизменных условий для понятий, используемых в универсальном отражении, см. в заметках к свойству <xref:System.Type.IsGenericType%2A>.  
  
|Имя члена класса System.Type|Описание|  
|----------------------------------|--------------|  
|<xref:System.Type.IsGenericType%2A>|В случае универсального типа возвращает значение true.|  
|<xref:System.Type.GetGenericArguments%2A>|Возвращает массив объектов `Type`, представляющих аргументы типа, поставляемые для созданного типа, или параметры типа для определения универсального типа.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Возвращает определение лежащего в основе универсального типа для текущего создаваемого типа.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Возвращает массив объектов `Type`, которые представляют ограничения, накладываемые на параметр текущего универсального типа.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Возвращает значение true, если тип или любые включающие его типы или методы содержат параметры типа, для которых определенные типы не были предоставлены.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Возвращает комбинацию флагов `GenericParameterAttributes`, описывающих особые ограничения параметра текущего универсального типа.|  
|<xref:System.Type.GenericParameterPosition%2A>|Для объекта `Type`, представляющего параметр типа, возвращает положение параметра типа в списке параметров типа для определения универсального типа или определения универсального метода, использованного для объявления этого параметра типа.|  
|<xref:System.Type.IsGenericParameter%2A>|Возвращает значение, которое показывает, представляет ли текущий `Type` параметр типа для универсального типа или определения метода.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Возвращает значение, которое показывает, представляет ли текущий <xref:System.Type> определение универсального типа, из которого могут быть созданы другие универсальные типы.  Возвращает значение true, если тип представляет определение универсального типа.|  
|<xref:System.Type.DeclaringMethod%2A>|Возвращает универсальный метод, который определяет параметр текущего универсального типа, или значение NULL, если параметр типа не был определен универсальным методом.|  
|<xref:System.Type.MakeGenericType%2A>|Замещает элементы массива типов для параметров типа определения текущего универсального типа и возвращает объект <xref:System.Type>, представляющий созданный в результате тип.|  
  
 Кроме того, новые члены добавляются в класс <xref:System.Reflection.MethodInfo>, для предоставления информации об универсальных типах во время выполнения.  Список неизменяемых условий для терминов, используемых для отражения универсальных методов, см. в примечаниях к свойству <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>.  
  
|Имя члена класса System.Reflection.MemberInfo|Описание|  
|---------------------------------------------------|--------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|В случае универсального метода возвращает значение true.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Возвращает массив объектов Type, представляющих аргументы типа для созданного универсального метода или параметры типа для определения универсального метода.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Возвращает определение лежащего в основе универсального метода для текущего создаваемого метода.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Возвращает значение true, если метод или любые включающие его типы содержат какие\-либо параметры типа, для которых определенные типы не были предоставлены.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Возвращает значение true, если текущий объект <xref:System.Reflection.MethodInfo> представляет определение универсального метода.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Заменяет параметры типа элементами массива типов для определения текущего универсального метода и возвращает объект <xref:System.Reflection.MethodInfo>, представляющий итоговый сконструированный метод.|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Reflection and Generic Types](../Topic/Reflection%20and%20Generic%20Types.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)