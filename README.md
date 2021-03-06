# iOSControl
这里介绍了Objective-C中一些控件的常用功能，随时补充～

----------
##UILabel
####有时候我们会有这样的需求：设置label字体的行距、设置同一label里不同颜色／不同字号大小类型的字体、设置中划线／下划线……

NSMutableAttributedString可以设置以上label的常用的属性。  我们先说一下和 attributes有关的四个方法：
 
	 为某一范围内文字设置多个属性
	 - (void)setAttributes:(NSDictionary*)attrs range:(NSRange)range;
 
	 为某一范围内文字添加某个属性
	 - (void)addAttribute:(NSString*)name value:(id)value range:(NSRange)range;
 
	 为某一范围内文字添加多个属性
	 - (void)addAttributes:(NSDictionary*)attrs range:(NSRange)range;
 
	 移除某一范围内的某个属性
	 - (void)removeAttribute:(NSString*)name range:(NSRange)range;


通过属性名设置对应的需求value即可实现：
		
	行距：NSParagraphStyleAttributeName
	下划线：NSUnderlineStyleAttributeName
	下划线颜色：NSUnderlineColorAttributeName
	中划线：NSStrikethroughStyleAttributeName
	中划线颜色：NSStrikethroughColorAttributeName
	字体设置：NSFontAttributeName

demo里我已经封装到了类目里，有需要的可以拖走。

```
/** 设置不同颜色的字体
 *  @param label : label
 *  @param color : 设置成的特殊颜色
 *  @param colorText  设置特殊颜色的字体
 */
- (void)changeColorWithColor:(UIColor *)color
                   colorText:(NSString *)colorText;

/** 设置不同大小字体的字体
 *  @param font  目标文字的字体设置
 *  @param fontText 目标文字
 */
- (void)changeFontWithFont:(UIFont *)font
                  fontText:(NSString *)fontText;


/** 设置中划线
 *  @param text  要设置中划线的字体
 */
- (void)setThroughLineWithText:(NSString *)text;

/** 设置中划线——自定义颜色
 *  @param text 要设置中划线的字体
 *  @param textColor    要设置中划线的颜色
 */
- (void)setThroughLineWithText:(NSString *)text color:(UIColor *)textColor;



/** 设置下划线
 *  @param text  要设置下划线的字体
 */
- (void)setUnderLineWithText:(NSString *)text;

/** 设置下划线——自定义颜色
 *  @param text 要设置下划线的字体
 *  @param textColor    要设置下划线的颜色
 */
- (void)setUnderLineWithText:(NSString *)text color:(UIColor *)textColor;


/** 设置多行label的行距
 */
- (void)changeLabelSpaceWithSpace:(NSInteger)space text:(NSString *)text;

```

效果：

![这里写图片描述](http://img.blog.csdn.net/20161110103856919)


----------
