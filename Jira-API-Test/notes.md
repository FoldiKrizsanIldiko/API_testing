**Newman is a command-line Collection Runner for Postman.**  
It enables you to run and test a Postman Collection directly from the command line. It's built with extensibility in mind so that you can integrate it with your continuous integration (CI) servers and build systems.


install newmnan with  
``` npm install -g newman@latest```

in Postman export the collection.

open terminal in folder with the .json file(where you exported the collection)

run the newman:  
  
  
``` newman run <name_of_collection>.json```

![alt text](runInTerminalWithNewman.png)

  
U can use a public link to run your test. Share your Collection :  
![alt text](sahreLinkPostman.png)

run with:  
``` newman run  https://api.postman.com/collections/26496391-f5cead71-bfab-4f45-ba4d-ae8610b94285?access_key=<acces key>```  
