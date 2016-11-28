---
title: "base (Справочник по C#) | Microsoft Docs"
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
  - "base"
  - "BaseClass.BaseClass"
  - "base_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "base - ключевое слово [C#]"
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# base (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `base` используется для доступа к членам базового из производного класса:  
  
-   Вызов метода базового класса, который был переопределен другим методом.  
  
-   Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.  
  
 Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа экземпляра.  
  
 Использование ключевого слова `base` в статическом методе является недопустимым.  
  
 Базовый класс, к которому осуществляется доступ, является базовым классом, заданным в объявлении класса.  Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB, независимо от базового класса ClassA.  
  
## Пример  
 В приведенном примере метод `Getinfo` присутствует как в базовом классе `Person`, так и в производном классе `Employee`.  За счет использования ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.  
  
 [!CODE [csrefKeywordsAccess#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#1)]  
  
 Дополнительные примеры см. в разделах [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) и [override](../../../csharp/language-reference/keywords/override.md).  
  
## Пример  
 В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.  
  
 [!CODE [csrefKeywordsAccess#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#2)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)