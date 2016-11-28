---
title: "Практическое руководство. Создание раздела в реестре (Visual C#) | Microsoft Docs"
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
  - "ключи, создание в реестре"
  - "разделы реестра, создание [C#]"
  - "реестр, добавление ключей и значений [C#]"
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание раздела в реестре (Visual C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере пара значений "Name" и "Isabella" добавляется к текущему реестру пользователя в разделе "Names".  
  
## Пример  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## Компиляция кода  
  
-   Скопируйте код и вставьте его в метод `Main` консольного приложения.  
  
-   Замените параметр `Names` именем раздела, который находится прямо в узле HKEY\_CURRENT\_USER реестра.  
  
-   Замените параметр `Nam` именем значения, которое находится прямо в узле "Names".  
  
## Отказоустойчивость  
 Исследуйте структуру реестра и найдите подходящее место для создания раздела.  Например, можно открыть раздел "Software" для текущего пользователя и создать в нем подраздел с названием компании,  а затем добавить значения для этого подраздела.  
  
 Исключение может возникнуть при следующих условиях:  
  
-   Имя раздела представляет собой значение NULL.  
  
-   У пользователя отсутствуют разрешения на создание разделов реестра.  
  
-   Длина имени раздела превышает ограничение в 255 знаков.  
  
-   Раздел является закрытым.  
  
-   Раздел реестра доступен только для чтения.  
  
## Безопасность платформы .NET Framework  
 Безопаснее записывать данные в папку пользователя — `Microsoft.Win32.Registry.CurrentUser`, — чем в папку локального компьютера — `Microsoft.Win32.Registry.LocalMachine`.  
  
 При создании значения реестра следует решить, что делать, если такое значение уже есть.  Есть вероятность, что другой процесс, возможно вредоносный, уже создал это значение и имеет к нему доступ.  При добавлении данных в значение реестра они становятся доступными другим процессам.  Для предотвращения этого используется метод `Overload:Microsoft.Win32.RegistryKey.GetValue`.  Он возвращает NULL, если данный раздел не существует.  
  
 Хранить секретные данные, например пароли, в реестре в виде обычного текста небезопасно, даже если раздел реестра защищен списком ACL.  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Чтение, запись и удаление из реестра с C\#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)