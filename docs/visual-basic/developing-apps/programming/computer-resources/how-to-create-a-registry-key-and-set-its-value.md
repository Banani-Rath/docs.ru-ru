---
title: "Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic | Microsoft Docs"
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
  - "RegistryKey.CreateSubKey"
  - "RegistryKey.SetValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "примеры [Visual Basic], реестр"
  - "разделы реестра, создание"
  - "разделы реестра, значения параметра"
  - "реестр, добавление разделов"
  - "реестр, добавление значений"
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод `CreateSubKey` объекта `My.Computer.Registry` позволяет создать раздел реестра.  
  
## Процедура  
  
#### Создание раздела реестра  
  
-   Используйте метод `CreateSubKey`, задав куст, в который нужно поместить раздел, а также имя раздела.  Параметр `Subkey` нечувствителен к регистру.  В этом примере создается раздел реестра `MyTestKey` в HKEY\_CURRENT\_USER.  
  
     [!CODE [VbResourceTasks#17](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#17)]  
  
#### Создание раздела реестра и установка его значения  
  
1.  Используйте метод `CreateSubkey`, задав куст, в который нужно поместить раздел, а также имя раздела.  В этом примере создается раздел реестра `MyTestKey` в HKEY\_CURRENT\_USER.  
  
     [!CODE [VbResourceTasks#17](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#17)]  
  
2.  Установка значения с помощью метода `SetValue`.  В этом примере строке "  MyTestKeyValue" присваивается значение "Это тестовое значение".  
  
     [!CODE [VbResourceTasks#14](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#14)]  
  
## Пример  
 В этом примере создается раздел реестра `MyTestKey`в HKEY\_CURRENT\_USER, а затем строке `MyTestKeyValue` присваивается значение `This is a test value`.  
  
 [!CODE [VbResourceTasks#15](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#15)]  
  
## Отказоустойчивость  
 Исследуйте структуру реестра и найдите подходящее место для создания раздела.  Например, можно открыть раздел HKEY\_CURRENT\_USER\\Software для текущего пользователя и создать в нем подраздел с названием компании,  а затем добавить значения для этого подраздела.  
  
 При чтении реестра из веб\-приложения то, какой пользователь будет считаться текущим, зависит от проверки подлинности и олицетворения, реализованных в веб\-приложении.  
  
 Безопаснее записывать данные в ветку текущего пользователя \(<xref:Microsoft.Win32.Registry.CurrentUser>\), чем в ветку локального компьютера \(<xref:Microsoft.Win32.Registry.LocalMachine>\).  
  
 При создании значения реестра следует решить, что делать, если такое значение уже есть.  Есть вероятность, что другой процесс, возможно вредоносный, уже создал это значение и имеет к нему доступ.  При добавлении данных в значение реестра они становятся доступными другим процессам.  Для предотвращения этого используется метод <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.  Он возвращает `Nothing`, если данный раздел не существует.  
  
 Небезопасно хранить секретные данные, например пароли, в реестре обычным текстом, даже если раздел реестра защищен ACL \(списком управления доступом\)  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Имя раздела представляет собой значение `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   У пользователя отсутствуют разрешения на создание разделов реестра \(<xref:System.Security.SecurityException>\).  
  
-   Длина имени раздела превышает ограничение в 255 знаков \(<xref:System.ArgumentException>\).  
  
-   Раздел является закрытым \(<xref:System.IO.IOException>\).  
  
-   Раздел реестра доступен только для чтения \(<xref:System.UnauthorizedAccessException>\).  
  
## Безопасность платформы .NET Framework  
 Для выполнения этого процесса сборке требуется уровень привилегий, предоставляемых классом <xref:System.Security.Permissions.RegistryPermission>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.  Например, локальное приложение, имеющее разрешение управления доступом для кода, может не иметь разрешения операционной системы.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>   
 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>   
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md)