# promtool-distro

Download promtool 
make the file executable: $ chmod +x promtool

for the first time, you need to launch from Apple Finder, using 'file open'. It will show a popup asking for your permission to run it. (say yes). It should launch and shell and run it. Exit that. 

Launch a new shell to run it from there. 
You will need a directory for your promtool files. 
1. Create a directory for your promtool home.
2. Set the PROMTOOL_HOME to your promtool home.
3. Now, when you start the app it should look like this:
```
% cd ~/Downloads 
~/Downloads % ./promtool 
Using PROMTOOL_HOME: /Users/brianmcginnis/Brian/promtool/home
promtool rootCmd running...

```
4. promtool is also a cli. So, you need to tell it to run in 'server' mode to use it as a REST API and Web app server.
5. Start it again in server mode: ```$ ./promtool server```

You should see something like this:
```
Using PROMTOOL_HOME: /Users/brianmcginnis/Brian/promtool/home
server mode starting up...
Server started. Hit ^C to exit.
... other stuff ...
```

6. Documentation is coming soon. To use it you will need some files in your $PROMTOOL_HOME directory. Copy the files in this repo's /promtool-home into your promtool home. When that's done it should look something like this:

```
$ tree $PROMTOOL_HOME
/Users/brianmcginnis/Brian/promtool/home
├── archive
│   └── prompts
│       ├── service.controller.add-endpoint
│       │   └── 20250219143850
│       │       ├── content.hbs
│       │       ├── doc.md
│       │       ├── input-default.yaml
│       │       ├── input-schema.yaml
│       │       └── properties.yaml
... snip ...
```

7. Try a few curl commands to see if REST API is working for you. You should see JSON responses with data from the promtool home files. 
```
// Get summaries of all projects
curl --request GET --url http://localhost:9000/api/v1/projects

// Get prompt by id
curl --request GET --url http://localhost:9000/api/v1/prompt/service.controller.add-endpoint
```

8. Run the webapp, by putting this url in your browser: ```http://localhost:9000/```




