acimage
==============
Библиотека для ресайза и кропа изображений на yii2

Установка
------------
Предпочтительный способ установки этого расширения — через [composer](http://getcomposer.org/download/).

Либо вставьте
```
"nigabrein/acimage": "*"
```
в раздел require вашего файла `composer.json`

Использование
-----

```
use nigabrein\acimage\AcImage;
```
```
use nigabrein\acimage\AcColor;
```
```
use nigabrein\acimage\AcImageGIF;
```
```
use nigabrein\acimage\AcImageJPG;
```
```
use nigabrein\acimage\AcImagePNG;
```

```
$img = AcImage::createImage(Yii::getAlias('@web').$targetPath);
$sizes = [800, 400, 150];
$thumbnails_folder = 3;

$parts = explode('/', $targetPath);
$directory = implode('/', array_slice($parts, 0, -1));
$filename = end($parts);

foreach ($sizes as $size) {
    $img->thumbnail($size, $size, 3);
    $img->save(Yii::getAlias('@web') . $directory ."/thumbnails/size_". $thumbnails_folder ."/" . $filename);
    $thumbnails_folder--;
}
```
