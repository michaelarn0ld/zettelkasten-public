# Introduction to Concurrency in Go: Goroutines & Channels


## Goroutine
A ***goroutine*** is a lightweight thread managed by the go runtime
```go
go f(x, y, z)
```
starts a new goroutine running 
```go
f(x, y, z)
```
where the evaluation of ```f(), x, y, z``` happens in the current goroutine and
their execution happen in the new goroutine.


## Channel
Channels must be created before use
```go
ch := make(chan int)
```
Channels are a type of conduit through which you can send and recieve values
with the channel operator ```<-````
```go
ch <- v // send v to channel ch
v := <-ch // recieve from channel ch and assign to v
```

By default, channels are unbuffered which essentially means that they cannot 
store data. Any send on a channel is then blocked until there is another 
goroutine to receive it.

```go
func main() {
    ch := make(chan int)
    go send(ch)
    go receive(ch)
    time.Sleep(time.Second * 3) // timeout to allow goroutines time to execute
}

func send(ch chan int) {
    fmt.Println("Sending to channel ch")
    ch <- 1
    fmt.Println("Send complete!")
}

func receive(ch chan int) {
    time.Sleep(time.Second * 1)
    fmt.Println("Recieving from channel ch")
    val := <-ch
    time.Sleep(time.Second * 1)
    fmt.Println(val)
}
```

Output
```bash
Sending to channel ch
Recieveing from channel ch
Send complete!
1
```

You can also create a ***buffered channel*** which has capacity to hold some
data.
```go
ch := make(chan int, capacity)
```

With a buffered channel the default rules for send and receive are slightly 
different:
* Sends on a buffered channel are only blocked if the channel is full
* Recieves from a buffered channel are only blocked if the channel is empty


## Related 

## Tags
#go
