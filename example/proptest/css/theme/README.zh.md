## Dependencies

主题是使用Sass编写的,以保持模块化并减少跨文件重复选择器的需要.在继续之前,请确保您已安装reveal.js开发环境,包括已安装的Grunt依赖项:<https://github.com/hakimel/reveal.js#full-setup>

## Creating a Theme

要创建自己的主题,首先要复制a`.scss`档案[/css/theme/source](https://github.com/hakimel/reveal.js/blob/master/css/theme/source).它将由Grunt从Sass自动编译为CSS(参见[Gruntfile](https://github.com/hakimel/reveal.js/blob/master/Gruntfile.js))当你跑步`npm run build -- css-themes`.

每个主题文件按以下顺序执行四项操作:

1.  **包括[/css/theme/template/mixins.scss](https://github.com/hakimel/reveal.js/blob/master/css/theme/template/mixins.scss)**共享实用功能.

2.  **包括[/css/theme/template/settings.scss](https://github.com/hakimel/reveal.js/blob/master/css/theme/template/settings.scss)**声明模板文件(步骤4)所需的一组自定义变量.可以在第3步中覆盖.

3.  **覆盖**这是您覆盖默认主题的位置.通过指定变量(参见[settings.scss](https://github.com/hakimel/reveal.js/blob/master/css/theme/template/settings.scss)供参考)或添加任何选择器和样式.

4.  **包括[/css/theme/template/theme.scss](https://github.com/hakimel/reveal.js/blob/master/css/theme/template/theme.scss)**模板主题文件,它将根据当前定义的变量生成最终的CSS输出.
