# Twenty Seventeen - theme boilerplate set up with [React-Union](https://github.com/lundegaard/react-union.git)

This project is an example of React-Union and React-Union-Scripts working together with CMS Wordpress and its default Twentyseventeen theme.

## Setting up the example

Copy the files as a theme into existing Wordpress installation (preferably clean) and activate it. You should see React-Union loaded within first post.

## Changes in theme

### Added Javacript files for React-Union

Located in directory ```assets/js```

```sh
content.widget.7c6da7f3.chunk.js
hero.widget.d6ff002c.chunk.js
SampleApp.bundle.js
vendor.bundle.js
```

### Functions.php

Included core files for React-Union, lines 457-458

```sh
wp_enqueue_script( 'react-union-vendor', get_theme_file_uri( '/assets/js/vendor.bundle.js' ), null , '1.0.0', true ); 
wp_enqueue_script( 'react-union-sample-app', get_theme_file_uri( '/assets/js/SampleApp.bundle.js' ), null , '1.0.0', true ); 
```

### Content.php

Content template file in ```template-parts/post/content.php``` is set up with DOM-marks to render React-Union components, lines 70-87.

```sh
    <div class="react-widget">
		React-union widget
        
		<div id="hero"></div>
		<script data-union-widget="" type="application/json">
		{
			"name": "hero",
			"container": "hero"
		}
		</script>

		<div id="react-content"></div>
		<script data-union-widget="" type="application/json">
		{
			"name": "content",
			"container": "react-content"
		}
		</script>
	</div>
```

