# Tricks

MAGENTO 2.3.0

1) /vendor/magento/framework/View/Element/Template/File/Validator.php:139

After installing magento 2.3 admin login page cant open properly

find : 
foreach ($directories as $directory) {
    if (0 === strpos($realPath, $directory)) {
        return true;
    }
}

Replace with:
foreach ($directories as $directory) {
    $realDirectory = $this->fileDriver->getRealPath($directory);
    // and replace `$directory` with `$realDirectory`
    if (0 === strpos($realPath, $realDirectory)) {
        return true;
    }
}

MAGENTO 2.1.x

1) fotorama.js:

Fix for Zoom Gallery Image Zoom the image can't be closed by iPhone with Safari browser:
https://github.com/magento/magento2/blob/cdf370b88900b2f8c00bda21de5647b99fd458be/lib/web/fotorama/fotorama.js#L1220

DJANGO 3.5.2 and PYTHON 3.7.1

1) widgets.py:

Fix for Django CMS 3.5.2 configured in DJANGO 1.11.x and PYTHON 3.7.1

DRUPAL 8.x

1) remove_generator.module

Remove Generator in Drupal 8.x

2) simplelogin.module

Fix for  Warning: array_flip(): Can only flip STRING and INTEGER values! when the module "Simple Login" upload a default image
