---
title: "Оператор Using (Visual Basic) | Microsoft Docs"
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
  - "vb.using"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "освобождение ресурсов"
  - "ресурсы [Visual Basic], освобождение"
  - "Try...Catch...Finally - операторы, эквивалент оператору Using"
  - "Using - оператор"
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
caps.handback.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор Using (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет начало блока `Using` и при необходимости получает системные ресурсы, которыми управляет блок.  
  
## Синтаксис  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`resourcelist`|Необходим, если не используется `resourceexpression`.  Список из одного или нескольких системных ресурсов, управления данного блока `Using`, разделенных запятыми.|  
|`resourceexpression`|Необходим, если не используется `resourcelist`.  Переменная ссылки или выражение ссылающееся на системный ресурс, контролируемый этим блоком `Using`.|  
|`statements`|Необязательный параметр.  Блок операторов, запускаемый блоком `Using`.|  
|`End Using`|Обязательное.  Завершает определение блока `Using` и удаляет все ресурсы, которыми он управляет.|  
  
 Каждый ресурс в элементе `resourcelist` имеет следующие синтаксис и составляющие:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 \-или\-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## Части resourcelist  
  
|||  
|-|-|  
|Термин|Определение|  
|`resourcename`|Обязательное.  Переменная ссылки, ссылающаяся на системный ресурс, которым управляет блок `Using`.|  
|`New`|Необходим, если оператор `Using` получает ресурс.  Если ресурс уже приобретен, используйте следующий альтернативный синтаксис.|  
|`resourcetype`|Обязательное.  Класс ресурса.  Класс должен реализовывать интерфейс <xref:System.IDisposable>.|  
|`arglist`|Необязательный параметр.  Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype`.  Дополнительные сведения см. в разделе [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Обязательное.  Переменная или выражение, которое ссылается на системный ресурс, отвечающий требованиям `resourcetype`.  Если используется альтернативный синтаксис, необходимо получить ресурс перед передачей управления оператору `Using`.|  
  
## Заметки  
 В некоторых случаях код требует неуправляемые ресурсы, такие как дескриптор файла, оболочка COM или SQL\-соединение.  Блок `Using` гарантирует удаление одного или более подобных ресурсов после завершения вашего кода, работающего с ними.  Это делает их доступными для использования другим кодом.  
  
 Управляемые ресурсы удаляются с помощью сборщика мусора платформе .NET Framework \(GC\) без дополнительного кодирования.  Для управляемых ресурсов блок `Using` необязателен.  Тем не менее по\-прежнему можно использовать блок`Using` для принудительного удаления управляемого ресурса вместо того, чтобы ждать сборщика мусора.  
  
 Блок `Using` состоит из трех частей: приобретение, использование и удаление.  
  
-   *Acquisition* означает создание переменной и инициализация ее для ссылки на ресурсы системы.  Оператор `Using` может получить один или больше ресурсов либо может получить ровно один ресурс перед вводом блока и заданием его в операторе `Using`.  Если указать `resourceexpression`, необходимо получить ресурс перед передачей управления оператору `Using`.  
  
-   *Usage* означает получение доступа к ресурсам и выполнение над ними действий.  Операторы между `Using` и `End Using` представляют собой использование ресурсов.  
  
-   *Disposal* означает вызов метода <xref:System.IDisposable.Dispose%2A> для объекта в `resourcename`.  Это позволяет объекту удалить его ресурсы чисто.  Оператор `End Using` удаляет ресурсы блока `Using`.  
  
## Поведение  
 Блок `Using` ведет себя подобно конструкции `Try`...`Finally`, в которой блок `Try` использует ресурсы и блок `Finally` удаляет их.  В результате блок `Using` гарантирует удаление ресурсов, независимо от способа выхода из блока.  Это справедливо даже в случае необработанного исключения, кроме <xref:System.StackOverflowException>.  
  
 Область действия переменной каждого ресурса полученного оператором `Using`, ограничена блоком `Using`.  
  
 Если указать более одного системного ресурса в операторе `Using`, это будет эквивалентно тому, если бы блоки `Using` были вложены друг в друга.  
  
 Если `resourcename``Nothing`, в <xref:System.IDisposable.Dispose%2A> не выполняется и исключение не создается.  
  
## Структурированная обработка исключений с помощью блока Using  
 Если необходимо обрабатывать исключения, которые могут возникнуть в блоке `Using`, можно добавить в него завершающую конструкцию `Try`...`Finally`.  Если требуется обрабатывать случаи, где оператор `Using` не может успешно получить ресурсы, можно проверить, является ли `resourcename` `Nothing`.  
  
## Структурированная обработка исключений без использования блока Using  
 Если необходимо более тщательно контролировать приобретение ресурсов, или требуется дополнительный код в блоке `Finally`, можно переписать блок `Using` как конструкцию `Try`...`Finally`.  В следующем примере показана схема конструкций `Try` и `Using`, которые эквивалентны в приобретении и удалении `resource`.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  В коде внутри блока `Using` не следует присваивать объект в `resourcename` другой переменной.  При выходе из блока `Using` ресурс будет удален, и другая переменная не сможет получить доступ к ресурсу, на которые она указывает.  
  
## Пример  
 В следующем примере создается файл с именем log.txt и записывает 2 линии текста в файл.  В примере также читает, что один и тот же файл и отображает линии текста.  
  
 Поскольку классы <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> реализуют интерфейс <xref:System.IDisposable>, код может использовать выписки `Using`, чтобы гарантировать, что файл правильно закрыть после записи и операций чтения.  
  
 [!CODE [VbVbalrStatements#50](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#50)]  
  
## См. также  
 <xref:System.IDisposable>   
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Практическое руководство. Удаление системного ресурса](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)