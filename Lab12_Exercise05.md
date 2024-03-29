# Lab 12 Exercise 5

## Abstract class

1.สร้าง console application project

```cmd
dotnet new console --name Lab12_Ex05
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
var shapes = new Shape[3];
shapes[0] = new Rectangle(10, 20);
shapes[1] = new Triangle(10, 20);
shapes[2] = new Circle(10);

foreach (var shape in shapes)
{
    shape.CalculateArea();
} 
abstract class Shape
{
    protected double Area;
    public abstract void Draw();
    public abstract void CalculateArea();
}
class Rectangle : Shape
{
    double width, height;
    public override void Draw()
    {
        System.Console.WriteLine($"Draw a rectangle with area {Area}");
    }
    public Rectangle(double W, double H)
    {
        width = W;
        height = H;
    }
    public override void CalculateArea()
    {
        Area = width * height;
        System.Console.WriteLine($"{this.GetType()} Area = {width:F5} x {height:F5} = {Area:F5} unit(s)");
    }
}
class Triangle : Shape
{
    double Base, Height;
    public override void Draw()
    {
        System.Console.WriteLine("Draw a triangle");
    }
    public Triangle(double B, double H)
    {
        Base = B;
        Height = H;
    }
    public override void CalculateArea()
    {
        Area = Base * Height * 0.5;
        System.Console.WriteLine($"{this.GetType()} Area = {Base:F5} x {Height:F5} x 1/2  = {Area:F5} unit(s)");
    }
}
class Circle : Shape
{
    double Radius;
    public override void Draw()
    {
        System.Console.WriteLine("Draw a circle");
    }
    public Circle(double R)
    {
        Radius = R;
    }
    public override void CalculateArea()
    {
        Area = Math.PI * Radius * Radius;
        System.Console.WriteLine($"{this.GetType()} Area = {Math.PI:F5} x {Radius} ^2  = {Area:F5} unit(s)");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab12_Ex05
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="793" alt="Screenshot 2024-03-29 160049" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-12/assets/144196049/18648eb8-4f52-4720-b8fa-491424fef5a0">

#### สามารถ Build ได้ เพราะ ทุกคลาสสืบทอดมาจาก abstract class Shape ซึ่งไม่มีโครงสร้างการทำงาน แต่สืบทอดไป class อื่น ทำให้เกิด override ทำให้สามารถแสดงผลข้อมูลที่แตกต่างกันไปในแต่ละ class
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab12_Ex05
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="795" alt="Screenshot 2024-03-29 160115" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-12/assets/144196049/f8228a92-179b-4472-98d1-62eeef901c9a">

#### สามารถ Run ได้ เพราะ สืบทอดมาแล้ว เกิด override แต่ละ class มีการทำงานที่แตกต่างกันตามที่กำหนด
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแกรมจะแสดงผล
#### Rectangle Area = 10.00000 x 20.00000 = 200.00000 unit(s)
#### Triangle Area = 10.00000 x 20.00000 x 1/2 = 100.00000 unit(s)
#### Circle Area = 3.14159 x 10 ^2 = 314.15927 unit(s)
