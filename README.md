# fantastic-system
# java第五次实验
  计G202班 2020322096 申麓
# 实验目的
1. 掌握字符串String及其方法的使用
2. 掌握文件的读取/写入方法
3. 掌握异常处理结构
# 实验要求
在某课上,学生要提交实验结果，该结果存储在一个文本文件A中。
文件A包括两部分内容：
一是学生的基本信息；
二是学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法，实现如下功能：

每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
允许提供输入参数，统计古诗中某个字或词出现的次数
输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
考虑操作中可能出现的异常，在程序中设计异常处理程序
# 实验过程
此次实验创建了两个类，一个Student类用来实例化学生，一个Test类用来做文档的输入输出处理和统计查找的字的出现的次数
- 创建一个学生类为Student，实例化一名学生，可以通过键盘录入来让学生输入自己的信息
信息包括 姓名，学号，年龄
```
Scanner sc= new Scanner(System.in);

        System.out.println("输入姓名：");
        name=sc.next();

        System.out.println("输入学号：");
        stuNum=sc.nextInt();

        System.out.println("输入年龄：");
        age=sc.nextInt();

        String str="姓名:"+name+" 学号:"+stuNum+" 年龄:"+age;
        return str;

```
- 创建一个Test类用来读取和写入文档和查找字数
查找字数也采用键盘录入的方式
```
Scanner sc = new Scanner(System.in);
                System.out.println("输入你要查找的字或词：");
                char o = sc.next().charAt(0);
                char[] ch =str.toCharArray();
                for(int i=0;i<ch.length;i++){
                    if(o==ch[i]){
                        count++;
                    }

                }

                System.out.println("你输入的字或词在诗中出现过"+count+"次。")
```
读取文档
```
  File file = new File("B.txt");
        FileInputStream fis = new FileInputStream(file);
        ByteOutputStream bos = new ByteOutputStream();
        
        int len;
                byte[] data = null;
                byte[] buffer = new byte[(int) file.length()];

                while ((len=fis.read(buffer))!=-1){
                    bos.write(buffer,0,len);
                }

                data = bos.toByteArray();
                String str = new String(data);
```
写入文档，要求把实例化之后的学生信息，和做过处理的诗词一起写入进A文档中
处理诗词时，用一个简单的for循环，每7个字加一个逗号，每14个字加一个句号。
```
 Student st = new Student();
            char[] b = st.x().toCharArray();
            out.write(b);                   
            out.write("\n");

            char[] c = new char[(int) file.length()];

            in.read(c);
```
# 运行结果
控制台运行结果
![](https://github.com/shenlu-hub/fantastic-system/blob/main/%E6%8E%A7%E5%88%B6%E5%8F%B0%E7%BB%93%E6%9E%9C.JPG)
其中让程序查找“三”这个字，程序会给出反馈，学生信息用键盘录入
A文件中显示结果
![]()



