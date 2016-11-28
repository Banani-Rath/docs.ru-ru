---
title: "Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "расшифровка, строки"
  - "шифрование, строки"
  - "строки [Visual Basic], расшифровка"
  - "строки [Visual Basic], шифрование"
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере демонстрируется использование <xref:System.Security.Cryptography.DESCryptoServiceProvider> класса для шифрования и расшифровки строк с помощью версии стандартного алгоритма шифрования данных Triple \(<xref:System.Security.Cryptography.TripleDES>\) поставщика служб шифрования \(CSP\).  Первым шагом является создание простого класса\-оболочки, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде зашифрованной строки base\-64.  Затем оболочка используется для безопасного хранения собственных данных пользователя в общедоступном текстовом файле.  
  
 Можно использовать шифрование для защиты секретов пользователя \(например паролей\) и создания учетных данных, которые недоступны для чтения неавторизованным пользователям.  Это позволяет защитить от кражи удостоверения авторизованного пользователя, что защищает ресурсы пользователя и гарантирует неподдельность.  Шифрование также может защитить данные пользователя от доступа неавторизованных пользователей.  
  
 Дополнительные сведения см. в разделе [Службы криптографии](../Topic/Cryptographic%20Services.md).  
  
> [!IMPORTANT]
>  Rijndael \(также известный как расширенный стандарт шифрования \[AES\]\) и стандарт шифрования данных Triple \(3DES\) обеспечивают более высокую степень безопасности, чем DES, из\-за большего объёма вычислений.  Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.  
  
### Создание оболочки шифрования  
  
1.  Создайте класс `Simple3Des` для инкапсуляции методов шифрования и расшифровки.  
  
     [!CODE [VbVbalrStrings#38](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#38)]  
  
2.  Добавьте импорт пространства имен шифрования к началу файла, который содержит класс `Simple3Des`.  
  
     [!CODE [VbVbalrStrings#77](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#77)]  
  
3.  В классе `Simple3Des` добавьте закрытое поле для хранения поставщика служб шифрования 3DES.  
  
     [!CODE [VbVbalrStrings#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#39)]  
  
4.  Добавьте закрытый метод, который создает массив байтов указанной длины из хэша указанного ключа.  
  
     [!CODE [VbVbalrStrings#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#41)]  
  
5.  Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     Параметр `key` управляет методами `EncryptData` и `DecryptData`.  
  
     [!CODE [VbVbalrStrings#40](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#40)]  
  
6.  Добавьте открытый метод, который шифрует строку.  
  
     [!CODE [VbVbalrStrings#42](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#42)]  
  
7.  Добавьте открытый метод, который расшифровывает строку.  
  
     [!CODE [VbVbalrStrings#43](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#43)]  
  
     Класс\-оболочку теперь можно использовать для защиты ресурсов пользователей.  В данном примере он используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.  
  
### Проверка оболочки шифрования  
  
1.  В отдельном классе добавьте метод, использующий метод `EncryptData` оболочки, чтобы зашифровать строку и записать ее в папку "Мои документы" пользователя.  
  
     [!CODE [VbVbalrStrings#78](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#78)]  
  
2.  Добавьте метод, который считывает зашифрованную строку из папки "Мои документы" пользователя и расшифровывает строку с помощью метода оболочки `DecryptData`.  
  
     [!CODE [VbVbalrStrings#79](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#79)]  
  
3.  Добавьте код пользовательского интерфейса для вызова методов `TestEncoding` и `TestDecoding`.  
  
4.  Запустите приложение.  
  
     При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные при вводе неправильного пароля.  
  
## См. также  
 <xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael>   
 [Службы криптографии](../Topic/Cryptographic%20Services.md)