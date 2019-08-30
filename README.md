# README

文件纵览

<pre>
|--lib
  |--common                             公共scss文件，变量等编译后不输出内容的文件
    |--_function.scss                   函数
    |--_mixins.scss                     mixinx
    |--_var.scss                        默认变量，所有变量使用!default修饰，方便定义其他主题
    |--index.scss                       导出出口
  |--common-modules                     公共的非业务模块，各个主题应存在相同名称的对应文件，使用@import引入对应文件
    |--flex.scss                        伸缩布局
    |--grid.scss                        网格
    |--transition.scss                  动画过渡
|--theme                                存放各个主题
  |--theme-1
    |--modules                          业务模块
      |--modules-x.scss                 业务模块x
      |--modules-xx.scss                业务模块xx
      ...                               ...
    |--_var.scss                        用于重置lib/common/_var.scss
    |--index.scss                       统一编译的出口，可使用按需编译
</pre>

theme/theme-x/modules/modules-x.scss

```scss
@import '../_var.scss';
@import '../../../lib/common/index.scss';
```
theme/theme-x/index.scss

```scss
@import './_var.scss';
@import '../../lib/common/index.scss';
```
