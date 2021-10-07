# Basic Modules in Go
I struggled with getting code to comppile whehn I was using local packages in
go ***for a very long time***

Turns out, its actually quite simple. I have a project for learning go called
"gopl", which located in my ```$PUBLIC/boost``` directory. If I want to make
packages within here, all I need to do is:
```bash
cd $PUBLIC/boost/gopl && go mod init gopl
```

Now, let's say I make a ```tempconv``` package in ```gopl/ch2/tempconv``` and
I want to use its namespace in another package within gopl:
```bash
import "gopl/ch2/tempconv"
```


## Tags
#go
