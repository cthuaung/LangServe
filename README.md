# LangServe

And that's it! 

python app.py

we should see our chain being served at http://localhost:8000.

##Playground
Every LangServe service comes with a simple built-in UI for configuring and invoking the application with streaming output and visibility into intermediate steps. Head to http://localhost:8000/chain/playground/ to try it out! Pass in the same inputs as before - {"language": "spain", "text": "hi"} - and it should respond same as before.

Client
Now let's set up a client for programmatically interacting with our service. We can easily do this with the langserve.RemoteRunnable. Using this, we can interact with the served chain as if it were running client-side.

from langserve import RemoteRunnable

remote_chain = RemoteRunnable("http://localhost:8000/chain/")
remote_chain.invoke({"language": "spain", "text": "hi"})

'Hola'