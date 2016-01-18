# HABanner
EZ to create Banner!

HABanner 可以简单容易创建一个banner，实际代码如下：

***********该框架依赖于SDWebImage，为了方便下载没有倒入，请自行倒入！***********

1.普通的banner,banner只是一个简单的图片,传入banner的frame和图片名字即可（无论图片来自网络还是本地），block是banner被点击时返回被点击的第几个view：
HADirect *direct=[HADirect direcWithtFrame:CGRectMake(0, 0, 375, 200) ImageArr:imgName AndImageClickBlock:^(NSInteger index) {
NSLog(@"%ld",(long)index);
}];

2.自定义banner，例如图片中既有图片和文字等等。。。,传入frame和自定义view的数组，block是banner被点击时返回被点击的第几个view
HADirect *direct2=[HADirect direcWithtFrame:CGRectMake(0, 0, 375, 200) ViewArr:CustomViewArr AndClickBlock:^(NSInteger index) {
NSLog(@"%ld",(long)index);
}];


*更多属性
@interface HADirect : UIView

//轮播的ScrollView
@property(strong,nonatomic) UIScrollView *direct;
//轮播的页码
@property(strong,nonatomic) UIPageControl *pageVC;
//轮播滚动时间间隔
@property(assign,nonatomic) CGFloat time;

//初始化图片格式的HADirect
+(instancetype)direcWithtFrame:(CGRect)frame ImageArr:(NSArray *)imageNameArray AndImageClickBlock:(imageClickBlock)clickBlock;

//初始化自定义样式的HADirect
+(instancetype)direcWithtFrame:(CGRect)frame ViewArr:(NSArray *)customViewArr AndClickBlock:(imageClickBlock)clickBlock;

//开始定时器
-(void)beginTimer;

//销毁定时器
-(void)stopTimer;
@end

可以自己修改banner的UIPageControl样式颜色，轮播速度，自定义开始、暂停等等功能！