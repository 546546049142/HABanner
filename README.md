# HABanner
EZ to create Banner!

HABanner 致力于最简单容易的banner!

***********该框架依赖于SDWebImage，为了方便下载没有倒入，请自行倒入！***********

##怎么用
###所有banner都有的功能，但突出简单容易上手：
1.普通的banner,banner只是一个简单的图片,传入banner的frame和图片名字即可（无论图片来自网络还是本地），block是banner被点击时返回被点击的第几个view：
```Object-C
HADirect *direct=[HADirect direcWithtFrame:CGRectMake(0, 0, 375, 200) ImageArr:imgName AndImageClickBlock:^(NSInteger index) {
NSLog(@"%ld",(long)index);
}];
```
###特色功能，完全自定义banner，拒绝限制，完全open，满足任何产品经理，甚至每一个页面都不相同的需求
2.自定义banner，例如图片中既有图片和文字等等。。。,传入frame和自定义view的数组，block是banner被点击时返回被点击的第几个view
```Object-C
HADirect *direct2=[HADirect direcWithtFrame:CGRectMake(0, 0, 375, 200) ViewArr:CustomViewArr AndClickBlock:^(NSInteger index) {
NSLog(@"%ld",(long)index);
}];
```

#更多属性

```Object-C
@interface HADirect : UIView

//轮播的ScrollView
@property(strong,nonatomic) UIScrollView *direct;

//轮播的页码
@property(strong,nonatomic) UIPageControl *pageVC;

//轮播滚动时间间隔
@property(assign,nonatomic) CGFloat time;

//网络加载可以选择需要使用的占为图片
@property(nonatomic,strong) NSString *placeholderName;

#pragma mark 初始化图片格式的HADirect
+(instancetype)direcWithtFrame:(CGRect)frame ImageNameArr:(NSArray *)imageNameArray AndImageClickBlock:(imageClickBlock)clickBlock;

#pragma mark 初始化自定义样式的HADirect
+(instancetype)direcWithtFrame:(CGRect)frame ViewArr:(NSArray *)customViewArr AndClickBlock:(imageClickBlock)clickBlock;

#pragma mark 开始定时器
-(void)beginTimer;

#pragma mark 销毁定时器
-(void)stopTimer;

#pragma mark 自定义UIPageControl样式（图片大小要合适）
-(void)customPageVcWithSelectedImg:(UIImage *)selectedImg NormalImg:(UIImage *)normalImg;
```

可以自己修改banner的UIPageControl样式颜色，轮播速度，自定义开始、暂停等等功能！

发现问题可联系546049142@qq.com,欢迎使用！