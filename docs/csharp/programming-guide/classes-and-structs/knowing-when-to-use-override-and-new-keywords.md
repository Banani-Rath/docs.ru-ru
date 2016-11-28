---
title: "Использование ключевых слов &quot;Override&quot; и &quot;New&quot; (Руководство по программированию в C#) | Microsoft Docs"
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
  - "new - ключевое слово [C#]"
  - "override - ключевое слово [C#]"
  - "полиморфизм [C#], использование операторов override и new [C#]"
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Использование ключевых слов &quot;Override&quot; и &quot;New&quot; (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# метод в производном классе может иметь то же имя, что и метод в базовом классе.  Можно задать способ взаимодействия методов, воспользовавшись ключевыми словами [new](../../../csharp/language-reference/keywords/new.md) и [override](../../../csharp/language-reference/keywords/override.md).  Модификатор `override` *разворачивает* метод базового класса, а модификатор `new` *скрывает* его.  В примере в этой теме показана эта разница.  
  
 В консольном приложении объявите следующие два класса: `BaseClass` и `DerivedClass`.  Тип `DerivedClass` наследуется от типа `BaseClass`.  
  
```c#  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
  
```  
  
 В методе `Main` объявите переменные `bc`, `dc`, и `bcdc`.  
  
-   Параметр `bc` имеет тип `BaseClass` и его значение — тип `BaseClass`.  
  
-   Параметр `dc` имеет тип `DerivedClass` и его значение — тип `DerivedClass`.  
  
-   Параметр `bcdc` имеет тип `BaseClass` и его значение — тип `DerivedClass`.  Это переменная, на которую следует обратить внимание.  
  
 Поскольку `bc` и `bcdc` имеют тип `BaseClass`, они могут только непосредственно осуществлять доступ к методу `Method1` \(если не используется приведение\).  Переменная `dc` может обращаться к `Method1` и `Method2`.  Эти связи показаны в следующем коде.  
  
```c#  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
  
```  
  
 Далее добавьте следующий метод `Method2` в класс `BaseClass`.  Сигнатура этого метода соответствует сигнатуре метода `Method2` в `DerivedClass`.  
  
```c#  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
  
```  
  
 Поскольку `BaseClass` теперь имеет метод `Method2`, можно добавить второй оператор вызова для переменных `bc` и `bcdc` класса `BaseClass`, как показано в следующем коде.  
  
```c#  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
  
```  
  
 При построении проекта видно, что добавление метода `Method2` в `BaseClass` вызывает предупреждение.  Это предупреждение говорит, что метод `Method2` в `DerivedClass` скрывает метод `Method2` в `BaseClass`.  Рекомендуется использовать ключевое слово `new` в определении `Method2`, если требуется получить такой результат.  Другой вариант — переименовать один из методов `Method2` для разрешения предупреждения, но это не всегда целесообразно.  
  
 Прежде чем добавлять `new`, выполните программу, чтобы увидеть выходные данные дополнительных операторов вызова.  Отобразятся следующие результаты.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
  
```  
  
 Ключевое слово `new` сохраняет связи, дающие этот результат, однако подавляет предупреждение.  Переменные, имеющие тип `BaseClass`, продолжают обращаться к элементам класса  `BaseClass`, а переменная, имеющая тип `DerivedClass`, продолжает обращаться к элементам в классе `DerivedClass` в первую очередь, а затем к элементам, унаследованным от `BaseClass`.  
  
 Чтобы подавить предупреждение, добавьте модификатор `new` в определение `Method2` в классе `DerivedClass`, как показано в следующем коде.  Модификатор можно добавить перед или после `public`.  
  
```c#  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
  
```  
  
 Запустите программу еще раз, чтобы убедиться, что результат не изменилась.  Также убедитесь, что предупреждение больше не появляется.  Используя ключевое слово `new`, вы утверждаете, что вам известно, что модифицируемый им член скрывается членом, который наследуется от базового класса.  Дополнительные сведения о скрытии имен через наследование см. в разделе [Модификатор new](../../../csharp/language-reference/keywords/new-modifier.md).  
  
 Чтобы противопоставить это поведение эффекту использования `override`, добавьте в `DerivedClass` следующий метод.  Модификатор `override` может быть добавлен перед или после `public`.  
  
```c#  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
  
```  
  
 Добавьте модификатор `virtual` к определению `Method1` в `BaseClass`.  Модификатор `virtual` может быть добавлен перед или после `public`.  
  
```c#  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
  
```  
  
 Снова запустите проект.  Обратите особое внимание на последние две строки следующих выходных данных.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
  
```  
  
 Использование модификатора `override` позволяет `bcdc` осуществлять доступ к методу `Method1`, определенному в `DerivedClass`.  Как правило, это требуемое поведение в иерархиях наследования.  Требуется, чтобы объекты со значениями, созданными из производного класса, использовали определенные в производном классе методы.  Это поведение достигается с использованием `override` для расширения метода базового класса.  
  
 Следующий код содержит полный пример.  
  
```c#  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending   
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
  
```  
  
 В следующем примере показано подобное поведение в другом контексте.  Пример определяет три класса: базовый класс `Car` и два класса, производных от него: `ConvertibleCar` и `Minivan`.  Базовый класс содержит метод `DescribeCar`.  Этот метод отображает общее описание автомобиля, а затем вызывает `ShowDetails` для предоставления дополнительной информации.  Каждый из трех классов определяет метод `ShowDetails`.  Для определения метода `ShowDetails` в классе `ConvertibleCar` используется модификатор `new`.  Для определения метода `ShowDetails` в классе `Minivan` используется модификатор `override`.  
  
```c#  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
  
```  
  
 В примере проверяется версия вызыванного `ShowDetails`.  Следующий метод, `TestCars1`, объявляет экземпляр каждого класса и затем вызывает `DescribeCar` на каждом экземпляре.  
  
```c#  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.    
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
  
```  
  
 `TestCars1` формирует следующие выходные данные.  Обратите особое внимание на результаты для `car2`, который, вероятно, не соответствуют ожидаемым.  Тип объекта — `ConvertibleCar`, но `DescribeCar` не получает доступа к версии `ShowDetails` , определенной в классе `ConvertibleCar`, потому что этот метод объявлен с модификатором `new`, а не `override`.  В результате объект `ConvertibleCar` отображает то же описание, что и объект `Car`.  Сравните результаты для `car3`, который является объектом `Minivan`.  В этом случае метод `ShowDetails`, объявляемый в классе `Minivan`, переопределяет метод `ShowDetails`, объявляемый в классе `Car`, и отображается описание микроавтобуса.  
  
```c#  
  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
  
```  
  
 `TestCars2` создает список объектов типа `Car` .  Значения объектов создаются из классов `Car`, `ConvertibleCar`, и `Minivan`.  `DescribeCar` вызывается для каждого элемента в списке.  В следующем коде показано определение `TestCars2`.  
  
```c#  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),   
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
  
```  
  
 Выводится следующий результат.  Обратите внимание, что это полностью соответствует выходным данным, отображаемым `TestCars1`.  Метод `ShowDetails` класса `ConvertibleCar` не вызывается независимо от того, является ли тип объекта `ConvertibleCar`, как в `TestCars1`, или `Car`, как в `TestCars2`.  И наоборот, `car3` вызывает метод `ShowDetails` из класса `Minivan` в обоих случаях, независимо от того, какого он типа — `Minivan` или `Car`.  
  
```c#  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
  
```  
  
 Методы `TestCars3` и `TestCars4` выполняют пример.  Эти методы вызывают `ShowDetails` непосредственно: сначала из объектов, объявленных с типом `ConvertibleCar` и `Minivan` \(`TestCars3`\), затем из объектов, объявленных с типом `Car` \(`TestCars4`\).  Следующий код определяет эти два метода.  
  
```c#  
  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
```  
  
 Методы производят следующий результат, который соответствует результатам из первого примера в этой теме.  
  
```c#  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
  
```  
  
 В следующем коде приведен полный проект и его результат.  
  
```c#  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.    
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),   
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
  
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [базовые](../../../csharp/language-reference/keywords/base.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)