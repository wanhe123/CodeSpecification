### 1、关于命名

##### 1> 统一要求
- 含义清楚，尽量做到不需要注释也能了解其作用，若做不到，就加注释
- 使用全称，不适用缩写

##### 2> 类的命名
- 大驼峰式命名：每个单词的首字母都采用大写字母
　　　例子：MFHomePageViewController
- 后缀要求
　ViewController: 使用ViewController做后缀
　例子: MFHomeViewController
 
##### 3> 私有变量
- 小驼峰式命名：第一个单词以小写字母开始，后面的单词的首字母全部大写
　　例子：firstName、lastName
- 以 _ 开头，第一个单词首字母小写
　　例子：NSString * _somePrivateVariable
- 私有变量放在 .m 文件中声明

      
