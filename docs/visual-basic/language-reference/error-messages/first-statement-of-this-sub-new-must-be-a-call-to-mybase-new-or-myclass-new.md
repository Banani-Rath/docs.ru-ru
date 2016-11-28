---
title: "Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров) | Microsoft Docs"
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
  - "bc30148"
  - "vbc30148"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30148"
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Первым оператором в Sub New должен являться вызов MyBase.New или MyClass.New, поскольку в базовом классе "\<базовое\_имя\>"' класса "\<производное\_имя\>" отсутствует доступный Sub New, вызываемый без аргументов.  
  
 В производном классе все конструкторы должны вызывать конструктор базового класса \(`MyBase.New`\).  Если базовый класс содержит конструктор без параметров, доступный производному классу, то `MyBase.New` может вызываться автоматически.  Если такого конструктора нет, конструктор базового класса должен вызываться с параметрами; в этом случае автоматический вызов невозможен.  В этом случае первый оператор всех конструкторов производного класса должен вызывать конструктор с параметрами из базового класса или другой конструктор производного класса, который вызывает конструктор базового класса.  
  
 **Идентификатор ошибки**: BC30148  
  
### Чтобы исправить эту ошибку  
  
-   Вызовите конструктор `MyBase.New`, предоставляющий необходимые параметры, или другой конструктор, выполняющий подобный вызов.  
  
     Например, если базовый класс содержит конструктор, объявляются как `Public Sub New(ByVal index as Integer)`, первая выписка в конструкторе производного класса может быть `MyBase.New(100)`.  
  
## См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)