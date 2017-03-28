# Ari_Image

An image manipulation script for Wordpress.

Handles downscaling, upscaling, cropping, and also creating retina images.

## Usage:

```php
$image  = Ari_Image::create( $image_url_or_id );
$resize = $image->resize( array( 'width' => 500, 'height' => 300 ) );

$new_url = $resize['url'];
```

## Arguments for the `resize` method:

```php
array(
  'width'     => '',
  'height'    => '',
  'crop'      => true,
  'retina'    => true,
  'resize'    => true,
);
```

* If you only define `width` or `height` the image will be resized using the original ratio. The missing value will be autocalculated.
* If you define both width & height then the image will be resized & cropped to the defined dimensions unless `crop` is set to `false`.
* If `retina` is set to `true` (default) then an extra file will be created using the `@2x` suffix.
