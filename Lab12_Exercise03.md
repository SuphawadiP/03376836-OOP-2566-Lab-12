# Lab 12 Exercise 3

## Abstract class

1.สร้าง console application project

```cmd
dotnet new console --name Lab12_Ex03
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
Animal[] animals = new Animal[3];
animals[0] = new Dog();
animals[1] = new Fish();
animals[2] = new Bird();

foreach (var animal in animals)
{
    animal.Move();
}

abstract class Animal
{
    public abstract void Move();
}
class Dog: Animal
{
    public override void Move()
    {
        System.Console.WriteLine($"{this.GetType()}: running on the ground");
    }
}
class Fish: Animal
{
    public override void Move()
    {
        System.Console.WriteLine($"{this.GetType()}: swimming in water");
    }
}
class Bird: Animal
{
    public override void Move()
    {
        System.Console.WriteLine($"{this.GetType()}: fly in the air");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab12_Ex03
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="788" alt="Screenshot 2024-03-29 154912" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-12/assets/144196049/8c3c59b1-aed0-43d4-b9e3-f6f3f2dedc39">

#### สามารถ Build ได้ เพราะ ทุกคลาสสืบทอดมาจาก abstract class Animal ซึ่งไม่มีโครงสร้างการทำงาน แต่สืบทอดไป class อื่น ทำให้เกิด override ทำให้สามารถแสดงผลข้อมูลที่แตกต่างกันไปในแต่ละ class
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab12_Ex03
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="796" alt="Screenshot 2024-03-29 154938" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-12/assets/144196049/7cd4a6ef-15c7-4264-974a-527f98f2ead6">

#### สามารถ Run ได้ เพราะ สืบทอดมาแล้ว เกิด override แต่ละ class มีการทำงานที่แตกต่างกันตามที่กำหนด
7.อธิบายสิ่งที่พบในการทดลอง
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแกรมจะแสดงผล
#### Dog: running on the ground
#### Fish: swimming in water
#### Bird: fly in the air
