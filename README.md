## Flex Image

***

### Responsive spritesheets with Sass and Compass

Flexible elements with background images using a sprite.  

This mixin allows you to use sprites with flexible elements. In other words the sprite responds with the element.


### Requirements
Sprite must be generated using the compass magic sprite method

### Usage

	@include flexImage( $containerWidth, $elemWidth, $elemHeight, filename, $fullSpriteName );

- No units should be defined for $containerWidth, $elemWidth and $elemHeight
- filename is the name of the image without its extension (e.g. myicon.png >>> myicon)
- $fullSpriteName should be the name to access the entire sprite e.g $my-icons-sprites, $icons-sprites etc
- If a sprite is normally referred to as $sprite-name, you can access the entire sprite using $sprite-name-sprites
- $containerWidth is the width of the parent element. This is a really important value, so if something goes wrong this is always the first place to look at.


Example:

	.home {
		@extend .ui-main-home;
		@include flexImage(640, 80, 84, home, $ui-main-sprites);
	}
	
Check out the example demo for more information.

