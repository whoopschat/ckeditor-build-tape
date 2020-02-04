ckeditor5-build-tape
========================================

## Quick start

First, install the build from npm:

```bash
npm install --save ckeditor5-build-tape
```

And use it in your website:

```html
<div id="toolbar-container"></div>
<div id="editor">
	<p>This is the editor content.</p>
</div>
<script src="./node_modules/ckeditor5-build-tape/build/ckeditor.js"></script>
<script>
	DecoupledEditor
		.create( document.querySelector( '#editor' ) )
		.then( editor => {
			// The toolbar needs to be explicitly appended.
			document.querySelector( '#toolbar-container' ).appendChild( editor.ui.view.toolbar.element );

			window.editor = editor;
		} )
		.catch( error => {
			console.error( 'There was a problem initializing the editor.', error );
		} );
</script>
```

Or in your JavaScript application:

```js
import TapeEditor from 'ckeditor5-build-tape';

// Or using the CommonJS version:
// const TapeEditor = require( 'ckeditor5-build-tape' );

TapeEditor
	.create( document.querySelector( '#editor' ) )
	.then( editor => {
		// The toolbar needs to be explicitly appended.
		document.querySelector( '#toolbar-container' ).appendChild( editor.ui.view.toolbar.element );

		window.editor = editor;
	} )
	.catch( error => {
		console.error( 'There was a problem initializing the editor.', error );
	} );
```

**Note:** If you are planning to integrate CKEditor 5 deep into your application, it is actually more convenient and recommended to install and import the source modules directly (like it happens in `ckeditor.js`). Read more in the [Advanced setup guide](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/advanced-setup.html).
