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

    #include <node.h>
    #include <v8.h>

    using namespace v8;

    Handle<Value> Method(const Arguments& args) {
      HandleScope scope;
      return scope.Close(String::New("world"));
    }

    void init(Handle<Object> target) {
      NODE_SET_METHOD(target, "hello", Method);
    }

    NODE_MODULE(binding, init);

	
### build it
	
	node-gyp configure
	node-gyp build