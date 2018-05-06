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

##### 4> property变量
- 小驼峰式命名  
　　　例子：///注释
　　　　　　@property (nonatomic, copy) NSString *userName;
- 禁止使用synthesize关键词

##### 5> 宏命名
- 全部大写，单词间用 _ 分隔。[不带参数]  
　　例子: #define THIS_IS_AN_MACRO @"THIS_IS_AN_MACRO"
- 以字母 k 开头，后面遵循大驼峰命名。[不带参数]  
　　例子：#define kWidth self.frame.size.width
- 小驼峰命名。[带参数]  
　　#define getImageUrl(url) [NSURL URLWithString:[NSString stringWithFormat:@"%@%@",kBaseUrl,url]]

##### 6> Enum
- Enum类型的命名与类的命名规则一致
- Enum中枚举内容的命名需要以该Enum类型名称开头
　　例子:
 ```
 typedef NS_ENUM(NSInteger, AFNetworkReachabilityStatus) {
     AFNetworkReachabilityStatusUnknown = -1,
     AFNetworkReachabilityStatusNotReachable = 0,
     AFNetworkReachabilityStatusReachableViaWWAN = 1,
     AFNetworkReachabilityStatusReachableViaWiFi = 2
     };
```
##### 7> Delegate命名
- 类的实例必须为回调方法的参数之一, 如  
　　-(NSInteger)tableView:(UITableView)tableView numberOfRowsInSection:(NSInteger)section
- 回调方法的参数只有类自己的情况，方法名要符合实际含义, 如:  
　　-(NSInteger)numberOfSectionsInTableView:(UITableView)tableView
- 以类的名字开头(回调方法存在两个以上参数的情况)以表明此方法是属于哪个类的, 如:  
　　-(UITableViewCell)tableView:(UITableView)tableView cellForRowAtIndexPath:(NSIndexPath )indexPath
- 使用did和will通知Delegate已经发生的变化或将要发生的变化, 如:  
　　-(NSIndexPath)tableView:(UITableView)tableView willSelectRowAtIndexPath:(NSIndexPath)indexPath;  
　　-(void)tableView:(UITableView)tableView didSelectRowAtIndexPath:(NSIndexPath)indexPath;

### 2、私有方法及变量声明
　##### 1> 声明位置
　　在.m文件中最上方，定义空的category进行声明

### 3、关于注释
　最好的代码是不需要注释的 尽量通过合理的命名  
　良好的代码把含义表达清楚 在必要的地方添加注释  
　注释需要与代码同步更新  
　如果做不到命名尽量的见名知意的话，就可以适当的添加一些注释或者mark  
　##### 1> 属性注释
　　例子：
　　　　/// 学生
　　　　@property (nonatomic, strong) Student *student;
##### 2> 方法声明注释：
```
     /** 
  　　* @brief 登录验证
  　　*
  　　* @param personId 用户名
  　　* @param password 密码
  　　* @param complete 执行完毕的block
  　　*
  　　* @return
  　　*/
 　　+ (void)loginWithPersonId:(NSString *)personId password:(NSString *)password complete:(void (^)(
```

### 4、格式化代码

#####　1> 指针 "" 位置  
　　定义一个对象时，指针 "" 靠近变量  
　　　例子: NSString *userName;
#####　2> 方法的声明和定义  
　　在 - 、+ 和 返回值 之间留一个空格，方法名和第一个参数之间不留空格
#####  3> 代码缩进
- 使用 xcode 默认缩进，即 tab = 4空格
- 使用 xcode 中 re-indent 功能定期对代码格式进行整理
- 相同类型变量声明需要独行声明  
　　例子:  
CGFloatoringX = frame.origin.x;  
CGFloatoringY = frame.origin.y;  
CGFloatlineWidth = frame.size.width;  
- Method与Method之间空一行  
##### 4> 对method进行分组
　　使用 #pragma mark - 方式对类的方法进行分组
##### 5> 大括号写法
- 对于类的method: 左括号另起一行写(遵循苹果官方文档)
- 对于其他使用场景: 左括号跟在第一行后边
```
- (instancetype)init
{
  self = [super init];
  if (self) {
    // ...
  }
  return self;
}
```
- 任何需要写大括号的部分，不得省略
      
