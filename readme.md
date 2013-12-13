### install

	npm install -g node-gyp
	
### create `binding.gyp`

	{
	  "targets": [
	    {
	      "target_name": "hello",
	      "sources": [ "hello.cc" ]
	    }
	  ]
	}
	
### write it


	
### build it
	
	node-gyp configure build