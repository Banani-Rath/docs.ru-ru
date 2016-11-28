---
title: "async (справочник по C#) | Microsoft Docs"
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
  - "async_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "async [C#]"
  - "async - ключевое слово [C#]"
  - "async - метод [C#]"
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 52
caps.handback.revision: 52
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# async (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `async` позволяет указать, что метод [лямбда\-выражение](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) или [анонимный метод](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) является асинхронным.  Если этот модификатор используется в методе или выражении, они называются асинхронными методами.  
  
```c#  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
  
```  
  
 Если вы только начали заниматься асинхронным программированием или не понимаете, как в асинхронном методе используется ключевое слово `await` для обеспечения потенциально долгой работы без блокировки потока вызывающего объекта, ознакомьтесь с общими сведениями в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
```  
string contents = await contentsTask;  
```  
  
 Метод выполняется синхронным образом до тех пор, пока не будет достигнуто первое выражение `await`, после чего метод приостанавливается, пока не будет завершена ожидаемая задача.  В то же время управление возвращается в вызывающий объект метода, как показано в примере в следующем разделе.  
  
 Если метод, который изменяется ключевым словом `async`, не содержит выражения или оператора `await`, метод выполняется синхронно.  Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих ключевого слова `await`, поскольку такая ситуация может указывать на ошибку.  См. раздел [Предупреждение компилятора \(уровень 1\) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).  
  
 Ключевое слово `async` — это контекстно\-зависимо ключевое слово, которое является ключевым словом, когда оно изменяет метод, лямбда\-выражение или анонимный метод.  Во всех других контекстах он интерпретируется как идентификатор.  
  
## Пример  
 В следующем примере показана структура и поток управления между обработчиком асинхронных событий `StartButton_Click` и асинхронным методом `ExampleMethodAsync`.  Результатом выполнения асинхронного метода является длина загруженного веб\-сайта.  Код подходит для приложения Windows Presentation Foundation \(WPF\) или приложения для Магазина Windows Presentation Foundation \(WPF\), которые создается в [!INCLUDE[vs_dev12](../../../csharp/getting-started/includes/vs_dev12_md.md)]; см. комментарии к коду для настройки приложения.  
  
```c#  
// You can run this code in Visual Studio 2013 as a WPF app or a Windows Store app.  
// You need a button (StartButton) and a textbox (ResultsTextBox).  
// Remember to set the names and handler so that you have something like this:  
// <Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
//         Click="StartButton_Click" Name="StartButton"/>  
// <TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
//          Text="TextBox" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
  
// To run the code as a WPF app:  
//    paste this code into the MainWindow class in MainWindow.xaml.cs,  
//    add a reference to System.Net.Http, and  
//    add a using directive for System.Net.Http.  
  
// To run the code as a Windows Store app:  
//    paste this code into the MainPage class in MainPage.xaml.cs, and  
//    add using directives for System.Net.Http and System.Threading.Tasks.  
  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // ExampleMethodAsync returns a Task<int>, which means that the method  
    // eventually produces an int result. However, ExampleMethodAsync returns  
    // the Task<int> value as soon as it reaches an await.  
    ResultsTextBox.Text += "\n";  
    try  
    {  
        int length = await ExampleMethodAsync();  
        // Note that you could put "await ExampleMethodAsync()" in the next line where  
        // "length" is, but due to when '+=' fetches the value of ResultsTextBox, you  
        // would not see the global side effect of ExampleMethodAsync setting the text.  
        ResultsTextBox.Text += String.Format("Length: {0}\n", length);  
    }  
    catch (Exception)  
    {  
        // Process the exception if one occurs.  
    }  
}  
  
public async Task<int> ExampleMethodAsync()  
{  
    var httpClient = new HttpClient();  
    int exampleInt = (await httpClient.GetStringAsync("http://msdn.microsoft.com")).Length;  
    ResultsTextBox.Text += "Preparing to finish ExampleMethodAsync.\n";  
    // After the following return statement, any method that's awaiting  
    // ExampleMethodAsync (in this case, StartButton_Click) can get the   
    // integer result.  
    return exampleInt;  
}  
// Output:  
// Preparing to finish ExampleMethodAsync.  
// Length: 53292  
  
```  
  
> [!IMPORTANT]
>  Дополнительные сведения о задачах и коде, который выполняется во время ожидания задачи, см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Полный пример WPF, в котором используются аналогичные элементы, см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Можно загрузить код пошагового руководства из раздела [Примеры кода разработчика](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
## Типы возвращаемых значений  
 Асинхронный метод может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или [void](../../../csharp/language-reference/keywords/void.md).  Метод не может объявить все параметры [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md), но может вызывать методы, которые имеют такие параметры.  
  
 `Task<TResult>` указывается в качестве возвращаемого типа асинхронного метода, если оператор [return](../../../csharp/language-reference/keywords/return.md) метода задает операнд типа `TResult`.  Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении.  То есть вызов метода возвращает `Task`, однако когда `Task` завершен, любое выражение `await`, которое ожидает `Task`, возвращает значение `void`.  
  
 Возвращаемый тип `void` используется в основном для определения обработчиков событий, которые требуют этого возвращаемого типа.  Вызывающий объект асинхронного метода, возвращающего `void`, не может ожидать его и перехватывать создаваемые методом исключения.  
  
 Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## См. также  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [await](../../../csharp/language-reference/keywords/await.md)   
 [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)