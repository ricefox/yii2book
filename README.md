# yii2book

Yii2 学习笔记

模块必须定义layout属性。
```
class ArticleModule extends \yii\base\Module
{
    /**
     * @inheritdoc
     */
    public $layout='main';
    public $controllerNamespace = 'ricefox\article\controllers';
    
}
```
这里如果不定义layout属性的话，yii将使用当前application的layoutPath下的布局文件，而不是当前模块的layoutPath下对应的布局文件。

bundle的sourcePath属性不能使用相对路径，否者将会出现循环复制的错误

```
class BaseAsset extends \yii\web\AssetBundle
{
    public $sourcePath;
    public $css=[
        'base.css',
    ];
    public function init()
    {
        parent::init();
        $this->sourcePath=__DIR__.'/assets';
    }
}
```
