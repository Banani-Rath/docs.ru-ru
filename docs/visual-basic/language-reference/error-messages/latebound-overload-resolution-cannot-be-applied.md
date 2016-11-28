---
title: "Разрешение перегружаемой функции с поздним связыванием не может быть применено к &lt;имяПроцедура&gt;, так как типом экземпляра, к которому осуществляется доступ, является интерфейс | Microsoft Docs"
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
  - "vbc30933"
  - "bc30933"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30933"
  - "разрешение перегрузки, с аргументом позднего связывания"
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Разрешение перегружаемой функции с поздним связыванием не может быть применено к &lt;имяПроцедура&gt;, так как типом экземпляра, к которому осуществляется доступ, является интерфейс
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компилятор пытается обратиться по ссылке к перегруженному свойству или процедуре, но доступ не выполняется, так как аргумент имеет тип `Object` и объект, к которому производится обращение, имеет тип данных интерфейса.  Аргумент `Object` указывает компилятору разрешить ссылку с поздней привязкой.  
  
 В этом случае компилятор разрешает перегрузку посредством реализующего класса вместо базового интерфейса.  Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию в качестве перегруженной, так как ее имя отличается.  Это указывает компилятору игнорировать переименованную версию, даже если был принят правильный выбор для разрешения ссылок.  
  
 **Идентификатор ошибки:** BC30933  
  
### Чтобы исправить эту ошибку  
  
-   `CType` используется для приведения аргументов `Object` к типу, указанному в сигнатуре перегрузки, которую требуется вызвать.  
  
     Обратите внимание, что он не помогает приведению объекта, к которому производится обращение, к базовому интерфейсу.  Необходимо привести аргумент для исключения этой ошибки.  
  
## Пример  
 В следующем примере показан вызов перегруженной процедуры `Sub`, которая вызывает эту ошибку во время компиляции.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 В предыдущем примере, если компилятор разрешил вызов `s1` как написано, потребуется разрешение с помощью класса `c1` вместо интерфейса `i1`.  Это будет означать, что компилятор не будет учитывать `s2`, так как его имя отличается в `c1`, даже если это правильный выбор, определенный `i1`.  
  
 Можно исправить ошибку путем изменения вызова одной из следующих строк кода:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Каждая из строк предыдущего кода явно приводит переменную `Object` `o1` к одному из типов параметров, определенных для перегрузки.  
  
## См. также  
 [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Разрешение перегрузки](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)