# nw-context

Modules loaded using `require()` inside node-webkit do not have access to the browser's usual globals such as `window` and `document`. To restore this behaviour it is possible to assign such objects to node's `global` object, but if you don't feel like polluting your global namespace, this module is for you.

Set up in the browser:

	var context = require('nw-context');
	context.set({
		window: window,
		document: document
	});

Then from within other modules:

	var window = require('nw-context').window,
		document = require('nw-context').document;
