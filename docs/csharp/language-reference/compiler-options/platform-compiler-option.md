---
title: "/platform (C# Compiler Options) | Microsoft Docs"
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
  - "/platform"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "platform compiler option [C#]"
  - "-platform compiler option [C#]"
  - "/platform compiler option [C#]"
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
caps.handback.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# /platform (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, какая версия среды CLR может выполнить сборку.  
  
## Синтаксис  
  
```  
/platform:string  
```  
  
#### Параметры  
 `string`  
 anycpu \(по умолчанию\), anycpu32bitpreferred, ARM, x64, x86 или Itanium.  
  
## Заметки  
  
-   **anycpu** \(по умолчанию\) компилирует вашу сборку для выполнения для любой платформе.  Приложение по возможности выполняется как 64\-разрядный процесс и возвращается к 32\-разрядному, если доступен только этот режим.  
  
-   **anycpu32bitpreferred** — сборка компилируется для работы на любой платформе  Приложение выполняется в 32\-разрядном режиме в системах, поддерживающих и 64 и 32\-разрядные приложения.  Можно указать этот параметр только для проектов, нацеленных на .NET Framework 4.5.  
  
-   **ARM** компилирует сборку для выполнения на компьютере с процессором Advanced RISC Machine \(ARM\).  
  
-   **x64** компилирует сборку для выполнения 64\-разрядной средой CLR на компьютере, который поддерживает набор инструкций AMD64 или EM64T.  
  
-   **x86** компилирует сборку для выполнения 32\-разрядной, совместимой с x86 средой CLR.  
  
-   **Itanium** компилирует сборку для выполнения 64\-разрядной средой CLR на компьютере с процессором Itanium.  
  
 В 64\-разрядной операционной системе Windows:  
  
-   Сборки, скомпилированные с параметром **\/platform:x86**, выполняются в 32\-разрядной среде CLR в подсистеме WOW64.  
  
-   Библиотека DLL, скомпилированная с помощью параметра **\/platform:anycpu**, выполняется в той же среде CLR, в которую загружается процесс.  
  
-   Исполняемые файлы, скомпилированные с помощью параметра **\/platform:anycpu**, будут выполняться в 64\-разрядной среде CLR.  
  
-   Исполняемые файлы, скомпилированные с помощью параметра **\/platform:anycpu32bitpreferred**, выполняются на 32\-разрядной среде CLR.  
  
 Параметр **anycpu32bitpreferred** допустим только для исполняемых файлов \(.EXE\) и требует .NET Framework 4.5.  
  
 Дополнительные сведения о разработке приложений для запуска в 64\-разрядной операционной системе Windows см. в разделе [64\-разрядные приложения](../Topic/64-bit%20Applications.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Измените значение свойства **Конечная платформа** и для проектов, нацеленных на .NET Framework 4.5, установите или снимите флажок **Предпочтительно: 32\-разрядн.**  
  
 **Бумага для заметок** Параметр **\/platform** не доступен в среде разработки Visual C\# Express.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.  
  
## Пример  
 В следующем примере показано использование параметра **\/platform** для указания того, что приложение должно выполняться на 64\-разрядной среде CLR с 64\-разрядной операционной системой Windows.  
  
```  
csc /platform:anycpu filename.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)