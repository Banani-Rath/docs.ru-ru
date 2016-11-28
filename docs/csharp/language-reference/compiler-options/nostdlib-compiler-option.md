---
title: "/nostdlib (C# Compiler Options) | Microsoft Docs"
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
  - "/nostdlib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nostdlib compiler option [C#]"
  - "-nostdlib compiler option [C#]"
  - "/nostdlib compiler option [C#]"
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# /nostdlib (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.  
  
## Синтаксис  
  
```  
/nostdlib[+ | -]  
```  
  
## Заметки  
 Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.  
  
 Если вы не укажете параметр **\/nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу \(как и при указании **\/nostdlib\-**\). Указание **\/nostdlib** дает тот же результат, что и указание **\/nostdlib\+**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Щелкните страницу свойств **сборки**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Не ссылаться на mscorlib.dll**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)