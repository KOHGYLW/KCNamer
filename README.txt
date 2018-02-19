KCNamer 随机中文名生成工具v1.0

-1- 说明：

>该工具可以通过姓氏字典+名称字典或随机汉字的方式生成随机的中文名称，并可自行指定生成姓名的性别风格和长度（2-4个字）。

-2- 1分钟快速开始：

2.1 在终端/命令行下使用：
>进入KCNamer.jar所在目录下。
>执行命令： 
$java -jar KCNamer.jar
>该命令可获得一个按照默认规则生成的、随机男女性别风格的、不限长度（2-4个字）的中文姓名。
>如果您想指定姓名的生成规则，请执行命令： 
$java -jar KCNamer.jar -h
即可查看可用的姓名生成选项。

2.2 在java应用中使用：
>首先，您需要将jar包导入至您的项目构建路径中。
>之后，请按照下方示例进行使用：
>代码示例：如何获得一个按照默认规则生成的、随机男女性别风格的、不限长度（2-4个字）的中文姓名并打印出来。

【code】

package kohgylw;

import kohgylw.randomChineseName.core.RandomChineseNameUtile;

public class MC {

	public static void main(String[] args) {
		RandomChineseNameUtile rcnu=new RandomChineseNameUtile();
		System.out.println(rcnu.getRandomName());
	}
}

【code】

>RandomChineseNameUtile类是本工具的核心类。其主要方法介绍如下：

public String getRandomName() 以默认规则获取一个随机生成的中文名称
public String getRandomFemaleName() 使用随机长度获取一个随机生成的女性风格的中文名
public String getRandomMaleName() 使用随机长度获取一个随机生成的男性风格的中文名
public String getRandomMaleName(NameLength nl) 根据指定长度获取一个随机生成的男性风格的中文名
public String getRandomFemaleName(NameLength nl) 根据指定长度获取一个随机生成的女性风格的中文名
public String getMaleNameOfSurname(String surname) 获取一个指定姓氏的随机男性风格名称
public String getFemaleNameOfSurname(String surname) 获取一个指定姓氏的随机女性风格名称
public String getComRandomName() 获取一个完全随机的、不分男女风格的、以姓氏字典中定义的姓氏为基础的名称

>如果您需要获得更详细的说明，请参阅其方法的文本注释。本工具的源代码包含在jar包之中，您可以随时查看它们。

-3- 关于随机姓名生成风格：使用“姓氏字典”和“名称字典”

>本工具内包含了一个默认的【姓氏字典】：
kohgylw.randomChineseName.core.DefultSurnameDictionaries
和一个默认的【名称字典】：
kohgylw.randomChineseName.core.DefultGivenNameDictionaries
>默认的【姓氏字典】中涵盖了《百家姓》内定义的所有单姓和复姓，而默认的【名称字典】中则涵盖了大多数现代常用的可用于起名的单字汉字和双字词组。如果您使用RandomChineseNameUtile()构造器实例化RandomChineseNameUtile对象，则该对象会使用上述默认字典进行随机姓名生成。
>接口定义：【姓氏字典】实现kohgylw.randomChineseName.core.SurnameDictionaries接口，而【名称字典】实现kohgylw.randomChineseName.core.GivenameDictionaries接口。
>自定义字典：您可以定义自己的姓氏字典和名称字典并实现上述接口，之后使用public RandomChineseNameUtile(SurnameDictionaries sd, GivenameDictionaries gd)构造器来实例化一个RandomChineseNameUtile对象，该对象会依照您的自定义字典来执行随机中文姓名的生成过程，这样您就可以得到更加个性化的姓名风格，例如使用古风风格的字典来专门生成古风风格的中文名（字典中的可选名称越多，生成的随机效果越好）。
>关于两种接口定义的方法及其需要实现的功能，请参见其文本注释。



