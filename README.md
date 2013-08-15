# Flex Image

***

## Responsive spritesheets with Sass and Compass

Flexible elements with background images using a sprite.  

This mixin allows you to use sprites with flexible elements. In other words the sprite responds with the element.

[Demo](http://zeezali.github.io/flex-image/)


## Requirements

Sass  
Compass  
Sprite must be generated using the compass magic sprite method

## Setting up the Sprite using Compass

	$ui-main-spacing: 2px; // Doesn't work with smart layout

This particular set up does not work with ‘smart’ sprite layouts. This is because the sprite doesn’t respond 100% accurately so we have to make sure there is a little buffer between each image in the sprite. We’re just accounting for the small margin of error that may occur when a sprite scales down. You can increase the spacing value to whatever you like.


## Usage

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

## Outputted values

Here is an example of what the outputted values look like:

	.elem {
	    width: 99.53704%;
	    padding-top: 100%;
	    background-size: 100.46512% 1006.48148%;
	    background-position: 0 55.51583%;
	}

## Credits
 [The icons in the example demo are by Vlad Chernushevich.](http://dribbble.com/shots/1163510-hicons-free-outline-icons)
