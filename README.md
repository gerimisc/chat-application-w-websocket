# Chat Application (Let's learn about Goroutines, Channels and of course Gorilla's websocket

This is an attempt at learning by coding on GO PROGRAMMING BLUEPRINTS first exercise on websockets. More importantly, this should act as a note to myself on grasping the basics right.

### Web Server in Go
Setting up handlers:
1) Below chunk of simple code is a HTTP handler handling the "/" route. the Handler type is an anonymous function and can fit right in. Refer to (2) for more details.
```
// HTTP Handler for the route "/"
http.HandleFunc("/", func(w http.ResponseWriter, r  *http.Request) {
       w.Write([]byte(`SOMETHING IS A STRING`))})
// start the web server
if err := http.ListenAndServe(":8080", nil); err != nil {
  log.Fatal("ListenAndServe:", err)
}
```
2) To better understand handlers, they are simply functions that serve a certain route (in Laravel, for example). And this handler is of the type `Interface`. This means that any struct that has a method that satisfies the `http.Handler` type, e.g.`ServeHTTP(ResponseWriter, *Request)` can be plugged and played as a handler for any route of interest. For example:

```
// "Rendering" static pages. Allows *View to be passed directly to http.handler
func (v *View) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	// Do something
	}
}
```
A struct of type View can then be passed directly as a `http.Handler` to handle a route


### Goroutines

### Channels

Learning a ton from Mat Ryer!

