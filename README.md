# Li'l Brother

Li'l Brother tracks clicks on web pages, without blocking any interaction.

## Client

    <script type="text/javascript" src="http://server/lilbro.js"></script>
    <script type="text/javascript">
    	// listen for click and change events on the wrapper element
    	var lilBro = new LilBro({
    		element: document.getElementById('lil_bro'),
    		server: 'server:8080',
    		ssl_server: 'server:8443',
    		track_focus: true
    	});
    
    	// register a click handler that snakes some data from the DOM,
    	// and specifies the the event type.
    	// This wont bubble to the wrapper element being watched.
    	lilBro.watch({
    		element: document.getElementById('search_button'),
    		callback: function(e) {
    			e.set(
    				'element_value',
    				document.getElementById('search_term').value
    			);
    			e.set('event_type', 'search');
    		}
    	});
    
    	// fire an event right now.
    	lilBro.write({
    		'event_type': 'page_load'
    	});
    </script>

## Server

cd lil_brother/server && ./bin/lilbro

## Authors

This library was developed by Douglas Hunter, Dave Kozma and Eric Smiling at [Shutterstock](http://www.shutterstock.com)

## License

Copyright (C) 2012 by Shutterstock Images, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

